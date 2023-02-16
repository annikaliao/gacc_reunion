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

<script>
  var post= document.getElementById("post");
post.addEventListener("click", function(){
    var commentBoxValue= document.getElementById("comment-box").value;
    var li = document.createElement("li");
    var text = document.createTextNode(commentBoxValue);
    li.appendChild(text);
    document.getElementById("unordered").appendChild(li); 
});
</script>
<script>
    function openComment() {
        document.getElementById("comment").style.display = "block";
    }
    function closeComment() {
        document.getElementById("comment").style.display = "none";
    }