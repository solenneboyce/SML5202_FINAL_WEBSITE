<h1>Exercise - remplissez les trous!</h1>
<br>
<h2>Remplissez les blancs pour compléter l'expression idiomatique.</h2>
<br>
<style type="text/css">
<!-- 

.instrC{
color:gray;
font-weight:bold;
}

.wordbox{
border:solid gray 2px;
margin:10px auto;
padding:3px 5px;
line-height:1.5;
font-weight:bold;
color:gray;
padding:4px 10px;
border-radius:15px;
-moz-border-radius:15px;
-webkit-border-radius:15px;
-o-border-radius:15px;
box-shadow:2px 2px 7px #333;
-moz-box-shadow:2px 2px 7px #333;
-webkit-box-shadow:2px 2px 7px #333;
-o-box-shadow:2px 2px 7px #333;
text-align:center;
}

.optionWord{
color:gray;
font-weight:bold;
}

.optionWord a{
color:gray;
text-decoration:none;
}

.optionWord a:hover{
color:black;
text-decoration:none;
}

.tdNumC{
padding:0 7px 0 0px;
color:gray;
font-weight:bold;
vertical-align:top;
}

.buttonC{
background:gray;
color:white;
padding:2px 3px;
font-weight:bold;
-moz-border-radius:5px;
-webkit-border-radius:5px;
-o-border-radius:5px;
-moz-box-shadow:1px 1px 5px #333;
-webkit-box-shadow:1px 1px 5px #333;
-o-box-shadow:1px 1px 5px #333;
margin:0 2px;
}

.textBoxC{
border:none;
border-bottom:1px dotted gray;
}


 -->
</style>

<div id="wordBox" class="wordbox" style="margin:10px 0;"><span class="optionWord">lapin</span> &nbsp; · &nbsp;<span class="optionWord">salades</span> &nbsp; · &nbsp;<span class="optionWord">râteau</span> &nbsp; · &nbsp;<span class="optionWord">pied</span> &nbsp; · &nbsp;<span class="optionWord">vieux</span> &nbsp; · &nbsp;<span class="optionWord">chandelle</span> &nbsp; · &nbsp;<span class="optionWord">diable</span> &nbsp; · &nbsp;<span class="optionWord">cheval</span> &nbsp; · &nbsp;<span class="optionWord">gueule</span> &nbsp; · &nbsp;<span class="optionWord">cheveux</span> &nbsp; </div>

<div style="font-family:arial;font-size:16px;"><table style="line-height:1.5;font-size:16;"><tbody>

<tr><td class="tdNumC">1.</td><td>Tirer le <input style="width:60;" class="textBoxC" type="text" id="ex0AnsBox0">  par la queue </td></tr>

<tr><td class="tdNumC">2.</td><td>Poser un <input style="width:60;" class="textBoxC" type="text" id="ex0AnsBox1">  à quelqu’un </td></tr>

<tr><td class="tdNumC">3.</td><td>Tenir la <input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox2">  </td></tr>

<tr><td class="tdNumC">4.</td><td>Prendre un coup de <input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox3">  </td></tr>

<tr><td class="tdNumC">5.</td><td>Se prendre un <input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox4">  </td></tr>

<tr><td class="tdNumC">6.</td><td>Être à <input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox5">  sur quelque chose </td></tr>

<tr><td class="tdNumC">7.</td><td>Tiré par les <input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox6">  </td></tr>

<tr><td class="tdNumC">8.</td><td>Avoir la <input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox7">  de bois </td></tr>

<tr><td class="tdNumC">9.</td><td>Raconter des <input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox8">  </td></tr>

<tr><td class="tdNumC">10.</td><td>Faire quelque chose d’arrache-<input style="width:90;" class="textBoxC" type="text" id="ex0AnsBox9">  </td></tr></tbody></table></div>

<div style="margin:10px 0;">
<input type="button" class="buttonC" value="Check" onclick="checkAnsBoxAnswers(0)">
<input type="button" class="buttonC" value="Show" onclick="showAnsBoxAnswers(0)">
<input type="button" class="buttonC" value="Clear" onclick="clearAnsBoxAnswers(0)">
 <span id="messageArea0">
</span>
</div>


<script type="text/javascript">
<!--

var clickedWord=""
var ansA=[]
ansA[0]=["diable","lapin","chandelle","vieux","râteau","cheval","cheveux","gueule","salades","pied"]

