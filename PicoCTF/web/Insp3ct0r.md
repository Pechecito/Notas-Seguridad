### Descripcion
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670
### Solucion
Al entrar a la pagina simplemente se hizo un control U, y ahi esta la primera parte 
```javascript 
|<div id="tababout" class="tabcontent">|
||<h3>How</h3>|
||<p>I used these to make this site: <br/>|
||HTML <br/>|
||CSS <br/>|
||JS (JavaScript)|
||</p>|
||<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->|
||</div>|
```
Ahora verificamos los documentos a los que hace referencia: css y js
```javascript
|<head>|
||<title>My First Website :)</title>|
||<link href="[https://fonts.googleapis.com/css?family=Open+Sans\|Roboto](https://fonts.googleapis.com/css?family=Open+Sans\|Roboto)" rel="stylesheet">|
||<link rel="stylesheet" type="text/css" href="[mycss.css](https://jupiter.challenges.picoctf.org/problem/9670/mycss.css)">|
||<script type="application/javascript" src="[myjs.js](https://jupiter.challenges.picoctf.org/problem/9670/myjs.js)"></script>|
||</head>|
```
```css
.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```
```javascript
    }
    tablinks = document.getElementsByClassName("tablink");
    for (i = 0; i < tablinks.length; i++) {
	tablinks[i].style.backgroundColor = "";
    }
    document.getElementById(tabName).style.display = "block";
    if(elmnt.style != null) {
	elmnt.style.backgroundColor = color;
    }
}

window.onload = function() {
    openTab('tabintro', this, '#222');
}

/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?2e7b23e3} */
```

### Tags

