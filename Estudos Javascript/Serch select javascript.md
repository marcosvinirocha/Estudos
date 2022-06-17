```javascript
var values = "Test,Prof,Off",
    options = Array.from(document.querySelectorAll('#strings option'));

values.split(',').forEach(function(v) {
  options.find(c => c.value == v).selected = true;
});
```

```xml
<select name='strings' id="strings" multiple style="width:100px;">
    <option value="Test">Test</option>
    <option value="Prof">Prof</option>
    <option value="Live">Live</option>
    <option value="Off">Off</option>
    <option value="On">On</option>
</select>
```