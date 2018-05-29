# JavaScript Snippets
Add Listener with IE support

```js
function addEvent(evnt, elem, func) {
    if (elem.addEventListener) // W3C DOM
        elem.addEventListener(evnt, func, false);
    else if (elem.attachEvent) { // IE DOM
        elem.attachEvent("on" + evnt, func);
    } else { // No much to do
        elem[evnt] = func;
    }
}

function uploadHandler(e){
    e.stopPropagation();
    e.preventDefault();
    console.log("Super Event Working");
    return false;
}

var uploadBtn = document.getElementById("uploadBtn");
addEvent("click", uploadBtn, uploadHandler);
```

