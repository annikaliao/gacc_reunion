<style>
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
</style>
<body>
<form>
<p>What are your symptoms:</p>

<input type="checkbox" id = "chk1" name="symptoms" value="trouble_sleeping" onclick="fDisplay();"> Trouble Sleeping
<br>
<input type="checkbox" id = "chk2" name="symptoms" value="acne" onclick="fDisplay();"> Acne
<br>
<input type="checkbox" id = "chk3" name="symptoms" value="joint_pain" onclick="fDisplay();"> Joint Pain
<br>
<input type="checkbox" id = "chk4" name="symptoms" value="lower_back_pain" onclick="fDisplay();"> Lower Back Pain
<br>
<input type="checkbox" id = "chk5" name="symptoms" value="fatigue" onclick="fDisplay();"> Fatigue
<br>
<input type="checkbox" id = "chk6" name="symptoms" value="bloating" onclick="fDisplay();"> Bloating
<br>
<input type="checkbox" id = "chk7" name="symptoms" value="abdominal pain" onclick="fDisplay();"> Abdominal Pain
<br>
<input type="checkbox" id = "chk8" name="symptoms" value="headaches" onclick="fDisplay();"> Headaches 
<br>
<input type="checkbox" id = "chk9" name="symptoms" value="tender_breasts" onclick="fDisplay();"> Tender Breasts
<br>
<input type="checkbox" id = "chk10" name="symptoms" value="muscle_aches" onclick="fDisplay();"> Muscle Aches
<br>
<input type="checkbox" id = "chk11" name="symptoms" value="diarrhea_or_constipation" onclick="fDisplay();"> Diarrhea or Constipation
</form>

<button type="button" onclick ="fDisplay()">See Remedies</button>
<br><a id = "s1" href="#Trouble_Sleeping">Trouble Sleeping</a>
<br><a id = "s2" href="#Acne">Acne</a>
<br><a id = "s3" href="#Joint_Pain">Joint Pain</a>
<br><a id = "s4" href="#Lower_Back_Pain">Lower Back Pain</a>
<br><a id = "s5" href="#Fatigue">Fatigue</a>
<br><a id = "s6" href="#Bloating">Bloating</a>
<br><a id = "s7" href="#Abdominal_Pain">Abdominal Pain</a>
<br><a id = "s8" href="#Headaches">Headaches</a>
<br><a id = "s9" href="#Tender_Breasts">Tender Breasts</a>
<br><a id = "s10" href="#Muscle_Aches">Muscle Aches</a>
<br><a id = "s11" href="#Diarrhea_or_Constipation">Diarrhea or Constipation</a>

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
      document.getElementById =("s"+ i).style.visibility = "hidden";
      }
   }
</script>

<p>To better take care of yourself during your period, keep in mind the symptoms you may face and know when you should go see a doctor. <p>

<div class="row">
  <div class="column">
    <h2><a id="Trouble_Sleeping">Trouble Sleeping</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Acne">Acne</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Joint_Pain">Joint Pain</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Lower_Back_Pain">Lower Back pain</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Fatigue">Fatigue</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Bloating">Bloating</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Abdominal Cramps">Abdominal Cramps</a></h2>
    <p>...</p>
  </div>
  <div class="column" >
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Headaches">Headaches</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2><a id="Tender_Breasts">Tender Breasts</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2><a id="Muscle_Aches">Muscle Aches</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2><a id="Diarrhea or Constipation">Diarrhea or Constipation</a></h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
</body>