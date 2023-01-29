<head>
<style>
* {
  box-sizing: border-box;
  }
ul {
  list-style-type: none;
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
  padding: 20px;
  width: 33.3%;
  text-align: center;
  color: darkred;
  font-size: 20px;
}
.tracker {
  background-color: pink;
}
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
  padding: 20px 0;
  background: #eee;
  margin: 0;
}
.days li {
  list-style-type: none;
  display: inline-block;
  width: 13.6%;
  text-align: center;
  margin-bottom: 10px;
  font-size:12px;
  color: #777;
}
.days li .active {
  padding: 10px;
  border-radius: 50%;
  background: darkred;
  color: white;
  font-weight: bold;
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
<body>

<h1>Cycle Tracker</h1>

<div>
  <form class="tracker">
    <table align="center">
      <tr id="q">
        <td>When was the first day of your last period?</td>
        <td>How many days did it last?</td>
        <td>How long is your usual menstrual cycle?</td>
      </tr>
      <tr id="input">
        <td><input type="date" id="lastPeriod" required></td>
        <td><input type="number" id="periodLength" step="1" min="1" max="10" required/></td>
        <td><input type="number" id="cycleLength" step="1" min="10" max="50" required/></td>
      </tr>
      <tr>
        <td></td>
        <td>
          <button class="track" onclick="printdate()">
            TRACK
          </button>
        </td>
        <td></td>
      </tr>
    </table>
  </form>
</div>
<p id="d"></p>
<script>
  var cycleLenght = "cycleLength"
  document.getElementById("cycleLength").value = cycleLength;
  let d = new Date();
  d.setDate(d.getDate() + input);
  function printdate() {
    document.getElementById("d").innerHTML = d;
  }
</script>

<br>
  <h1 style="text-align: center; color: darkred;" >&#65086;</h1>
<br>

<div class="month">      
  <ul>
    <li class="prev">&#10094;</li>
    <li class="next">&#10095;</li>
    <li style="text-align: center;">
     January<br>
      <span style="font-size:18px">2023</span>
    </li>
  </ul>
</div>

<ul class="weekdays">
  <li>Su</li>
  <li>Mo</li>
  <li>Tu</li>
  <li>We</li>
  <li>Th</li>
  <li>Fr</li>
  <li>Sa</li>
</ul>

<ul class="days">  
  <li>1</li>
  <li>2</li>
  <li>3</li>
  <li>4</li>
  <li>5</li>
  <li>6</li>
  <li>7</li>
  <li>8</li>
  <li>9</li>
  <li>10</li>
  <li>11</li>
  <li>12</li>
  <li>13</li>
  <li>14</li>
  <li>15</li>
  <li>16</li>
  <li>17</li>
  <li>18</li>
  <li>19</li>
  <li>20</li>
  <li>21</li>
  <li>22</li>
  <li>23</li>
  <li><span class="active">24</span></li>
  <li><span class="active">25</span></li>
  <li><span class="active">26</span></li>
  <li><span class="active">27</span></li>
  <li><span class="active">28</span></li>
  <li>29</li>
  <li>30</li>
  <li>31</li>
</ul>
<br>

<script>

</script>

{% include login.html %}

<button action="javascript:" onclick="openForm()">
  <p style="color: darkred;">Get reminders through phone or email!</p>
</button>

</body>