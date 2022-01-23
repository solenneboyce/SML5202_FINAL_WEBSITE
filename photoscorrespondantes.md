<h1>Page 3</h1>
<p>write your content in this file as you would normally</p>


<!DOCTYPE html>
02 <head>
03  <link href="main.css" rel="stylesheet" type="text/css"/>
04  <script src="jquery.min.js"></script>
05  <script src="source.js"></script>
06 </head>
07 <body>
08  <div id="activityTitle">English/Spanish Flashcards</div> 
09  <div id="cardArea"></div>
10  <div id="buttonArea"></div> 
11  </div>
12 </body>
13</html>

html, body {
02 margin: 0;
03 padding: 0;
04 -webkit-user-select: none; 
05 -moz-user-select: none; 
06 user-select: none; 
07} 
08@font-face {
09 font-family: Montserrat;
10 src: url('Montserrat-Medium.ttf');
11}
12#activityTitle{
13 text-align:center;
14 font-size:38px;
15 font-family:Montserrat,Arial;
16 margin-top:50px;
17}
18#cardArea{
19 width:300px;
20 height:200px;
21 margin:auto;
22 margin-top:80px;
23 border:3px solid #ABB7B7;
24 border-radius:5px;
25 position:relative;
26 overflow:hidden;
27}
28.card{
29 width:300px;
30 height:200px;
31 position:absolute;
32 text-align:center;
33 line-height:200px;
34 font-size:45px;
35 color:#efefef;
36 font-family:Montserrat,Arial;
37 cursor:pointer;
38}
39#nextButton{
40 width:80px;
41 text-align:center;
42 font-size:20px;
43 padding:10px;
44 cursor:pointer;
45 color:#efefef;
46 margin:auto;
47 margin-top:30px;
48 background-color:#019875;
49 border: 2px solid #1E824C;
50 border-radius:5px;
51 font-family:Montserrat,Arial;
52}
53#nextButton:hover{
54 opacity:.6;
55}
56#finalMessage{
57 text-align:center;
58 font-size:30px;
59 margin-top:30px;
60 font-family:Montserrat,Arial;
61}


{"questionlist":[
02 {"cardfront":"CAT",
03 "cardback":"GATO"
04 }, 
05 {"cardfront":"DOG",
06 "cardback":"PERRO"
07 }, 
08 {"cardfront":"HORSE",
09 "cardback":"CABALLO"
10 }, 
11 {"cardfront":"RABBIT",
12 "cardback":"CONEJO"
13 }, 
14 {"cardfront":"TIGER",
15 "cardback":"TIGRE"
16 }, 
17 {"cardfront":"KANGAROO",
18 "cardback":"CANGURO"
19 }
20]}


$(document).ready(function () { 
02 
03 var colorArray=["#019875","#1E8BC3","#D91E18","#D35400","#8E44AD","#C0392B"];
04 var cardState;
05 var currentQuestion=0;
06 var qbank=new Array;
07 
08 loadDB();
09 
10 function loadDB(){
11  $.getJSON("activity.json", function(data) { 
12   for(i=0;i<data.questionlist.length;i++){ 
13    qbank[i]=[];
14    qbank[i][0]=data.questionlist[i].cardfront;
15    qbank[i][1]=data.questionlist[i].cardback;
16   }//for 
17   beginActivity();
18  })//gtjson
19 }//loadDB
20
21 function beginActivity(){
22  cardState=0;
23  var color1=colorArray[Math.floor(Math.random()*colorArray.length)];
24  $("#cardArea").empty();
25  $("#cardArea").append('<div id="card1" class="card">' + qbank[currentQuestion][0] + '</div>');
26  $("#cardArea").append('<div id="card2" class="card">' + qbank[currentQuestion][1] + '</div>');
27  $("#card1").css("background-color",color1);
28  $("#card2").css("background-color","#34495E");
29  $("#card2").css("top","200px");
30  $("#cardArea").on("click",function(){
31   if(cardState!=1){
32    cardState=1;
33    //togglePosition();
34    $("#card1").animate({top: "-=200"}, 150, function() {cardState=0;togglePosition();});
35    $("#card2").animate({top: "-=200"}, 150, function() {togglePosition2();});
36   }//if
37  });//click function
38  currentQuestion++;
39  $("#buttonArea").empty();
40  $("#buttonArea").append('<div id="nextButton">NEXT</div>');
41  $("#nextButton").on("click",function(){
42   if(currentQuestion<qbank.length){beginActivity();}
43   else{displayFinalMessage();}
44  });//click function
45 }//beginactivity
46
47 function togglePosition(){
48  if($("#card1").position().top==-200){$("#card1").css("top","200px");};
49 }//toggle
50
51 function togglePosition2(){
52  if($("#card2").position().top==-200){$("#card2").css("top","200px");};
53 }//toggle2
54
55 function displayFinalMessage(){
56  $("#buttonArea").empty();
57  $("#cardArea").empty();
58  $("#cardArea").append('<div id="finalMessage">You have finished the activity.</div>'); 
59 }//final message
60
61});