function checkAnsBoxAnswers(exNum){ 
  var ca=0
  for(var c=0;c<ansA[exNum].length;c++){
    var guess=doSpaces(exNum,c)
    var ans=doAnswers(guess,ansA[exNum][c])
    if(ans=="yes"){
      document.getElementById("ex"+exNum+"AnsBox"+c).style.color="green"
      document.getElementById("ex"+exNum+"AnsBox"+c).style.fontWeight="bold"
      ca++
    }
    else{
      document.getElementById("ex"+exNum+"AnsBox"+c).style.color="red" 
    } 
  }
  showScore(exNum,ca) 
}

function checkAnsBoxInvisibleAnswersScore(exNum){
  var ca=0
  for(var c=0;c<ansA[exNum].length;c++){
    var guess = document.getElementById("ex"+exNum+"AnsBox"+c).value;
    var ans=doAnswers(guess,ansA[exNum][c])
    if(ans=="yes"){
      document.getElementById("ex"+exNum+"TickBox"+c).innerHTML=getInvisibleAnswersSign(1)
      ca++
    }
    else if(guess==""){
      document.getElementById("ex"+exNum+"TickBox"+c).innerHTML=getInvisibleAnswersSign(3)
    }
    else{
      document.getElementById("ex"+exNum+"TickBox"+c).innerHTML=getInvisibleAnswersSign(2)
    }
  }
  showScore(exNum,ca) 
}
function doAnswers(guess,ans){
  if(guess==ans){
    txt="yes"
  }
  else{
    txt="no"
  }
  return txt
}


function getInvisibleAnswersSign(x){
  if(x==1){
    var txt='<span style="color:green;font-weight:bold;">Y</span>'
  }
  else if(x==2){ 
    var txt='<span style="font-size: 100%;color:red;font-weight:bold;">X</span>'
  }
  else if(x==3){ 
    var txt='<span style="font-size: 100%;color:orange;font-weight:bold;">?</span>'
  }
  return txt  
}


function showScore(exNum,ca){
  var qlen=ansA[exNum].length
  var pc=ca/qlen*100
  pc=Math.round(pc)
  var txt="<span class='instrC'>You have scored "+pc+" percent ( "+ca+" / "+qlen+" )</span>"
  document.getElementById("messageArea"+exNum).innerHTML=txt
}


function doSpaces(exNum,qNum){
  var txt=document.getElementById("ex"+exNum+"AnsBox"+qNum).value
  if(txt.charAt(txt.length-1)==" "){
    txt=txt.slice(0,txt.length-1)
    document.getElementById("ex"+exNum+"AnsBox"+qNum).value=txt
  }
  return txt
}

function showAnsBoxAnswers(exNum){
  for(var c=0;c<ansA[exNum].length;c++){
  if(document.getElementById("ex"+exNum+"AnsBox"+c).value==ansA[exNum][c]){
    document.getElementById("ex"+exNum+"AnsBox"+c).style.color="green"
    document.getElementById("ex"+exNum+"AnsBox"+c).style.fontWeight="bold"
  }
  else{
    document.getElementById("ex"+exNum+"AnsBox"+c).value=ansA[exNum][c]
    document.getElementById("ex"+exNum+"AnsBox"+c).style.color="red"
    document.getElementById("ex"+exNum+"AnsBox"+c).style.fontWeight="bold"
    }
  }
}
function clearAnsBoxAnswers(exNum){
  for(var c=0;c<ansA[exNum].length;c++){
  document.getElementById("ex"+exNum+"AnsBox"+c).value=""
  document.getElementById("ex"+exNum+"AnsBox"+c).style.color="black"
  document.getElementById("ex"+exNum+"AnsBox"+c).style.fontWeight="normal"
  }
  clearMessageArea(exNum)
}


function clearAnsBoxInvisibleAnswers(exNum){
  for(var c=0;c<ansA[exNum].length;c++){
    document.getElementById("ex"+exNum+"AnsBox"+c).value=""
    document.getElementById("ex"+exNum+"AnsBox"+c).style.color="black"
    document.getElementById("ex"+exNum+"AnsBox"+c).style.fontWeight="normal"
    document.getElementById("ex"+exNum+"TickBox"+c).innerHTML=""
  }
  clearMessageArea(exNum)
}

function clearMessageArea(exNum){
  document.getElementById("messageArea"+exNum).innerHTML=""
}
// -->
</script>
