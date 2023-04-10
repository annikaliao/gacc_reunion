<style>
/* remedies */
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
/* comment box */
#comment-box, #symptoms, #post {
    border: none;
    border-radius: 5px 5px 0 0;
    background-color: #fadadd  
}
/* delete */
#x {
  border: none;
  border-radius: 5px 5px 0 0;
  background-color: white  
}
/* remedies */
#rem {
  border: none;
  border-radius: 5px 5px 0 0;
  background-color: #fadadd  
}
/* font color */
body {
  color: darkred;
}
input {
  color: darkred;
}  
/* products */
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 5px;
}
img {
  border-radius: 5px 5px 0 0;
}
#comment_section {
  border:1px solid darkred;
  border-radius: 5px 5px 0 0;
  background-color: #fadadd  
}
p1 {
  font-size: 50px;
}
</style>
<body>
<p1>Find Remedies for Your Period Symptoms</p1>
<p><b>Check off Your Symptoms and Discover New Remedies!</b></p>
<div>
  <table>
    <tr>
      <th style="width:500px">Symptoms</th>
      <th style="width:500px">Remedies</th>
    </tr>
    <tr>
      <td>
        <input type="checkbox" id = "chk1" onchange="fDisplay()"> Trouble Sleeping
        <br>
        <input type="checkbox" id = "chk2" name="symptoms" onclick="fDisplay()" style="color: white"> Acne
        <br>
        <input type="checkbox" id = "chk3" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Joint Pain</font>
        <br>
        <input type="checkbox" id = "chk4" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Lower Back Pain</font> 
        <br>
        <input type="checkbox" id = "chk5" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Fatigue</font> 
        <br>
        <input type="checkbox" id = "chk6" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Bloating</font> 
        <br>
        <input type="checkbox" id = "chk7" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Abdominal Cramps</font> 
        <br>
        <input type="checkbox" id = "chk8" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Headaches</font> 
        <br>
        <input type="checkbox" id = "chk9" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Tender Breasts</font> 
        <br>
        <input type="checkbox" id = "chk10" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Muscle Aches</font> 
        <br>
        <input type="checkbox" id = "chk11" name="symptoms" onclick="fDisplay()" style="color: white"><font color="#990000"> Diarrhea or Constipation</font> 
      </td>
      <td>
        <div id="remedies">Your Remedies</div>
      </td>
    </tr>
  </table>
</div>

<div class="row">
  <div class="column" id="rm1" hidden>
    <h2><a>Trouble Sleeping</a></h2>
      <ul>
        <li>heating pad</li>
        <li>hot tea/water</li>
        <li>maintain a healthy and balanced diet</li>
        <li>cut down on alcohol and caffeine</li>
      </ul>
  </div>
</div>

<div class="row">
  <div class="column" id="rm2" hidden>
    <h2><a>Acne</a></h2>
      <ul>
        <li>don't touch your face</li>
        <li>salicylic acid</li>
        <li>birth control(consult a doctor)</li>
        <li>drink a sufficient amount of water</li>
      </ul>
      <p>acne is normal, so don't feel too bad about having it:)</p>
  </div>
</div>

<div class="row">
  <div class="column" id="rm3" hidden>
    <h2><a>Joint Pain</a></h2>
      <p>Make sure you are not deficient in:</p>
      <ul>
        <li>Vitamin D</li>
        <li>Magnesium</li>
      </ul>
      <p>but, if immediate relief is needed, magnesium gel or pain medication could help as well.</p>
  </div>
</div>

<div class="row">
  <div class="column" id="rm4" hidden>
    <h2><a>Lower Back pain</a></h2>
      <ul>
        <li>heating pad</li>
        <li>hot shower or bath</li>
        <li>mild exercise/ stretching</li>
        <li>massage</li>
      </ul>
  </div>
</div>

<div class="row">
  <div class="column" id="rm5" hidden>
    <h2><a>Fatigue</a></h2>
      <ul>
        <li>increase iron in your diet</li>
        <li>drink more water</li>
        <li>make sure you're getting a good night of sleep</li>
      </ul>
  </div>
</div>

<div class="row">
  <div class="column" id="rm6" hidden>
    <h2><a>Bloating</a></h2>
      <ul>
        <li>eat more whole foods</li>
        <li>exercise regularly</li>
        <li>birth control (consult a doctor)</li>
      </ul>
  </div>
</div>

