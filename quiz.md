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
	background-color: #297;
	color: #fff;
	border: 0px;
	border-radius: 3px;
	padding: 20px;
	cursor: pointer;
	margin-bottom: 20px;
}
#submit:hover{
	background-color: #3a8;
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

<body>
<div id="quiz"></div>
<button id="submit">Get Results</button>
<div id="results"></div>
</body>