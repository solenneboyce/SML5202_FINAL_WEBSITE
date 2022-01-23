<h1>Page 3</h1>
<p>write your content in this file as you would normally</p>



<html manifest="cache.manifest">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1"/>
    <title> Flashcards</title>
    <link href="static/bootstrap/css/bootstrap.min.css" rel="stylesheet"/>
    <style>
      .question-text { font-size: 28px }
    </style>
  </head>
  <body>
    <div class="container" id="decks">decks: </div>
    <hr class="soften"/>

    <div id="flashcard" class="container" data-sync="{{ sync | lower }}">
      <div id="question">
        <div class="question-text">question</div>
        <img class="image"></img>
        <br/>
        <button type="button" class="btn btn-primary btn-lg">show</button>
      </div>
      <div id="answer">
        <div class="answer-text">answer</div>
        <div class="note-text">note</div>
        <br/>
        <button type="button" class="btn btn-success btn-lg">right</button>
        <button type="button" class="btn btn-warning btn-lg">wrong</button>
      </div>
    </div>

    <hr class="soften"/>

    <div class="container">
      <button type="button" id="new-card-button" class="btn btn-primary">New card</button>
      <button type="button" id="edit-card-button" class="btn btn-info">Edit card</button>
      <button type="button" id="delete-card-button" class="btn btn-danger">Delete card</button>
    </div>

    <hr class="soften"/>

    <div class="container">
        <a id="export-button" download="flashcard.json" class="btn btn-default">Export</a>
        <a id="import-button" class="btn btn-default">Import</a>
        <input id="import-input" type="file" style="visibility:hidden;"/>
    </div>

    <!-- New card modal dialog -->
    <div id="new-card" class="modal fade">
    <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header"> <h4>Edit card</h4> </div>
      <div class="modal-body">

        <form role="form">
          <div class="form-group">
            <label for="input-question">Question</label>
            <input type="text" id="input-question" class="form-control" placeholder="Question">
          </div>
          <div class="form-group">
            <label for="input-answer">Answer</label>
            <input type="text" id="input-answer" class="form-control" placeholder="Answer">
          </div>
          <div class="form-group">
            <label for="input-note">Note</label>
            <input type="text" id="input-note" class="form-control" placeholder="Note">
          </div>
        </form>

      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-default" data-dismiss="modal">Cancel</button>
        <button type="button" id="add-button" class="btn btn-primary">Add</button>
      </div>
    </div>
    </div>
    </div>

    <script src="static/js/jquery-2.1.0.min.js"></script>
    <script src="static/bootstrap/js/bootstrap.min.js"></script>
    <script src="static/js/flashcard-ahhh.js"></script>
  </body>
</html>








