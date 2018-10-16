# SurveyApp-Backend
Code for a simple survey app backend logic

Request urls detail:
QA Table:
Question-AnswerOptions-CorrectAnswer
create table t_survey_qa (question varchar2(100), answer varchar2(100), correctind number(1));

Survey Table:
Question-CheckedAnswer-SurveyNbr
create table t_survey_r (question varchar2(100), checkedAnswer varchar2(100), surveyNbr number(1));



addQA:
url: http://localhost:9000/addQA
RequestBody:

{
	"question":"what is your name",
	"ansCInd":{
	"manish":1,
	"anish":0
	}
}

Delete a question: method: DELETE
url: http://localhost:9000/deleteQA/{question}

Read all questions: GET
URL: http://localhost:9001/getAllQuestions

Read a question with all answers: GET
http://localhost:9001/getQuestionByName/{question}

Submit  a survey: POST
URL: http://localhost:9000/submitSurvey

Request Body:
[{
	"question":"what is your name",
	"surveyNbr":2,
	"answers":[	"manish","anish","animesh"]
},{
	"question":"what is your age",
	"surveyNbr":2,
	"answers":[	"30", "20"]
}]

Percentage distribution of answer for a question:
URL: http://localhost:9001/responsePercentQues/{question}


Modify Question:
url: http://localhost:9000/modifyQuestion
RequestBody:
{
	"question":"what is your name",
	"ansCInd":{
	"manish":1,
	"anish":0,
	"animesh":0
	}
}

