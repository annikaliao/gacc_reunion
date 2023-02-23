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
  width: 100%;
  padding: 10px;
  height: 300px; 
}

.row:after {
  content: "";
  display: table;
  clear: both;
}

<!-- commentbox -->
#comment-box, #post {
    border: none;
    border-radius: 5px;
}

body {
  color: darkred;
}
input {
  color: darkred;
}  
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 5px; /* 5px rounded corners */
}

/* Add rounded corners to the top left and the top right corner of the image */
img {
  border-radius: 5px 5px 0 0;
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
<p><b>Add A Comment! What has Worked For You?</b></p>
<p>What Symptom Are You Addressing?</p>
<input type="text" id="symptoms" placeholder="symptom">
<!-- button id="symptom">Enter</button-->
<p>What Remedies Work For You? What Other Remedies or Products do you Recommend?</p>
<input type="text" id="comment-box" placeholder="your comment">
<button id="post" onclick="addData();">Post</button>
<p id="unordered"></p>
<script src="code.js"></script>
<form>
<table>
  <thead>
  <tr>
    <th style="width:20%">Symptom</th>
    <th style="width:80%">Comment</th>
  </tr>
  </thead>
  <tbody id="comment">
    <!-- javascript generated data -->
  </tbody>
</table>
<hr>
<p id = "whatSymptoms"><b>What are your symptoms:</b></p>

<input type="checkbox" id = "chk1" name="symptoms" value="trouble_sleeping"><font color="#990000"> Trouble Sleeping</font>
<br>
<input type="checkbox" id = "chk2" name="symptoms" value="acne" style="color: white"><font color="#990000"> Acne</font>
<br>
<input type="checkbox" id = "chk3" name="symptoms" value="joint_pain" style="color: white"><font color="#990000"> Joint Pain</font>
<br>
<input type="checkbox" id = "chk4" name="symptoms" value="lower_back_pain" style="color: white"><font color="#990000"> Lower Back Pain</font> 
<br>
<input type="checkbox" id = "chk5" name="symptoms" value="fatigue" style="color: white"><font color="#990000"> Fatigue</font> 
<br>
<input type="checkbox" id = "chk6" name="symptoms" value="bloating" style="color: white"><font color="#990000"> Bloating</font> 
<br>
<input type="checkbox" id = "chk7" name="symptoms" value="Abdominal_Cramps" style="color: white"><font color="#990000"> Abdominal Cramps</font> 
<br>
<input type="checkbox" id = "chk8" name="symptoms" value="headaches" style="color: white"><font color="#990000"> Headaches</font> 
<br>
<input type="checkbox" id = "chk9" name="symptoms" value="tender_breasts" style="color: white"><font color="#990000"> Tender Breasts</font> 
<br>
<input type="checkbox" id = "chk10" name="symptoms" value="muscle_aches" style="color: white"><font color="#990000"> Muscle Aches</font> 
<br>
<input type="checkbox" id = "chk11" name="symptoms" value="diarrhea_or_constipation" style="color: white"><font color="#990000"> Diarrhea or Constipation</font> 
</form>

<button type="button" onclick ="fDisplay()" style = "color: white"><font color="#000000"> See Remedies To:</font></button>
<hr>
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
<hr>
<button onclick="topFunction()" id="myBtn" title="Go to top">Top</button>
<script>
var post= document.getElementById("symptom");
post.addEventListener("click", function(){
    var symptomsValue= document.getElementById("symptoms").value;
    var li = document.createElement("span");
    var text = document.createTextNode(symptomsValue);
    li.appendChild(text);
    document.getElementById("unordered").appendChild(li); 
});
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

<div class="row">
  <div class="column">
    <h2><a id="Trouble_Sleeping">Trouble Sleeping</a></h2>
    <ul>
    <li>heating pad</li>
    <li>hot tea/water</li>
    <li>maintain a healthy and balanced diet</li>
    <li>cut down on alcohol and caffeine</li>
    </ul>
  </div>
<div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/81fPpqynQ2L._AC_SY355_.jpg" alt="Heating Pad" style="width:50%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a></b></h4>
    <p>$25.47</p>
  </div>
</div>
    <li><a href="https://thesleepdoctor.com/women/how-to-sleep-better-during-period/"><b>How To Sleep Better On Your Period</b></a></li>
  </div>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div class="row">
  <div class="column">
    <h2><a id="Acne">Acne</a></h2>
  <ul>
  <li>don't touch your face</li>
  <li>salicylic acid</li>
  <li>birth control(consult a doctor)</li>
  <li>drink a sufficient amount of water</li>
  </ul>
  acne is normal, so don't feel too bad about having it:)
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <p><b>Non-Prescription Products for Acne</b></p>
      <div class="card">
  <img src="https://www.sephora.com/productimages/sku/s2458669-main-zoom.jpg?imwidth=315" style="width:50%">
  <div class="container">
    <h4><b><a href="https://www.sephora.com/product/innbeauty-project-pimple-paste-overnight-blemish-drying-paste-P471039?om_mmc=aff-linkshare-redirect-tv2R4u9rImY&c3ch=Linkshare&c3nid=tv2R4u9rImY&affid=tv2R4u9rImY-Pnax7uqtyTYhOoMcoAQyMQ&ranEAID=tv2R4u9rImY&ranMID=2417&ranSiteID=tv2R4u9rImY-Pnax7uqtyTYhOoMcoAQyMQ&ranLinkID=10-1&browserdefault=true&correlationId=746a40da-6b90-459c-bfa6-6ade91bd3947">Pimple Paste Overnight Blemish Drying Paste</a></b></h4>
    <p>$15.00</p>
  </div>
</div>
    <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/71PKFdvUWjL._SY355_.jpg">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/dp/B07L1PHSY9/?language=en_US&cstrackid=08f5968e-6772-4d25-ba94-34baafbea509&tag=galderma_differin_csus-20">Differin Gel</a></b></h4>
    <p>$14.99</p>
  </div>
</div>
  <div class="card">
  <img src="https://www.sephora.com/productimages/sku/s2425080-main-zoom.jpg?imwidth=315">
  <div class="container">
    <h4><b><a href="https://www.sephora.com/product/the-inkey-list-c-50-blemish-night-treatment-P469544?om_mmc=aff-linkshare-redirect-tv2R4u9rImY&c3ch=Linkshare&c3nid=tv2R4u9rImY&affid=tv2R4u9rImY-Cmu3VbYMnlxURlzJnKodgg&ranEAID=tv2R4u9rImY&ranMID=2417&ranSiteID=tv2R4u9rImY-Cmu3VbYMnlxURlzJnKodgg&ranLinkID=10-1&browserdefault=true&correlationId=084b11f5-fb46-4081-b7e9-40e4ec33542b"><br>C-50 Blemish Night Treatment<br></a></b></h4>
    <p>$15.99</p>
  </div>
</div>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/61NCz9l8C+L._SY355_.jpg">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/Mighty-Patch-Hydrocolloid-Absorbing-count/dp/B074PVTPBW?&linkCode=ll1&tag=best-acne-treatment-update-20&linkId=63f92e54bb84227034d2420fed232bb2&language=en_US&ref_=as_li_ss_tl&ascsubtag=c7810558-ae69-4d40-9b13-5288002d6f50&correlationId=c7810558-ae69-4d40-9b13-5288002d6f50"><br>Mighty Patch Original from Hero Cosmetics<br></a></b></h4>
    <p>$12.99</p>
  </div>
</div>
    <ul>
    <li><a href="https://www.mayoclinic.org/diseases-conditions/acne/in-depth/acne-treatments/art-20045814"><b>Skincare Ingredients for Acne</b></a></li>
    </ul>
  </div>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div class="row">
  <div class="column">
    <h2><a id="Joint_Pain">Joint Pain</a></h2>
    Make sure you are not deficient in:
    <ul>
    <li>Vitamin D</li>
    <li>Magnesium</li>
    </ul>
    but, if immediate relief is needed, magnesium gel or pain medication could help as well.
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/71135CDfkXL._AC_SX679_.jpg" alt="Vitamin D" style="width:30%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/Nature-Made-Strength-Softgels-Packaging/dp/B0828JGTXB/ref=sr_1_6?keywords=vitamin+D&qid=1675657135&s=hpc&sr=1-6">Nature Made Extra Strength Vitamin D3 5000 IU (125 mcg)</a></b></h4>
    <p>$28.58</p>
  </div>
</div>
<div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/71mwsjajGnL._AC_SX679_.jpg" alt="Magnesium" style="width:30%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/Nature-Made-Potency-Magnesium-Softgels/dp/B07CDWT8WM/ref=sr_1_5?crid=3A23V8L7FQYP8&keywords=magnesium&qid=1675657214&s=hpc&sprefix=Magne%2Chpc%2C182&sr=1-5">Nature Made Extra Strength Magnesium Oxide 400 mg</a></b></h4>
    <p>$9.89</p>
  </div>
</div>
<div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/61olCy3UdfL._AC_SX466_.jpg" alt="Naomi" style="width:30%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/NAOMI-Activated-Vitamin-Balanced-Function/dp/B08L3YC3X9/ref=sr_1_1_sspa?crid=17CK9OWRMXU1P&keywords=magnesium+and+vitamin+d&qid=1675657261&s=hpc&sprefix=magnesium+and+vitamin%2Chpc%2C185&sr=1-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyTlhYMUcyTzhYMVkyJmVuY3J5cHRlZElkPUEwNDIyODEyRFZIMENMTTgyTkFDJmVuY3J5cHRlZEFkSWQ9QTA3MDA5NTNONE1TSUJVU0RaUk4md2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl">NAOMI Activated Vitamin D, Vitamin D3 5000 IU with Magnesium Supplement</a></b></h4>
    <p>$19.99</p>
  </div>
</div>
</div>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div class="row">
  <div class="column">
    <h2><a id="Lower_Back_Pain">Lower Back pain</a></h2>
    <ul>
    <li>heating pad</li>
    <li>hot shower or bath</li>
    <li>mild exercise/ stretching</li>
    <li>massage</li>
    </ul>
  </div>
    <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/81fPpqynQ2L._AC_SY355_.jpg" alt="Heating Pad" style="width:50%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a></b></h4>
    <p>$25.47</p>
  </div>
</div>
<div class="card">
  <img src="https://i.ytimg.com/vi/eZdwBl1yu14/hqdefault.jpg?sqp=-oaymwEcCNACELwBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLARxKOlUjk00W6PwRP-jn9dB-oihQ" alt="Yoga" style="width:50%">
  <div class="container">
    <h4><b><a href="https://www.bing.com/videos/search?q=period+exercise&&view=detail&mid=C215C7B58F0D380AF5D3C215C7B58F0D380AF5D3&&FORM=VRDGAR&ru=%2Fvideos%2Fsearch%3Fq%3Dperiod%2Bexercise%26FORM%3DHDRSC3">Gentle Period Yoga</a></b></h4>
  </div>
</div>
</div>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div class="row">
  <div class="column">
    <h2><a id="Fatigue">Fatigue</a></h2>
    <ul>
    <li>increase iron in your diet</li>
    <li>drink more water</li>
    <li>make sure you're getting a good night of sleep</li>
    </ul>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/71edZ4s6YvL.__AC_SX300_SY300_QL70_FMwebp_.jpg" alt="Heating Pad" style="width:30%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/Nature-Made-Ferrous-Sulfate-Tablets/dp/B003PGJLRO/ref=sr_1_4?crid=21W7PCJE8UCPZ&keywords=iron+supplement&qid=1675659803&s=hpc&sprefix=iron+%2Chpc%2C196&sr=1-4">Nature Made Iron 65 mg (325 mg Ferrous Sulfate) Tablets</a></b></h4>
    <p>$5.57</p>
  </div>
</div>
  </div>
</div>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<div class="row">
  <div class="column">
    <h2><a id="Bloating">Bloating</a></h2>
    <ul>
    <li>eat more whole foods</li>
    <li>exercise regularly</li>
    <li>birth control (consult a doctor)</li>
    </ul>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <ul>
    <li><a href="https://www.everydayhealth.com/diet-nutrition/whole-foods-diet/"><b>Guide to Whole Foods</b></a></li>
    </ul>
  </div>
</div>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<div class="row">
  <div class="column">
    <h2><a id="Abdominal_Cramps">Abdominal Cramps</a></h2>
    <ul>
    <li>heating pad</li>
    <li>herbal tea</li>
    <li>pain medication</li>
    <li>yoga</li>
    <li>increase magnesium intake</li>
    <li>birth control(consult doctor)</li>
    </ul>
    if severe, go to the doctor to see if it might be:
    <ul>
    <li>endometriosis</li>
    <li>uterine fibrosis</li>
    </ul>
    etc.
    </div>
  <div class="column" >
  <h2><font color="#8B0000">Products and Other Resources</font></h2>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/81fPpqynQ2L._AC_SY355_.jpg" alt="Heating Pad" style="width:50%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a></b></h4>
    <p>$25.47</p>
  </div>
</div>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/71mwsjajGnL._AC_SX679_.jpg" alt="Magnesium" style="width:30%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/Nature-Made-Potency-Magnesium-Softgels/dp/B07CDWT8WM/ref=sr_1_5?crid=3A23V8L7FQYP8&keywords=magnesium&qid=1675657214&s=hpc&sprefix=Magne%2Chpc%2C182&sr=1-5">Nature Made Extra Strength Magnesium Oxide 400 mg</a></b></h4>
    <p>$9.89</p>
  </div>
</div>
    <li><a href="https://www.healthline.com/nutrition/tea-for-cramps"><b>Guide to Herbal Teas</b></a></li>
    <br>
    <li><a href="https://www.mayoclinic.org/diseases-conditions/endometriosis/symptoms-causes/syc-20354656"><b>Endometriosis Symptoms and Causes</b></a></li>
    <br>
    <li><a href="https://www.mayoclinic.org/diseases-conditions/uterine-fibroids/symptoms-causes/syc-20354288"><b>Uterine Fibrosis Symptoms and Causes</b></a></li>
  </div>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div class="row">
  <div class="column">
    <h2><a id="Headaches">Headaches</a></h2>
    <ul>
    <li>pain medication</li>
    <li>ice on forehead or neck</li>
    <li>acupuncture</li>
    <li>massage</li>
    <li>hot tea or water</li>
    <li>magnesium</li>
    </ul>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/71mwsjajGnL._AC_SX679_.jpg" alt="Magnesium" style="width:30%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/Nature-Made-Potency-Magnesium-Softgels/dp/B07CDWT8WM/ref=sr_1_5?crid=3A23V8L7FQYP8&keywords=magnesium&qid=1675657214&s=hpc&sprefix=Magne%2Chpc%2C182&sr=1-5">Nature Made Extra Strength Magnesium Oxide 400 mg</a></b></h4>
    <p>$9.89</p>
  </div>
</div>
</div>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div class="row">
  <div class="column">
    <h2><a id="Tender_Breasts">Tender Breasts</a></h2>
    <ul>
    <li>apply warm or cold compress</li>
    <li>wear a comfortable bra</li>
    <li>limit caffeine intake</li>
    <br>
    if severe, go to doctor to check if everything is ok
    </ul>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
  <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/81fPpqynQ2L._AC_SY355_.jpg" alt="Heating Pad" style="width:50%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/GENIANI-Electric-Heating-Cramps-Relief/dp/B08MV3Z3GK/ref=sr_1_2_sspa?c=ts&keywords=Heating+Pads&qid=1675656453&s=hpc&sr=1-2-spons&ts_id=3763871&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEyWjZOVFVaUjI1Rlo5JmVuY3J5cHRlZElkPUEwNjI4NTI2MTVXTlhUTVNSSDlFSyZlbmNyeXB0ZWRBZElkPUEwNDY0ODA4MllKOUVQQUpBQVlRSCZ3aWRnZXROYW1lPXNwX2F0ZiZhY3Rpb249Y2xpY2tSZWRpcmVjdCZkb05vdExvZ0NsaWNrPXRydWU=">Heating Pad</a></b></h4>
    <p>$25.47</p>
  </div>
</div>
  </div>
</div>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<div class="row">
  <div class="column">
    <h2><a id="Muscle_Aches">Muscle Aches</a></h2>
    <ul>
    <li>exercise</li>
    <li>have a balanced diet</li>
    <li>get a good amount of sleep</li>
    </ul>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <ul>
    <li><a href="https://www.healthline.com/health/muscle-aches"><b>More on muscle Aches</b></a></li>
    <br>
    </ul>
  </div>
</div>
<br>
<br>
<br>
<br>
<br>
<div class="row">
  <div class="column">
    <h2><a id="Diarrhea_or_Constipation">Diarrhea or Constipation</a></h2>
    <ul>
    <li>have a fiber dense diet</li>
    <li>drink water</li>
    <li>avoid sugar and caffeine</li>
    </ul>
  </div>
  <div class="column">
    <h2><font color="#8B0000">Products and Other Resources</font></h2>
    <div class="card">
  <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T2/images/I/71IEuMw4WVL._AC_SX679_.jpg" alt="Heating Pad" style="width:20%">
  <div class="container">
    <h4><b><a href="https://www.amazon.com/Benefiber-Prebiotic-Supplement-Digestive-Taste-Free/dp/B01978FIZC/ref=sr_1_5?crid=2NH2N9FLFAB5I&keywords=fiber+supplement&qid=1675661200&s=hpc&sprefix=fiber%2Chpc%2C391&sr=1-5">Benefiber Daily Prebiotic Fiber Supplement Powder for Digestive Health</a></b></h4>
    <p>$25.47</p>
  </div>
</div>
  </div>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("comment");
  // prepare URL's to allow easy switch from deployment and localhost
  const url = "http://flowhealth.duckdns.org/api/symptom"
  const create_fetch = url + '/create';
  const read_fetch = url + '/';
  // Load users on page entry
  read_users();
  //alert(create_fetch);
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
      }
    }
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
  function create_user(sym,com){
    //Validate Password (must be 6-20 characters in len)
    //verifyPassword("click");
    const body = {
        //symptom: document.getElementById("symptoms").value,
        //comment: document.getElementById("comment-box").value,
        symptom: sym,
        comment: com,
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
        // trap error response from Web API
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
            console.log(data);
            //add a table row for the new/created userid
            //add_row(data);
        })
    })
  }
  function add_row(data) {
    //alert(data.symptom);
    const tr = document.createElement("tr");
    const symptom = document.createElement("td");
	  const comment = document.createElement("td");
    // obtain data that is specific to the API
    symptom.innerHTML = data.symptom; 
    comment.innerHTML = data.comment; 
    // add HTML to container
	tr.appendChild(symptom);
    tr.appendChild(comment);
    resultContainer.appendChild(tr);
    //alert("before post");
    // save database
    create_user(data.symptom,data.comment);
    //alert("after post");
  }



  function addData(){
    //alert("hell0");
    if(document.getElementById("symptoms").value&&document.getElementById("comment-box").value){
      myObj = { "symptom":document.getElementById("symptoms").value, "comment":document.getElementById("comment-box").value};
      //alert(document.getElementById("symptoms").value);
      //alert(document.getElementById("comment-box").value);

      add_row(myObj);
      //alert("do something!");
    }

  }

  </script>

