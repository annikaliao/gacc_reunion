<head>
<style>
.none {
  display: none;
}
span {
  color: dark red;
  font-size: 30px;
}
h1 .title {
  color: darkred;
}
button {
  padding: 10px;
  background-color: darkred;
  border-radius: 10px;
  text-align: center;
  justify-content: center;
  color: darkred;
}
input {
  color: black;
}
.tracker td {
  padding: 60px;
  width: 33.3%;
  text-align: center;
  color: darkred;
  font-size: 20px;
  border: none;
}
.tracker {
  background-color: #ffe1e8;
  border: none;
}
.date td {
  padding: 20px;
  width: 250px;;
}
.unhealthy {
  display: inline-block;
  font-size: 20px;
  border-color: darkred;
  padding: 20px;
  color: darkred;
}
a {
  color: black;
}
a.hover a.focus {
  background: none;
}
</style>
</head>
<body>


<h1 style="color:darkred;" >Cycle Tracker</h1>


<div>
  <form class="tracker">
    <table align="center" style="border:none;">
      <tr id="q">
        <td>When was the first day of your last period?</td>
        <td>How many days did it last?</td>
        <td>How long is your usual menstrual cycle?</td>
      </tr>
      <!--collect user input-->
        <tr id="input">
          <td><input type="date" id="lastperiod" required></td>
          <td><input type="number" id="periodlength" step="1" min="1" max="10" placeholder="1-10" required/></td>
          <td><input type="number" id="cyclelength" step="1" min="10" max="50" placeholder="10-50" required/></td>
        </tr>
      <tr>
        <td></td>
        <td>
          <button class="track" type="button" onclick="printDate(); validate()">
            TRACK
          </button>
        </td>
      </tr>
    </table>
  </form>
</div>
<br>
<div class="date">
  <p style="font-size: 30px; color: darkred;">Next Period:</p>
  <table>
    <tr>
      <td>
        <span id="nextperiod"></span>
      </td>
      <td>
        <p style="text-align: center; color: darkred; font-weight:bolder; font-size: 20px;">&#x2964;</p>
      </td>
      <td>
        <span id="nextperiodend"></span>
      </td>
    </tr>
  </table>
  <br>
  <span class="unhealthy" id="unhealthy"></span>
</div>
  <h1 style="text-align: center; color: darkred;" >&#65086;</h1>
<br>
<script>
  // print date of next period
  function printDate() {
    // get user inputs
    const x = document.getElementById("lastperiod").value;
    var y = document.getElementById("cyclelength").value;
    const z = document.getElementById("periodlength").value;
    // calculate date
    var resDate = new Date(x);
    resDate.setDate(resDate.getDate() + parseInt(y));
    var year = resDate.getUTCFullYear();
    var month = resDate.getUTCMonth() + 1;
    var startdate = resDate.getUTCDate();
    // print dates onto site
    const periodstart = `${month}/${startdate}/${year}`;
    document.getElementById("nextperiod").innerHTML = periodstart
    var enddate = resDate.getUTCDate() + parseInt(z);
    const periodend = `${month}/${enddate}/${year}`
    document.getElementById("nextperiodend").innerHTML = periodend
    // conditional for if period has unhealthy schedule
    if(parseInt(z) <= 2) {
      document.getElementById("unhealthy").innerHTML = "NOTICE: Your period is abnormally short. This may be a sign of some health concerns.   <a href=\"https://www.everydayhealth.com/pms/short-periods.aspx#:~:text=A%20short%20menstrual%20period%20might,even%20a%20serious%20medical%20problem.\">Learn More</a>" ;
    }
  }
</script>
<!--table displaying data from database-->
<table>
  <thead>
  <tr>
    <th>Your Periods</th>
    <th>Period Length</th>
    <th>Cycle Length</th>
  </tr>
  </thead>
  <tbody id="periodresult">
    <!-- javascript generated data -->
  </tbody>
