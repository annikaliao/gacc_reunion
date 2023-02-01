<style>
#myBtn {
  display: none; /* Hidden by default */
  position: fixed; /* Fixed/sticky position */
  bottom: 20px; /* Place the button at the bottom of the page */
  right: 30px; /* Place the button 30px from the right */
  z-index: 99; /* Make sure it does not overlap */
  border: none; /* Remove borders */
  outline: none; /* Remove outline */
  background-color: white; /* Set a background color */
  color: DarkRed; /* Text color */
  cursor: pointer; /* Add a mouse pointer on hover */
  padding: 15px; /* Some padding */
  border-radius: 10px; /* Rounded corners */
  font-size: 18px; /* Increase font size */
}

#myBtn:hover {
  background-color: #555; /* Add a dark-grey background on hover */
}

* {
  box-sizing: border-box;
}

/* Create two equal columns that floats next to each other */
.column {
  float: left;
  width: 50%;
  padding: 10px;
  height: 300px; /* Should be removed. Only for demonstration */
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}
 input {
  color: white;
}  
table, tr {
  border:1px solid black;
}
</style>
<body>
<form>
<p>What are your symptoms:</p>

<input type="checkbox" id = "chk1" name="symptoms" value="trouble_sleeping"><font color="#FFFFFF"> Trouble Sleeping</font>
<br>
<input type="checkbox" id = "chk2" name="symptoms" value="acne" style="color: white"><font color="#FFFFFF"> Acne</font>
<br>
<input type="checkbox" id = "chk3" name="symptoms" value="joint_pain" style="color: white"><font color="#FFFFFF"> Joint Pain</font>
<br>
<input type="checkbox" id = "chk4" name="symptoms" value="lower_back_pain" style="color: white"><font color="#FFFFFF"> Lower Back Pain</font> 
<br>
<input type="checkbox" id = "chk5" name="symptoms" value="fatigue" style="color: white"><font color="#FFFFFF"> Fatigue</font> 
<br>
<input type="checkbox" id = "chk6" name="symptoms" value="bloating" style="color: white"><font color="#FFFFFF"> Bloating</font> 
<br>
<input type="checkbox" id = "chk7" name="symptoms" value="Abdominal_Cramps" style="color: white"><font color="#FFFFFF"> Abdominal Cramps</font> 
<br>
<input type="checkbox" id = "chk8" name="symptoms" value="headaches" style="color: white"><font color="#FFFFFF"> Headaches</font> 
<br>
<input type="checkbox" id = "chk9" name="symptoms" value="tender_breasts" style="color: white"><font color="#FFFFFF"> Tender Breasts</font> 
<br>
<input type="checkbox" id = "chk10" name="symptoms" value="muscle_aches" style="color: white"><font color="#FFFFFF"> Muscle Aches</font> 
<br>
<input type="checkbox" id = "chk11" name="symptoms" value="diarrhea_or_constipation" style="color: white"><font color="#FFFFFF"> Diarrhea or Constipation</font> 
</form>

<button type="button" onclick ="fDisplay()" style = "color: white"><font color="#000000"> See Remedies To:</font></button>


<br><a id = "s1" href="#Trouble_Sleeping">Trouble Sleeping</a>
<br><a id = "s2" href="#Acne">Acne</a>
<br><a id = "s3" href="#Joint_Pain">Joint Pain</a>
<br><a id = "s4" href="#Lower_Back_Pain">Lower Back Pain</a>
<br><a id = "s5" href="#Fatigue">Fatigue</a>
<br><a id = "s6" href="#Bloating">Bloating</a>
<br><a id = "s7" href="#Abdominal_Cramps">Abdominal Cramps</a>
<br><a id = "s8" href="#Headaches">Headaches</a>
<br><a id = "s9" href="#Tender_Breasts">Tender Breasts</a>
<br><a id = "s10" href="#Muscle_Aches">Muscle Aches</a>
<br><a id = "s11" href="#Diarrhea_or_Constipation">Diarrhea or Constipation</a>

