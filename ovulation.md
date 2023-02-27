<p> Ovulation is the process in which a mature egg is released from the ovary. After it's released, the egg moves down the fallopian tube and stays there for 12 to 24 hours, where it can be fertilized. This period of time usually occurs 12-14 days before your next period and typically lasts 6 days. </p>

<head>
    <!--<link rel="stylesheet" href="style.css">-->
<style>
* {box-sizing: border-box;}
ul {list-style-type: none;}

.month {
  padding: 60px 25px;
  width: 100%;
  background: pink;
  text-align: center;
}

.month ul {
  margin: 0;
  padding: 0;
}

.month ul li {
  color: white;
  font-size: 20px;
  text-transform: uppercase;
  letter-spacing: 3px;
}

.month .prev {
  float: left;
  padding-top: 10px;
}

.month .next {
  float: right;
  padding-top: 10px;
}

.weekdays {
  margin: 0;
  padding: 10px 0;
  background-color: #ddd;
}

.weekdays li {
  display: inline-block;
  width: 13.6%;
  color: #d19696;
  text-align: center;
}

.days {
  padding: 10px 0;
  background: #eee;
  margin: 0;
}

.days li {
  list-style-type: none;
  display: inline-block;
  width: 13.6%;
  text-align: center;
  margin-bottom: 5px;
  font-size:12px;
  color: #777;
}

.days li .active {
  padding: 6px;
  background: #ADD8E6;s
}

red{
  color: #8B0000;
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
</style>

</head>

<div>
  <form class="tracker">
    <table align="center" style="border:none;">
      <tr id="q">
        <td>Once you get your next period date from the period tracker, enter the date here:</td>
        <td>How many days does your period usually last?</td>
        <td>How long is your usual menstrual cycle?</td>
      </tr>
      <tr id="input">
        <td><input type="date" id="perioddate" required></td>
        <td><input type="text" id="periodcycle"/></td>
        <td><input type="text" id="menscycle" required onchange="validate()"/></td>
      </tr>
      <tr>
        <td></td>
        <td>
          <button class="track" type="button" onclick="printDate(); addData()">
            TRACK
          </button>
        </td>
      </tr>
    </table>
  </form>
</div>
<br>

<p style="font-size: 25px; color: darkred;">Next Ovulation:</p>
  <table>
    <tr>
      <td>
        <span id="nextovulation"></span>
      </td>
      <td>
        <p style="text-align: center; color: darkred; font-weight:bolder; font-size: 20px;">&#x2964;</p>
      </td>
      <td>
        <span id="nextovulationend"></span>
      </td>
    </tr>
  </table>

<br>

<script>
  function printDate() {
    const x = document.getElementById("perioddate").value;
    var y = document.getElementById("periodcycle").value;
    const z = document.getElementById("menscycle").value;
    var resDate = new Date(x);
    resDate.setDate(resDate.getDate() + parseInt(y));
    var year = resDate.getUTCFullYear();
    var month = resDate.getUTCMonth() + 1;
    var startdate = resDate.getUTCDate() - 13;
    const ovulationstart = `${month}/${startdate}/${year}`;
    document.getElementById("nextovulation").innerHTML = ovulationstart
    var enddate = resDate.getUTCDate() - 7;
    const ovulationend = `${month}/${enddate}/${year}`
    document.getElementById("nextovulationend").innerHTML = ovulationend
  }
</script>

<table>
  <thead>
  <tr>
    <th>Period Date</th>
    <th>Period Length</th>
    <th>Menstrual Cycle</th>
  </tr>
  </thead>
  <tbody id="ovulationresult">
    <!-- javascript generated data -->
  </tbody>
</table>

<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("ovulationresult");
  // prepare URL's to allow easy switch from deployment and localhost
  //const url = "http://localhost:8087/api/ovulation"
  const url = "https://flowhealth.duckdns.org/api/ovulation"
  const create_fetch = url + '/create';
  const read_fetch = url + '/';
  const del_fetch = url + '/delete';

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

  function create_user(periodD, periodC, mensC){
    const body = {
        perioddate: periodD,
        periodcycle: periodC,
        menscycle: mensC
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
          //for (let row in data) {
            console.log(data);
            add_row(data);
        //}
    })
  })

  function add_row(data) {
    const tr = document.createElement("tr");
    const perioddate = document.createElement("td");
    const periodcycle = document.createElement("td");
    const menscycle = document.createElement("td");
    // obtain data that is specific to the API
    perioddate.innerHTML = data.perioddate;
    periodcycle.innerHTML = data.periodcycle;
    menscycle.innerHTML = data.menscycle;   
    console.log(data)
    // add HTML to container
	  tr.appendChild(perioddate);
    tr.appendChild(periodcycle);
    tr.appendChild(menscycle);

    resultContainer.appendChild(tr);
  }

  function addData(){
    if(document.getElementById("perioddate").value&&document.getElementById("periodcycle").value&&document.getElementById("menscycle").value)
      myData = {"perioddate": document.getElementById("perioddate").value, "periodcycle": document.getElementById("periodcycle").value, "menscycle": document.getElementById("menscycle").value};
    add_row(myData);
    //alert("before post");
    create_user(myData.perioddate, myData.periodcycle, myData.menscycle);
    //alert("after post");
    }

  function delete_record() {
    const delOptions = {
        method: 'DELETE',
        headers: {
            "content-type": "application/json",
            'Authorization': 'Bearer my-token',
        },
    };

    // URL for DELETE API
    // Fetch API call to the database to create a new user
    fetch(del_fetch, delOptions)
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


function validate(){
  var userperiodl = document.getElementById('periodcycle').value;
  var usermensc = document.getElementById('menscycle').value;
  if(isNaN(userperiodl) || isNaN(usermensc)){
    alert("Make sure you are entering a number");
  }else{
    create_user();
  }
}
</script>

<form action="javascript:delete_record()">
  <button>Delete Records</button>
</form>