</table>
<br><br>
<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("periodresult");
  // prepare URL's to allow easy switch from deployment and localhost
  //const url = "http://localhost:8087/api/periods"
  const url = "https://flowhealth.duckdns.org/api/periods"
  const create_fetch = url + '/create';
  const read_fetch = url + "/";
  const delete_fetch = url + "/delete";
  // Load users on page entry
  read_users();
  // Display User Table, data is fetched from Backend Database
  function read_users() {
    // prepare fetch options
    const read_options = {
      method: 'GET', // *GET, POST, PUT, DELETE, etc.
      mode: 'cors', // no-cors, *cors, same-origin
      cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
      credentials: 'omit', // include, *same-origin, omit
      headers: {
        'Content-Type': 'application/json'
      },
    };
    // fetch the data from API
    fetch(read_fetch, read_options)
      // response is a RESTful "promise" on any successful fetch
      .then(response => {
        // check for response errors
        if (response.status !== 200) {
            const errorMsg = 'Database read error: ' + response.status;
            console.log(errorMsg);
            const tr = document.createElement("tr");
            const td = document.createElement("td");
            td.innerHTML = errorMsg;
            tr.appendChild(td);
            resultContainer.appendChild(tr);
            return;
        }
        // valid response will have json data
        response.json().then(data => {
            console.log(data);
            for (let row in data) {
              console.log(data[row]);
              add_row(data[row]);
            }
        })
    })
    // catch fetch errors (ie ACCESS to server blocked)
    .catch(err => {
      console.error(err);
      const tr = document.createElement("tr");
      const td = document.createElement("td");
      td.innerHTML = err;
      tr.appendChild(td);
      resultContainer.appendChild(tr);
    });
  }
  function create_user(){
    const body = {
        nextperiod: document.getElementById("lastperiod").value,
        periodlength: document.getElementById("periodlength").value,
        cyclelength: document.getElementById("cyclelength").value,
        //nextperiod: nextP,
        //periodlength: periodL,
        //cyclelength: cycleL
    };
    //alert(body.toString());
    const requestOptions = {
        method: 'POST',
        body: JSON.stringify(body),
        headers: {
            "content-type": "application/json",
            'Authorization': 'Bearer my-token',
        },
    };
    // URL for Create API
    // Fetch API call to the database to create a new user
    fetch(create_fetch, requestOptions)
      .then(response => {
        // trap error response from Web API
        if (response.status !== 200) {
          const errorMsg = 'Database create error: ' + response.status;
          console.log(errorMsg);
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.innerHTML = errorMsg;
          tr.appendChild(td);
          resultContainer.appendChild(tr);
          return;
        }
        // response contains valid result
        response.json().then(data => {
            console.log(data);
            // add_row(data);
        })
    })
  }
  function add_row(data) {
    const tr = document.createElement("tr");
    const nextperiod = document.createElement("td");
    const periodlength = document.createElement("td");
    const cyclelength = document.createElement("td");
    // obtain data that is specific to the API
    nextperiod.innerHTML = data.nextperiod;
    periodlength.innerHTML = data.periodlength;
    cyclelength.innerHTML = data.cyclelength;
    console.log(data)
    // add HTML to container
    tr.appendChild(nextperiod);
    tr.appendChild(periodlength);
    tr.appendChild(cyclelength);
    resultContainer.appendChild(tr); 
    create_user(data.nextperiod, data.periodlength, data.cyclelength)
  }
  function addData(){
    if(document.getElementById("lastperiod").value&&document.getElementById("periodlength").value&&document.getElementById("cyclelength").value)
      myData = {"nextperiod": document.getElementById("lastperiod").value, "periodlength": document.getElementById("periodlength").value, "cyclelength": document.getElementById("cyclelength").value};
    add_row(myData);
    }
  function validate(){
    var enterPeriod = document.getElementById('lastperiod').value
    var periodLength = document.getElementById('periodlength').value;
    var cycleLength = document.getElementById('cyclelength').value;
    if(isNaN(periodLength) || isNaN(cycleLength)||periodLength < 0 || cycleLength < 10){
      alert("Please enter valid values");
    } else{
      addData();
    }
  }
  function delete_user() {
  const deleteOptions = {
        method: 'DELETE',
        headers: {
            "content-type": "application/json",
            'Authorization': 'Bearer my-token',
        },
    };
    fetch(delete_fetch, deleteOptions)
      .then(response => {
        // trap error response from Web API
        if (response.status !== 200) {
          window.location.reload();
          return;
        }
        // response contains valid result
        response.json().then(data => {
            console.log(data);
        })
    })
  }
  /*function delete_user(){
    const body = {
        nextperiod: document.getElementById('lastperiod').value,
        periodlength: document.getElementById('periodlength').value,
        cyclelength: document.getElementById('cyclelength').value,
    };
    const requestOptions = {
        method: 'DELETE',
        body: JSON.stringify(body),
        headers: {
            "content-type": "application/json",
            'Authorization': 'Bearer my-token',
        },
        mode: 'cors',
        cache: 'default',
        credentials: 'omit'
    };
    fetch(delete_fetch, requestOptions)
      .then(response => {
        // trap error response from Web API
        if (response.status !== 200) {
          const errorMsg = 'Database delete error: ' + response.status;
          console.log(errorMsg);
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.innerHTML = errorMsg;
          tr.removeChild(td);
          resultContainer.removeChild(tr);
          return;
        }
        // response contains valid result
        response.json().then(data => {
            console.log(data);
            //add a table row for the new/created userid
            delete_row(data);
        })
      })
        .catch(err => {
        console.error(err);
        const tr = document.createElement("tr");
        const td = document.createElement("td");
        td.innerHTML = err;
        tr.appendChild(td);
        resultContainer.appendChild(tr);
      });
    }
  function delete_row(data){
    const tr = document.createElement("tr");
    const nextperiod = document.createElement("td");
    const periodlength = document.createElement("td");
    const cyclelength = document.createElement("td");
    // obtain data that is specific to the API
    nextperiod.innerHTML = data.nextperiod;
    periodlength.innerHTML = data.periodlength;
    cyclelength.innerHTML = data.cyclelength;
    console.log(data)
    // add HTML to container
    tr.appendChild(nextperiod);
    tr.appendChild(periodlength);
    tr.appendChild(cyclelength);
    resultContainer.removeChild(tr);
  } */

</script>

{% include login.html %}
<div>
<button onclick="delete_user()">Delete All Period Records</button>
</div>

</body>