<div class="row">
  <div class="column" id="rm7" hidden>
    <h2><a>Abdominal Cramps</a></h2>
      <ul>
        <li>heating pad</li>
        <li>herbal tea</li>
        <li>pain medication</li>
        <li>yoga</li>
        <li>increase magnesium intake</li>
        <li>birth control(consult doctor)</li>
      </ul>
      <p>if severe, go to the doctor to see if it might be:</p>
      <ul>
        <li>endometriosis</li>
        <li>uterine fibrosis</li>
      </ul>
  </div>
</div>

<div class="row">
  <div class="column" id="rm8" hidden>
    <h2><a>Headaches</a></h2>
      <ul>
        <li>pain medication</li>
        <li>ice on forehead or neck</li>
        <li>acupuncture</li>
        <li>massage</li>
        <li>hot tea or water</li>
        <li>magnesium</li>
      </ul>
  </div>
</div>

<div class="row">
  <div class="column" id="rm9" hidden>
    <h2><a>Tender Breasts</a></h2>
      <ul>
        <li>apply warm or cold compress</li>
        <li>wear a comfortable bra</li>
        <li>limit caffeine intake</li>
      </ul>
      <br>
      <p>if severe, go to doctor to check if everything is ok</p>
  </div>
</div>

<div class="row">
  <div class="column" id="rm10" hidden>
    <h2><a>Muscle Aches</a></h2>
      <ul>
        <li>exercise</li>
        <li>have a balanced diet</li>
        <li>get a good amount of sleep</li>
      </ul>
  </div>
</div>

<div class="row">
  <div class="column" id="rm11" hidden>
    <h2><a>Diarrhea or Constipation</a></h2>
      <ul>
        <li>have a fiber dense diet</li>
        <li>drink water</li>
        <li>avoid sugar and caffeine</li>
      </ul>
  </div>
</div>
<!-- comment section -->
<p><b>Add A Comment! What has Worked For You?</b></p>
<p>What Symptom Are You Addressing?</p>
<input type="text" id="symptoms" placeholder="symptom">
<p>What Remedies Work For You? What Other Remedies or Products do you Recommend?</p>
<input type="text" id="comment-box" placeholder="your comment">
<!-- this button calls the addData function which adds the comment to the database and saves is-->
<button id="post" onclick="addData()">Post</button>
<form>
<!-- table of comments -->
<hr>
<h2><a id="divTable">Comments</a></h2>
<div id="divTable">
<table id="comment_table">
  <thead>
  <tr>
    <th style="width: 500px;">Symptom</th>
    <th style="width: 500px;">Comment</th>
  </tr>
  </thead>
  <tbody id="comment">
  </tbody>
</table>
</div>
<script>
  // this function hides all the links at first
  fHide();
  function fHide(count = 11) {
    for (var i = 1; i <= count; i++) {
      document.getElementById("rm" + i).style.visibility = "hidden";
    }
  }
// when this function is called, it will display the remedies to the symptoms that have been checked
  function fDisplay(count = 11){
    document.getElementById("remedies").innerHTML="";
    for (var i = 1; i <= count; i++) {
      if (document.getElementById("chk"+ i).checked==true){
        document.getElementById("remedies").innerHTML += document.getElementById("rm"+ i).innerHTML;
      }
    }
  }
// prepare HTML result container for new output
  const resultContainer = document.getElementById("comment");
  const url = "https://flowhealth.duckdns.org/api/symptom/"
  const create_fetch = url + '/create';
  const read_fetch = url + '/';
  // Load users on page entry
  read_users();
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
    //Validate Password (must be 2+ characters in len)
    const body = {
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
        })
    })
  }
  function add_row(data) {
    const tr = document.createElement("tr");
    const symptom = document.createElement("td");
	  const comment = document.createElement("td");
    const td_delete = document.createElement("td");
    // obtain data that is specific to the API
    symptom.innerHTML = data.symptom; 
    comment.innerHTML = data.comment;
    // add HTML to container
	tr.appendChild(symptom);
    tr.appendChild(comment);
    resultContainer.appendChild(tr);
    // save database
    create_user(data.symptom,data.comment);
  }
//this function adds the comment to the table
  function addData(){
    if(document.getElementById("symptoms").value&&document.getElementById("comment-box").value){
      myObj = { "symptom":document.getElementById("symptoms").value, "comment":document.getElementById("comment-box").value};
      add_row(myObj);
    }
  }
</script>

