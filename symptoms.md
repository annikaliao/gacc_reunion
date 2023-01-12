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
<input type="checkbox" name="symptoms" id="sym1" value="trouble_sleeping" onclick="return ValidateSelection();">
<label for="sym1">Trouble Sleeping</label>
<br>
<input form="myForm" type="checkbox" name="symptoms" id="sym2"  value="acne" onclick="return ValidateSelection();"> 
<label for="sym2">Acne</label>
<br>
<input form="myForm" type="checkbox" name="symptoms" id="sym3"  value="joint_pain" onclick="return ValidateSelection();"> 
<label for="sym3">Joint Pain</label>
<br>
<input type="checkbox" name="symptoms" id="sym4" value="lower_back_pain" onclick="return ValidateSelection();"> 
<label for="sym4">Lower Back Pain</label>
<br>
<input type="checkbox" name="symptoms" id="sym5" value="fatigue" onclick="return ValidateSelection();"> 
<label for="sym4">Fatigue</label>
<br>
<input type="checkbox" name="symptoms" id="sym6" value="bloating" onclick="return ValidateSelection();"> 
<label for="sym4">Bloating</label>
<br>
<input type="checkbox" name="symptoms" id="sym7" value="abdominal pain" onclick="return ValidateSelection();">
<label for="sym4">Abdominal Pain</label>
<br>
<input type="checkbox" name="symptoms" id="sym8" value="headaches" onclick="return ValidateSelection();"> 
<label for="sym4">Headaches</label>
<br>
<input type="checkbox" name="symptoms" id="sym9" value="tender_breasts" onclick="return ValidateSelection();">
<label for="sym4">Tender Breasts</label>
<br>
<input type="checkbox" name="symptoms" id="sym10" value="muscle_aches" onclick="return ValidateSelection();">
<label for="sym4">Muscle Aches</label>
<br>
<input type="checkbox" name="symptoms" id="sym11" value="diarrhea_or_constipation" onclick="return ValidateSelection();">
<label for="sym4">Diarrhea or Constipation</label>
</form>

<p><input type="submit" value="Submit"></p>
    
<script type="text/javascript">  
   function ValidateSelection()  
   {  
       var check_box = document.getElementsByName("symptoms");  
       var CheckedItems = 0; 
       for(var i = 0; i < check_box.length; i++)  
       {  
           if(check_box[i].checked)  
               CheckedItems++;  
       }   
   }  
</script>

<p>To better take care of yourself during your period, keep in mind the symptoms you may face and know when you should go see a doctor. <p>

<div class="row">
  <div class="column">
    <h2>Trouble Sleeping</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2>Acne</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2>Joint Pain</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2>Lower back pain</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2>Fatigue</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2>Bloating</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2>Abdominal cramps</h2>
    <p>...</p>
  </div>
  <div class="column" >
    <h2>...</h2>
    <p>...</p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2>Headaches</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2>Tender breasts</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2>Muscle aches</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2>Diarrhea or constipation</h2>
    <p>...</p>
  </div>
  <div class="column">
    <h2>...</h2>
    <p>...</p>
  </div>
</div>
