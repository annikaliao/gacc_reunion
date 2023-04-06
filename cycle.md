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
          <button class="track" type="button" onclick="printDate(document.getElementById('lastperiod').value, parseInt(document.getElementById('cyclelength').value), parseInt(document.getElementById('periodlength').value))">
            TRACK
          </button>
        </td>
      </tr>
    </table>
  </form>
</div>
<br>
<div class="date">
  <p style="font-size: 30px; color: darkred;">Next 3 Periods:</p>
  <table>
    <tr>
      <td>
        <span id="period1start"></span>
      </td>
      <td>
        <p style="text-align: center; color: darkred; font-weight:bolder; font-size: 20px;">&#x2964;</p>
      </td>
      <td>
        <span id="period1end"></span>
      </td>
    </tr>
    <tr>
      <td>
        <span id="period2start"></span>
      </td>
      <td>
        <p style="text-align: center; color: darkred; font-weight:bolder; font-size: 20px;">&#x2964;</p>
      </td>
      <td>
        <span id="period2end"></span>
      </td>
    </tr>
    <tr>
      <td>
        <span id="period3start"></span>
      </td>
      <td>
        <p style="text-align: center; color: darkred; font-weight:bolder; font-size: 20px;">&#x2964;</p>
      </td>
      <td>
        <span id="period3end"></span>
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
  function printDate(lastperiod, cyclelength, periodlength) {
    // get user inputs
    //var lastperiod = document.getElementById("lastperiod").value;
    //var cyclelength = parseInt(document.getElementById("cyclelength").value);
    //var periodlength = parseInt(document.getElementById("periodlength").value);
    // calculate date
    var resDate = new Date(lastperiod);
    for (let i = 1; i <= 3; i++) {
      resDate.setDate(resDate.getDate() + cyclelength);
      var year = resDate.getUTCFullYear();
      var month = resDate.getUTCMonth() + 1;
      var startdate = resDate.getUTCDate();
      // print dates onto site
      var periodstart = `${month}/${startdate}/${year}`;
      document.getElementById(`period${i}start`).innerHTML = periodstart;
      var enddate = resDate.getUTCDate() + periodlength - 1;
      var periodend = `${month}/${enddate}/${year}`
      document.getElementById(`period${i}end`).innerHTML = periodend
      resDate = new Date(periodstart)
      // conditional for if period has unhealthy schedule
      if(parseInt(periodlength) <= 2) {
        document.getElementById("unhealthy").innerHTML = "NOTICE: Your period is abnormally short. This may be a sign of some health concerns. <a href=\"https://www.everydayhealth.com/pms/short-periods.aspx#:~:text=A%20short%20menstrual%20period%20might,even%20a%20serious%20medical%20problem.\">Learn More</a>"
        } else {
        document.getElementById('unhealthy').innerHTML = "";
      } 
    }
  }
</script>

{% include login.html %}

</body>



