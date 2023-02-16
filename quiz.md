<style>
div.container h1 {
	padding: 20px;
	font-size: 50px;
	font-style: normal;
	text-align: center;
	font-weight: normal;
	text-transform: none;
	color: #ffffff;
	background-color: pink;
	}

div.container p {
	text-align: center;
	}


body {
  color: white;
  font-family: 'Lato', sans-serif;
  font-size: 14px;
}

[id=container] {
  width: 50 ;
  background: white;
  color: #000;
  margin: 20px auto;
  overflow: auto;
  padding: 2.6rem;
  border: 2px solid pink;
  border-radius: 10px
}

header {
  text-align: center;
  border-bottom: pink dashed 1px;
}

header h1 {
  margin: 0;
  padding: 0;
}

header p {
  padding: 0;
  margin-top: 5px;
  color: #000;
}

input[type="submit"] {
  background: pink;
  border: 0;
  color: #fff;
  padding: 10px 12px;
  cursor: pointer;
}

[id=results] {
  margin-top: 1rem;
}

[id=results] h3 {
  background: pink;
  padding: 10px;
  margin: 10px 0;
  color: #000;
}

 input[type='radio'] { 
     transform: scale(1.5); 

</style>

<div class="container" style="background-color: pink;">
	<h1>How much do you know about periods?</h1>
</div>



<div id="container">
	<header>
	</header>
	<section>
		<form name="quizForm" >
	<h3>1. What is the average age at which menstruation begins in North America?</h3>
		<input type="radio" name="q1" value="a" id="q1a"> 8 <br>
		<input type="radio" name="q1" value="b" id="q1b"> 10 <br>
		<input type="radio" name="q1" value="c" id="q1c"> 12 <br>
		<input type="radio" name="q1" value="d" id="q1d"> 14 <br>
	<h3>2. __________is the time when the woman is most fertile.</h3>
		<input type="radio" name="q2" value="a" id="q2a"> Ovulation<br>
		<input type="radio" name="q2" value="b" id="q2b"> Period<br>
		<input type="radio" name="q2" value="c" id="q2c"> Amenorrhea<br>
		<input type="radio" name="q2" value="d" id="q2d"> Pregnancy <br>
	<h3>3. How long is the average menstrual cycle?</h3>
		<input type="radio" name="q3" value="a" id="q3a"> 26 days<br>
		<input type="radio" name="q3" value="b" id="q3b"> 28 days <br>
		<input type="radio" name="q3" value="c" id="q3c"> 30 days<br>
		<input type="radio" name="q3" value="d" id="q3d"> 35 days<br>
	<h3>4. What is the most environmentally friendly period product?</h3>
		<input type="radio" name="q4" value="a" id="q4a"> Diva Cups<br>
		<input type="radio" name="q4" value="b" id="q4b"> Tampon<br>
		<input type="radio" name="q4" value="c" id="q4c"> Pad<br>
	<h3>5. When fully saturated, how much blood can a regular tampon or daytime pad hold?</h3>
		<input type="radio" name="q5" value="a" id="q5a"> 2 milliliters <br>
		<input type="radio" name="q5" value="b" id="q5b"> 5 milliliters <br>
		<input type="radio" name="q5" value="c" id="q5c"> 7 milliliters <br>
		<input type="radio" name="q5" value="d" id="q5d"> 10 milliliters <br>
	<h3>6. How many tablespoons of blood does the average person lose during a period?</h3>
		<input type="radio" name="q6" value="a" id="q6a"> 11-14 tablespoons<br>
		<input type="radio" name="q6" value="b" id="q6b"> 8-10 tablespoons <br>
		<input type="radio" name="q6" value="c" id="q6c"> 5-7 tablespoons<br>
		<input type="radio" name="q6" value="d" id="q6d"> 2-4 tablespoons <br>
	<h3>7. From first period to menopause, how many periods do women and people who menstruate have on average in their lifetime?</h3>
		<input type="radio" name="q7" value="a" id="q7a"> Around 200<br>
		<input type="radio" name="q7" value="b" id="q7b"> Around 350<br>
		<input type="radio" name="q7" value="c" id="q7c"> Around 400<br>
		<input type="radio" name="q7" value="d" id="q7d"> Around 450<br>
	<h3>8. The first menstrual flow is called ... </h3>
		<input type="radio" name="q8" value="a" id="q8a"> Mjolnir<br>
		<input type="radio" name="q8" value="b" id="q8b"> Menarche<br>
		<input type="radio" name="q8" value="c" id="q8c"> Menopause<br>
		<input type="radio" name="q8" value="d" id="q8d"> Menses<br>
	<h3>9. What layer of the uterus is shredded during menstruation?</h3>
		<input type="radio" name="q9" value="a" id="q9a"> Perimetrium<br>
		<input type="radio" name="q9" value="b" id="q9b"> Epimetrium<br>
		<input type="radio" name="q9" value="c" id="q9c"> Endometrium<br>
		<input type="radio" name="q9" value="d" id="q9d"> Cervix<br>
	<h3>10. Is it possible to get pregnant during your period.</h3>
		<input type="radio" name="q10" value="a" id="q10a"> Yes<br>
		<input type="radio" name="q10" value="b" id="q10b"> No<br>
		<input type="radio" name="q10" value="c" id="q10c"> Maybe<br>

<div id="container">
		<p>Please enter your name to save your score:</p>
		<input type="name" name = "name" placeholder="Enter your name">
		<br>
		<br>
		<input type="submit" value="Submit Answers">
		<div id="results"></div>
	
</div>

<table>
  <thead>
  <tr>
    <th>Name</th>
    <th>Score</th>
  </tr>
  </thead>
  <tbody id="result1">
    <!-- javascript generated data -->
  </tbody>
</table>

<form action="javascript:create_user()">
    <p><label>
		Name:
        <input type="text" name="name" id="name" required>
    </label></p> 
    Score:
        <input type="text" name="uid" id="uid" required>
    <p>
        <button>Create</button>
    </p>
</form>


<script>
  var formElement = document.forms['quizForm'];

formElement.onsubmit = function submitAnswers(){
	var total = 10;
	var score = 0;
	
	// Get User Input
	var q1 = document.forms["quizForm"]["q1"].value,
	    q2 = document.forms["quizForm"]["q2"].value,
	    q3 = document.forms["quizForm"]["q3"].value,
	    q4 = document.forms["quizForm"]["q4"].value,
	    q5 = document.forms["quizForm"]["q5"].value;
		q6 = document.forms["quizForm"]["q6"].value;
		q7 = document.forms["quizForm"]["q7"].value;
		q8 = document.forms["quizForm"]["q8"].value;
		q9 = document.forms["quizForm"]["q9"].value;
		q10 = document.forms["quizForm"]["q10"].value;
		name = document.forms["quizForm"]["name"].value;
	
	// Validation
	for(i = 1; i <= total;i++){
		if(eval('q'+i) === null || eval('q'+i) === ''){
			// alert('You missed question '+ i);
			return false;
		}
	}
	
	// Set Correct Answers
	var answers = ["c","a","b","a","c","d","d","b","c","a"];
	
	// Check Answers
	for(i = 1; i <= total;i++){
		if(eval('q'+i) === answers[i - 1]){
			score++;
		}
	}
	
	// Display Results
	var results = document.getElementById('results');
	results.innerHTML = 'You scored <span>'+score+'</span> out of <span>'+total+'</span></h3>';
	
	return false;

	console.log(name)
	console.log(results)
}
  
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("result1");
  // prepare URL's to allow easy switch from deployment and localhost
  const url = "http://192.168.1.225:8087/api/scores"
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
      },
    };

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

 
  function create_user(){
    //Validate Password (must be 6-20 characters in len)
    //verifyPassword("click");
    const body = {
        uid: document.getElementById("uid").value,
        name: document.getElementById("name").value,
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
            add_row(data);
        })
    })
  }

  function add_row(data) {
    const tr = document.createElement("tr");
    const name = document.createElement("td");
	const uid = document.createElement("td");
  

    // obtain data that is specific to the API
    uid.innerHTML = data.uid; 
    name.innerHTML = data.name; 

    // add HTML to container
	tr.appendChild(name);
    tr.appendChild(uid);

    resultContainer.appendChild(tr);
  }

</script>