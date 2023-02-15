<html>
<body>
<h1>How much do you know about your period?</h1>
<div id="quiz"></div>
<button id="submit">Get Results</button>
<div id="results"></div>
</body>

<style>
body{
	font-size: 20px;
	font-family: sans-serif;
	color: #333;
}
.question{
	font-weight: 600;
}
.answers {
    margin-bottom: 20px;
}
#submit{
	font-family: sans-serif;
	font-size: 20px;
	background-color: red;
	color: white;
	border: 0px;
	border-radius: 5px;
	padding: 20px;
	cursor: pointer;
	margin-bottom: 20px;
}
#submit:hover{
	background-color: pink;
}
</style>


<script>
var myQuestions = [
	{
		question: "1. Which of the following would be considered an abnormal length of time for a period to last?",
		answers: {
			a: '2 days',
			b: '5 days',
			c: '6 days'
		},
		correctAnswer: 'c'
	},
	{
		question: "2. __________is the time when the woman is most fertile.",
		answers: {
			a: 'Ovulation',
			b: 'Period',
			c: 'Amenorrhea'
		},
		correctAnswer: 'c'
	},
  {
		question: "3. How long is the average menstrual cycle?",
		answers: {
			a: '26 days',
			b: '28 days',
			c: '30 days'
		},
		correctAnswer: 'b'
	},
  {
		question: "4. What is the most environmentally friendly period product?",
		answers: {
			a: 'Diva cups',
			b: 'Tampons',
			c: 'Pads'
		},
		correctAnswer: 'a'
	},
  {
		question: "5. When fully saturated, how much blood can a regular tampon or daytime pad hold?",
		answers: {
			a: '2 milliliters',
			b: '5 milliliters',
			c: '7 milliliters'
		},
		correctAnswer: 'b'
	},
  {
		question: "6. How many tablespoons of blood does the average person lose during a period?",
		answers: {
			a: '2-4 tablespoons',
			b: '5-7 tablespoons',
			c: '8-10 tablespoons'
		},
		correctAnswer: 'a'
	},
  {
		question: "7. From first period to menopause, how many periods do women and people who menstruate have on average in their lifetime?",
		answers: {
			a: 'around 200',
			b: 'around 350',
			c: 'around 450'
		},
		correctAnswer: 'c'
	},
  {
		question: "8. The first menstrual flow is called ... ",
		answers: {
			a: 'Mjolnir',
			b: 'Menarche',
			c: 'Menopause'
		},
		correctAnswer: 'b'
	},
  {
		question: "9. What layer of the uterus is shredded during menstruation? ",
		answers: {
			a: 'Perimetrium',
			b: 'Epimetrium',
			c: 'Endometrium'
		},
		correctAnswer: 'c'
	},
  {
		question: "10. Is it possible to get pregnant during your period.",
		answers: {
			a: 'No',
			b: 'Yes',
			c: 'I dont know'
		},
		correctAnswer: 'b'
	},
];

var quizContainer = document.getElementById('quiz');
var resultsContainer = document.getElementById('results');
var submitButton = document.getElementById('submit');

generateQuiz(myQuestions, quizContainer, resultsContainer, submitButton);

function generateQuiz(questions, quizContainer, resultsContainer, submitButton){

	function showQuestions(questions, quizContainer){
		// we'll need a place to store the output and the answer choices
		var output = [];
		var answers;

		// for each question...
		for(var i=0; i<questions.length; i++){
			
			// first reset the list of answers
			answers = [];

			// for each available answer...
			for(letter in questions[i].answers){

				// ...add an html radio button
				answers.push(
					'<label>'
						+ '<input type="radio" name="question'+i+'" value="'+letter+'">'
						+ letter + ': '
						+ questions[i].answers[letter]
					+ '</label>'
				);
			}

			// add this question and its answers to the output
			output.push(
				'<div class="question">' + questions[i].question + '</div>'
				+ '<div class="answers">' + answers.join('') + '</div>'
			);
		}

		// finally combine our output list into one string of html and put it on the page
		quizContainer.innerHTML = output.join('');
	}


	function showResults(questions, quizContainer, resultsContainer){
		
		// gather answer containers from our quiz
		var answerContainers = quizContainer.querySelectorAll('.answers');
		
		// keep track of user's answers
		var userAnswer = '';
		var numCorrect = 0;
		
		// for each question...
		for(var i=0; i<questions.length; i++){

			// find selected answer
			userAnswer = (answerContainers[i].querySelector('input[name=question'+i+']:checked')||{}).value;
			
			// if answer is correct
			if(userAnswer===questions[i].correctAnswer){
				// add to the number of correct answers
				numCorrect++;
				
				// color the answers green
				answerContainers[i].style.color = 'lightgreen';
			}
			// if answer is wrong or blank
			else{
				// color the answers red
				answerContainers[i].style.color = 'red';
			}
		}

		// show number of correct answers out of total
		resultsContainer.innerHTML = numCorrect + ' out of ' + questions.length;
	}

	// show questions right away
	showQuestions(questions, quizContainer);
	
	// on submit, show results
	submitButton.onclick = function(){
		showResults(questions, quizContainer, resultsContainer);
	}


}
</script>

<form action="javascript:create_user()">
    <p><label>
        Name:
        <input style="color: black" type="text" name="name" id="name" required>
    </label></p>
</form>
<p>
	<button>Enter</button>
</p>



<table>
  <thead>
  <tr>
    <th>Score</th>
    <th>Name</th>
  </tr>
  </thead>
  <tbody id="result1">
    <!-- javascript generated data -->
  </tbody>
</table>

<p>Enter your score</p>

<form action="javascript:create_user()">
    <p><label>
        Score:
        <input type="text" name="uid" id="uid" required>
    </label></p>
    <p><label>
        Name:
        <input type="text" name="name" id="name" required>
    </label></p>
    <p>
        <button>Create</button>
    </p>
</form>

<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("result1");
  // prepare URL's to allow easy switch from deployment and localhost
  const url = "http://192.168.1.225:8086/api/scores"
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
    const uid = document.createElement("td");
    const name = document.createElement("td");
  

    // obtain data that is specific to the API
    uid.innerHTML = data.uid; 
    name.innerHTML = data.name; 

    // add HTML to container
    tr.appendChild(uid);
    tr.appendChild(name);

    resultContainer.appendChild(tr);
  }

</script>
