<style>
* {
  box-sizing: border-box;
}

/* Create three equal columns that floats next to each other */
.column {
  float: left;
  width: 33.33%;
  padding: 10px;
  height: 300px; /* Should be removed. Only for demonstration */
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

h2 {
  color: black;
}
</style>

<body>
<img src="https://cdn.discordapp.com/attachments/908884737135874048/1075326522489045013/logo.gif">

<h2 class="center" style="color: dark red">Learn about periods!</h2>

<div class="row">
  <div class="column" style="background-color:#FFB6C1;">
    <h2>Fertility</h2>
    <a href="https://www.reproductivefacts.org/news-and-publications/patient-fact-sheets-and-booklets/documents/fact-sheets-and-info-booklets/age-and-fertility/" style = "center" class="button"> Information from ARSM</a>
  </div>
  <div class="column" style="background-color:#FFB6C1;">
    <h2>Menstruation</h2>
    <a href="https://medlineplus.gov/menstruation.html" style = "center" class="button"> Information from MedlinePlus</a>
  </div>
  <div class="column" style="background-color:#FFB6C1;">
    <h2>Pregnancy</h2>
    <a href="https://www.plannedparenthood.org/learn/pregnancy" style = "center" class="button"> Information from Planned Parenthood</a>
  </div>
</div>

<br>

<div class="row">
  <div class="column" style="background-color:#FFB6C1;">
    <h2>Birth Control</h2>
    <a href="https://www.plannedparenthood.org/learn/birth-control" style = "center" class="button"> Information from Planned Parenthood</a>
  </div>
  <div class="column" style="background-color:#FFB6C1;">
    <h2>Issues and Controls</h2>
    <a href="https://my.clevelandclinic.org/health/diseases/14633-abnormal-menstruation-periods" style = "center" class="button"> Information from Cleveland Clinic</a>
  </div>
  <div class="column" style="background-color:#FFB6C1;">
    <h2>Postpartum</h2>
    <a href="https://www.mayoclinic.org/diseases-conditions/postpartum-depression/symptoms-causes/syc-20376617" style = "center" class="button"> Information from Mayo Clinic</a>
  </div>
</div>


