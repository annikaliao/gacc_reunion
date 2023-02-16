<head>
<style>
.none {
  display: none;
}
span {
<<<<<<< HEAD
=======
  color: dark red;
>>>>>>> 3f160589d10c4b0ecb1b99750d2fb637819db077
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
  background-color: pink;
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
      <tr id="input">
        <td><input type="date" id="lastPeriod" required></td>
        <td><input type="number" id="periodLength" step="1" min="1" max="10" placeholder="1-10" required/></td>
        <td><input type="number" id="cycleLength" step="1" min="10" max="50" placeholder="10-50" required/></td>
      </tr>
      <tr>
        <td></td>
        <td>
          <button class="track" type="button" onclick="printDate()">
            TRACK
          </button>
        </td>
      </tr>
    </table>
  </form>
</div>
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
    <tr>
      <td>
        <span id="nextperiod2"></span>
      </td>
    </tr>
  </table>
  <br>
  <span class="unhealthy" id="unhealthy"></span>
</div>
<script>
	function printDate() {
	  const x = document.getElementById("lastPeriod").value;
		var y = document.getElementById("cycleLength").value;
    const z = document.getElementById("periodLength").value;
		var resDate = new Date(x);
		resDate.setDate(resDate.getDate() + parseInt(y));
		var year = resDate.getUTCFullYear();
    var month = resDate.getUTCMonth() + 1;
    var startdate = resDate.getUTCDate();
    document.getElementById("nextperiod").innerHTML = month + "/" + startdate + "/" + year;
    var enddate = resDate.getUTCDate() + parseInt(z);
    document.getElementById("nextperiodend").innerHTML = month + "/" + enddate + "/" + year;
    //startdate = enddate + parseInt(y);
    //document.getElementById("nextperiod2").innerHTML = startdate;
    if(parseInt(z) <= 2) {
      document.getElementById("unhealthy").innerHTML = "NOTICE: Your period is abnormally short. This may be a sign of some health concerns.   <a href=\"https://www.everydayhealth.com/pms/short-periods.aspx#:~:text=A%20short%20menstrual%20period%20might,even%20a%20serious%20medical%20problem.\">Learn More</a>" ;
    }
  }
</script>
<table>
  <thead>
  <tr>
    <th>Period</th>
  </tr>
  </thead>
  <tbody id="period">
    <!-- javascript generated data -->
  </tbody>
</table>
<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("period");
  // prepare URL's to allow easy switch from deployment and localhost
  //const url = "http://localhost:8086/api/users"
  const url = "http://172.31.22.127:8087/api/periods"
  const create_fetch = url + '/create';
  const read_fetch = url + '/';
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
    //Validate Password (must be 6-20 characters in len)
    //verifyPassword("click");
    const body = {
        period: document.getElementById("startdate").value,
    };
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
            //add a table row for the new/created userid
            add_row(data);
        })
    })
  }
  function add_row(data) {
    const tr = document.createElement("tr");
    const period = document.createElement("td"); 
    // obtain data that is specific to the API
    period.innerHTML = data.period; 
    // add HTML to container
    tr.appendChild(period);
    resultContainer.appendChild(tr);
  }

</script>
<br>
  <h1 style="text-align: center; color: darkred;" >&#65086;</h1>
<br>

{% include login.html %}

<button action="javascript:" onclick="openForm()">
  <p style="color: darkred;">Get reminders through phone or email!</p>
</button>

</body>