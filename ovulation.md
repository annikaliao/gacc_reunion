<p> Ovulation is the process in which a mature egg is released from the ovary. After it's released, the egg moves down the fallopian tube and stays there for 12 to 24 hours, where it can be fertilized. This period of time usually occurs 12-14 days before your next period and typically lasts 6 days. </p>

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Comment Box</title>
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

<button action="javascript:" onclick="openComment()" id="comment">
  <p style="color: darkred;">Leave a Comment!</p>
</button>

</head>
<br>
<body>
    <input type="text" id="comment-box" placeholder="Enter comment">
    <button id="post">Enter</button>
    <ul id="unordered">
       
   </ul>
   
  <script src="code.js"></script>
  
<div class="month">      
  <ul>
    <li class="prev">&#10094;</li>
    <li class="next">&#10095;</li>
    <li>
     February<br>
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
  <li style="color:red">6</li>
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
  <li><span class="active">23</span></li>
  <li><span class="active">24</span></li>
  <li><span class="active">25</span></li>
  <li><span class="active">26</span></li>
  <li><span class="active">27</span></li>
  <li><span class="active">28</span></li>
  <li>29</li>
  <li>30</li>
  <li>31</li>
</ul>

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