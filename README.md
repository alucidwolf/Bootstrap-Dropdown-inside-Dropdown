# Bootstrap-Dropdown-inside-Dropdown
Brief example showing how some javascript can you provide you with the opportunity to create a form inside of a dropdown using bootstrap and some additional javascript

##HTML
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Dropdown inside dropdown</title>
  <!-- Bootstrap -->
  <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous"></head>
<body>
  <div class="col-xs-12">
    <h1>Dropdown inside dropdown</h1>
    <ul>
      <li class="dropdown bd-dropdown">
        <a href="javascript:;" class="dropdown-toggle">My dropdown inside dropdown list</a>
        <div class="dropdown-menu bd-dropdown-menu col-xs-12">
          <div class="dropdown">
            <button class="btn btn-default dropdown-toggle" type="button" id="dropdown-dropdown" data-toggle="dropdown" aria-haspopup="true" aria-expanded="true">
              Dropdown
              <span class="caret"></span>
            </button>
            <ul class="dropdown-menu" aria-labelledby="dropdown-dropdown">
              <li>
                <a href="#">Action</a>
              </li>
              <li>
                <a href="#">Another action</a>
              </li>
              <li>
                <a href="#">Something else here</a>
              </li>
              <li role="separator" class="divider"></li>
              <li>
                <a href="#">Separated link</a>
              </li>
            </ul>
          </div>
          <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
          <input type="checkbox" id="inlineCheckbox1" value="option1">
          1
          <input type="radio" name="inlineRadioOptions" id="inlineRadio1" value="option1">
          1
          <select class="form-control">
            <option>1</option>
            <option>2</option>
            <option>3</option>
            <option>4</option>
            <option>5</option>
          </select>
          <div class="col-xs-12">
            <a class="btn">a.button</a>
            <a class="btn">a.button</a>
          </div>
        </div>
      </li>
    </ul>
  </div>
  <div class="col-xs-12">
    <h1>Content below the dropdown</h1>
    <h1>Content below the dropdown dropdown</h1>
    <h1>Content below the dropdown dropdown dropdown</h1>
    <h1>Content below the dropdown dropdown dropdown dropdown</h1>
    <h1>Content below the dropdown dropdown dropdown dropdown dropdown</h1>
  </div>

  <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>

  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" integrity="sha384-0mSbJDEHialfmuBBQP6A4Qrprq5OVfW37PRR3j5ELqxss1yVqOtnepnHVP9aJ7xS" crossorigin="anonymous"></script>

</body>
</html>
```

##Javascript
```
      $(document).ready(function(){
        $('li.dropdown.bd-dropdown a').on('click', function(event){
          $(this).parent().toggleClass("open");
        });
        $('body').on('click', function (e) {
          if (!$('li.dropdown.bd-dropdown').is(e.target) && $('li.dropdown.bd-dropdown').has(e.target).length === 0 && $('.open').has(e.target).length ===0){
            $('li.dropdown.bd-dropdown').removeClass('open');
          }
        });
      });
```
