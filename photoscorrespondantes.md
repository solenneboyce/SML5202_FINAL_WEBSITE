<h1>Page 3</h1>
<p>write your content in this file as you would normally</p>



<body>
  <h1>Flashcards (JS)</h1><br><br>
  <h4 style="width:100%; text-align:center;margin-top:-50px;">check out the new hotkeys: L/R Arrow Keys for previous/next, Up/Down for front/back, Enter for adding a card, and Delete for clearing the deck (after a prompt)! </h4>
  <p id="front">
    <!-- term lives here   -->
  </p><br>
  <hr><br>
  <div id="back">
    <!-- definition lives here   -->
  </div><br>
  <div id ="activeCardButtons">
    <button id="prev" onclick="prevCard()">Previous Card
  </button>
  <button id="flip" type="button" value="Flip" onclick="flash()">
  Flip</button>
  <button id="next" onclick="nextCard()">Next Card
  </button>
  </div>
  <br>
  <br>
  <br>
  <div id="formContainer">
    <form id="cardForm">
      <input id="newTerm" type="text" placeholder="Add your own term or concept..." onKeyDown="if(event.keyCode==13) document.getElementById('newDef').focus()">
      <input id="newDef" type="text" placeholder="...give it a definition, then click the button to..." onKeyDown="if(event.keyCode==13) cardAdd()">
      <br>
      <input id="submit" type="button" value="add it to the deck!" onClick="cardAdd()">
      <br>
      <input id="clearDeck" type="button" value="Click HERE to clear the deck!" onClick="emptyDeck()">
    </form>
    <br>
  </div>
<select id="selectCards" style="display:none;">

</select>
  <div id="importExport">
    
	  <div id="import"> 
		  <h2 style="text-align:center;">Import</h2>
		  <p>choose a local file containing a <code>.json</code> array of cards, and then click below!</p>
		  <input id="uploadDeck" type="file"></input>
	  <button id="deckSubmit" onclick="upload_deck()">Choose a File and Click Here</button>
	  
	</div>
	
	<div id="export"> 
		 <a class="close" id="close" onclick="slideOut()"></a>
		<h2 style="text-align:center;color:white;">Export</h2>
		<p style="color:white;">Click below to save a local <code>.json</code> file containing the current deck.</p>
		
		<button id="saveDeck" onclick="download_deck()">Save this Deck?</button>
</div>
 
  </div>
<a class="activator" id="activator" onclick="slideIn()">Click Here to Import & Export/Save Decks of Cards</a>
      <script type="text/javascript">

    </script>
</body>