<button onclick="topFunction()" id="myBtn" title="Go to top">Top</button>
<script>
fHide();
    function fHide()
   {
    for (var i =1; i <12;i++){
      document.getElementById("s"+ i).style.visibility = "hidden";
      }
   } 
   function fDisplay()
   {
    for (var i =1; i <12;i++)
      if (document.getElementById("chk"+ i).checked==true){
        document.getElementById("s"+ i).style.visibility = "";
      }
    else{
        document.getElementById("s"+ i).style.visibility = "hidden";
      }
   }
let mybutton = document.getElementById("myBtn");
window.onscroll = function() {scrollFunction()};
function scrollFunction() {
  if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
    mybutton.style.display = "block";
  } else {
    mybutton.style.display = "none";
  }
}
function topFunction() {
  document.body.scrollTop = 0; 
  document.documentElement.scrollTop = 0; 
}
</script>

<p>To better take care of yourself during your period, keep in mind the symptoms you may face and know when you should go see a doctor. <p>

<div class="row">
  <div class="column">
    <h2><a id="Trouble_Sleeping">Trouble Sleeping</a></h2>
    <p>- heating pad<br>
    - hot tea/water<br>
    - maintain a healthy and balanced diet<br>
    - cut down on alcohol and caffeine</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Acne">Acne</a></h2>
    <p>- don't touch your face<br>
    - salicylic acid<br>
    - birth control(consult a doctor)<br>
    - drink a sufficient amount of water<br>
    acne is normal, so don't feel too bad about having it:)</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Joint_Pain">Joint Pain</a></h2>
    <p>Make sure you are not deficient in:<br>
    - Vitamin D<br>
    - Magnesium<br>
    but, if immediate relief is needed, magnesium gel or pain medication could help as well.</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Lower_Back_Pain">Lower Back pain</a></h2>
    <p>- heating pad<br>
    - hot shower or bath<br>
    - mild exercise/ stretching<br>
    - massage
    <p>
  <div class="column">
    <h2></h2>
    <p></p>

<div class="row">
  <div class="column">
    <h2><a id="Fatigue">Fatigue</a></h2>
    <p>- increase iron in your diet<br>
    - drink more water<br>
    - make sure you're getting a good night of sleep</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Bloating">Bloating</a></h2>
    <p>- eat more whole foods<br>
    - exercise regularly<br>
    - birth control (consult a doctor)</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Abdominal_Cramps">Abdominal Cramps</a></h2>
    <p>- heating pad<br>
    - herbal tea<br>
    - pain medication<br>
    - yoga<br>
    - increase magnesium intake<br>
    - birth control(consult doctor)<br>
    if severe, go to the doctor to see if it might be:<br>
      - endometriosis<br>
      - uterine fibrosis<br>
    etc.</p>
  </div>
  <div class="column" >
    <h2></h2>
    <p></p>
  </div>
</div>
<br>
<br>
<br>
<br>
<div class="row">
  <div class="column">
    <h2><a id="Headaches">Headaches</a></h2>
    <p>- pain medication
    - ice on forehead of neck<br>
    - acupuncture<br>
    - massage<br>
    - hot tea or water<br>
    - magnesium</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2><a id="Tender_Breasts">Tender Breasts</a></h2>
    <p>- apply warm or cold compress<br>
    - wear a comfortable bra<br>
    - limit caffeine intake<br>
    if severe, go to doctor to check if everything is ok</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2><a id="Muscle_Aches">Muscle Aches</a></h2>
    <p>- exercise<br>
    - have a balanced diet<br>
    - get a good amount of sleep</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2><a id="Diarrhea_or_Constipation">Diarrhea or Constipation</a></h2>
    <p>- have a fiber dense diet<br>
    - drink water<br>
    - avoid sugar and caffeine</p>
  </div>
  <div class="column">
    <h2></h2>
    <p></p>
  </div>
</div>