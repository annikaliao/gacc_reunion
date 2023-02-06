<style>
#myBtn {
  display: none; 
  position: fixed; 
  bottom: 20px; 
  right: 30px; 
  z-index: 99; 
  border: none; 
  outline: none; 
  background-color: white; 
  color: DarkRed; 
  cursor: pointer; 
  padding: 15px; 
  border-radius: 10px; 
  font-size: 18px; 
}

#myBtn:hover {
  background-color: #555; 
}

* {
  box-sizing: border-box;
}

.column {
  float: left;
  width: 50%;
  padding: 10px;
  height: 300px; 
}

.row:after {
  content: "";
  display: table;
  clear: both;
}

 input {
  color: darkred;
}  

table, tr {
  border:1px solid black;
}
#comment-box, #post {
    border: none;
    border-radius: 5px;
}
body {
  color: darkred;
}
</style>
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Comment Box</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
<p>Add A Comment! What has Worked For You?</p>
<input type="text" id="comment-box" placeholder="Enter comment">
<button id="post">Post</button>
<ul id="unordered">
</ul>
<script src="code.js"></script>
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
var post= document.getElementById("post");
post.addEventListener("click", function(){
    var commentBoxValue= document.getElementById("comment-box").value;
    var li = document.createElement("li");
    var text = document.createTextNode(commentBoxValue);
    li.appendChild(text);
    document.getElementById("unordered").appendChild(li); 
});
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a>
    <br>
    -  <a href="https://thesleepdoctor.com/women/how-to-sleep-better-during-period/">How To Sleep Better On Your Period</a></p>
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.mayoclinic.org/diseases-conditions/acne/in-depth/acne-treatments/art-20045814">Skincare Ingredients for Acne</a>
    <br>
    -  <a href="https://www.healthline.com/health/skin/best-acne-treatment#our-picks">Skincare Products for Acne</a></p>
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/Nature-Made-Strength-Softgels-Packaging/dp/B0828JGTXB/ref=sr_1_6?keywords=vitamin+D&qid=1675657135&s=hpc&sr=1-6">Vitamin D Supplements</a>
    <br>
    -  <a href="https://www.amazon.com/Nature-Made-Potency-Magnesium-Softgels/dp/B07CDWT8WM/ref=sr_1_5?crid=3A23V8L7FQYP8&keywords=magnesium&qid=1675657214&s=hpc&sprefix=Magne%2Chpc%2C182&sr=1-5">Magnesium Supplements</a>
    <br>
    -  <a href="https://www.amazon.com/NAOMI-Activated-Vitamin-Balanced-Function/dp/B08L3YC3X9/ref=sr_1_1_sspa?crid=17CK9OWRMXU1P&keywords=magnesium+and+vitamin+d&qid=1675657261&s=hpc&sprefix=magnesium+and+vitamin%2Chpc%2C185&sr=1-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyTlhYMUcyTzhYMVkyJmVuY3J5cHRlZElkPUEwNDIyODEyRFZIMENMTTgyTkFDJmVuY3J5cHRlZEFkSWQ9QTA3MDA5NTNONE1TSUJVU0RaUk4md2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl">Magnesium and Vitamin D Supplements</a></p>
  </div>
</div>
<div class="row">
  <div class="column">
    <h2><a id="Lower_Back_Pain">Lower Back pain</a></h2>
    <p>- heating pad<br>
    - hot shower or bath<br>
    - mild exercise/ stretching<br>
    - massage</p>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a>
    <br>
    -  <a href="https://www.bing.com/videos/search?q=period+exercise&&view=detail&mid=C215C7B58F0D380AF5D3C215C7B58F0D380AF5D3&&FORM=VRDGAR&ru=%2Fvideos%2Fsearch%3Fq%3Dperiod%2Bexercise%26FORM%3DHDRSC3">Gentle Period Yoga</a></p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h2><a id="Fatigue">Fatigue</a></h2>
    <p>- increase iron in your diet<br>
    - drink more water<br>
    - make sure you're getting a good night of sleep</p>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/Nature-Made-Ferrous-Sulfate-Tablets/dp/B003PGJLRO/ref=sr_1_4?crid=21W7PCJE8UCPZ&keywords=iron+supplement&qid=1675659803&s=hpc&sprefix=iron+%2Chpc%2C196&sr=1-4">Iron Supplements</a>
    </p>
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.everydayhealth.com/diet-nutrition/whole-foods-diet/">Whole Foods</a></p>
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a>
    <br>
    -  <a href="https://www.healthline.com/nutrition/tea-for-cramps">Herbal Tea</a>
    <br>
    -  <a href="https://www.amazon.com/Nature-Made-Potency-Magnesium-Softgels/dp/B07CDWT8WM/ref=sr_1_5?crid=3A23V8L7FQYP8&keywords=magnesium&qid=1675657214&s=hpc&sprefix=Magne%2Chpc%2C182&sr=1-5">Magnesium Supplements</a>
    <br>
    -  <a href="https://www.mayoclinic.org/diseases-conditions/endometriosis/symptoms-causes/syc-20354656">Endometriosis Symptoms and Causes</a>
    <br>
    -  <a href="https://www.mayoclinic.org/diseases-conditions/uterine-fibroids/symptoms-causes/syc-20354288">Uterine Fibrosis Symptoms and Causes</a>
    <br></p>
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
    - ice on forehead or neck<br>
    - acupuncture<br>
    - massage<br>
    - hot tea or water<br>
    - magnesium</p>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/Nature-Made-Potency-Magnesium-Softgels/dp/B07CDWT8WM/ref=sr_1_5?crid=3A23V8L7FQYP8&keywords=magnesium&qid=1675657214&s=hpc&sprefix=Magne%2Chpc%2C182&sr=1-5">Magnesium Supplements</a>
    <br>
    </p>
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a>
    <br></p>
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.healthline.com/health/muscle-aches">More on muscle Aches</a>
    <br></p>
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
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p>-  <a href="https://www.amazon.com/Benefiber-Prebiotic-Supplement-Digestive-Taste-Free/dp/B01978FIZC/ref=sr_1_5?crid=2NH2N9FLFAB5I&keywords=fiber+supplement&qid=1675661200&s=hpc&sprefix=fiber%2Chpc%2C391&sr=1-5">Fiber Supplements</a>
    <br></p>
  </div>
</div>