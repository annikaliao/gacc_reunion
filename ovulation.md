<p> Ovulation is the process in which a mature egg is released from the ovary. After it's released, the egg moves down the fallopian tube and stays there for 12 to 24 hours, where it can be fertilized. This period of time usually occurs 12-14 days before your next period and typically lasts 6 days. </p>

<head>
    <link rel="stylesheet" href="style.css">
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

/* Add media queries for smaller screens */
@media screen and (max-width:720px) {
  .weekdays li, .days li {width: 13.1%;}
}

@media screen and (max-width: 420px) {
  .weekdays li, .days li {width: 12.5%;}
  .days li .active {padding: 2px;}
}

@media screen and (max-width: 290px) {
  .weekdays li, .days li {width: 12.2%;}
}
</style>

</head>
<br>
<body>
    <ul id="unordered">
       
   </ul>
   
  <script src="code.js"></script>

<p style="font-size: 30px; color: darkred;">Next Ovulation:</p>
<p style="font-size: 15px; color: darkred;">Make sure you put your info into the cycle tracker!</p>
<table>
    <tr>
      <td>
        <span id="year1"></span>
        <span id="month1"></span>
        <span id="date1"></span>
      </td>
      <td>
        <p style="text-align: center; color: darkred; font-weight:bolder; font-size: 20px;">&#x2964;</p>
      </td>
      <td>
        <span id="year2"></span>
        <span id="month2"></span>
        <span id="date2"></span>
      </td>
    </tr>
  </table>

<script>
function printOvulation() {
	  const x = document.getElementById("lastPeriod").value;
		var y = document.getElementById("cycleLength").value;
    const z = document.getElementById("periodLength").value;
		var resDate = new Date();
		resDate.setDate(resDate.getDate()+parseInt(y));
		document.getElementById("year1").innerHTML = resDate.getUTCFullYear() + " /" ;
		document.getElementById("month1").innerHTML = resDate.getUTCMonth()+1 + " /";
    document.getElementById("year2").innerHTML = resDate.getUTCFullYear() + " /" ;
		document.getElementById("month2").innerHTML = resDate.getUTCMonth()+1 + " /";
		document.getElementById("date1").innerHTML = resDate.getUTCDate() + z - 13;
    document.getElementById("date2").innerHTML = resDate.getUTCDate() + z - 7;
    }
</script>

<table>
  <thead>
  <tr>
    <th>Start Ovulation Month</th>
    <th>Start Ovulation Day</th>
  </tr>
  </thead>
  <tbody id="ovulation">
    <!-- javascript generated data -->
  </tbody>
</table>

<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("ovulation");
  // prepare URL's to allow easy switch from deployment and localhost
  const url = "http://flowhealth.duckdns.org/api/periods/ov"
  const create_fetch = url + '/create';
  const read_fetch = url;

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
        ovulation: document.getElementById("nextovulation").value,
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
            console.log(data[row]);
            add_row(data[row]);
        })
    })
  }

  function add_row(data) {
    const tr = document.createElement("tr");
    const ovulation = document.createElement("td");
  

    // obtain data that is specific to the API
    ovulation.innerHTML = data;  
    console.log(data)

    // add HTML to container
	  tr.appendChild(ovulation);

    resultContainer.appendChild(tr);
  }

</script>