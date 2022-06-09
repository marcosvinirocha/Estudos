```javascript
function DOM(nodeName) {

this.element = document.querySelectorAll(nodeName)

  

this.on = (event, callback) => {

Array.prototype.forEach.call(this.element, (node) => {

node.addEventListener(event, callback)

})

}

  

this.off = (event, callback) => {

Array.prototype.forEach.call(this.element, (node) => {

node.removeEventListener(event, callback)

})

}

  

this.get = () => this.element

}

  

var $a = new DOM('[data-js="link"]');

$a.on('click', function (e) {

e.preventDefault();

console.log('clicou');

});

  

console.log('Elementos selecionados:', $a.get());

console.log('$a é filho de body?', $a.get()[0].parentNode === document.body);

```


###Percorrer Dom
```javascript
function DOM(query){

this.nodeElements = doc.querySelectorAll(query);

}

  

DOM.prototype.on=function(eventName, callback){

Array.prototype.forEach.call(this.nodeElements, (value) => value.addEventListener(eventName, callback, false));

}

  

DOM.prototype.get=function(){

return this.nodeElements;

}

  

DOM.is = function is(object){

return Object.prototype.toString.call(object);

}

  

DOM.prototype.off=function(eventName, callback){

Array.prototype.forEach.call(this.nodeElements, (value) => value.removeEventListener(eventName, callback))

}

  

DOM.prototype.foreach=function(eventName, callback){

return Array.prototype.forEach.apply(this.nodeElements, arguments);

}

  

DOM.prototype.map=function(){

return Array.prototype.map.apply(this.nodeElements, arguments);

}

  

DOM.prototype.filter=function(){

return Array.prototype.filter.apply(this.nodeElements, arguments);

}

  

DOM.prototype.reduce=function reduce(){

return Array.prototype.reduce.apply(this.nodeElements, arguments);

}

  

DOM.prototype.reduceRight = function reduceRight(){

return Array,prototype.reduceRight.apply(this.nodeElements, arguments);

}

  

DOM.prototype.every = function every(){

return Array.prototype.every.apply(this.nodeElements, arguments);

}

  

DOM.prototype.some = function some(){

return Array.prototype.some.apply(this.nodeElements, arguments);

}

  

DOM.isArray = function(object){

return DOM.is(object) === '[object Array]';

}

  

DOM.isObject = function(object){

return DOM.is(object) === '[object Object]';

}

  

DOM.isNumber = function(object){

return DOM.is(object) === '[object Number]';

}

  

DOM.isBoolean = function(object){

return DOM.is(object) === '[object Boolean]';

}

  

DOM.isFunction = function(object){

return DOM.is(object) === '[object Function]';

}

  

DOM.isNull = function(object){

return DOM.is(object) === '[object Null]' || DOM.is(object) === '[object Undefined]';

}

  

var $a = new DOM('[data-js="link"]');

$a.on('click', function(e) {

e.preventDefault();

console.log('clicou');

});

  

console.log('Elementos selecionados:', $a.get());

console.log('$a é filho de body?', $a.get()[0].parentNode === document.body);

  

DOM.isArray([1, 2, 3]); // true

DOM.isFunction(function() {}); // true

DOM.isNumber('numero'); // false
```