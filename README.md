# 4d-plugin-json

![obsolete-word-black-frame-word-obsolete-word-black-frame-d-rendering-123942590](https://user-images.githubusercontent.com/1725068/78463940-29122280-771e-11ea-8be8-a7830725403e.jpg)

### Platform

| carbon | cocoa | win32 | win64 |
|:------:|:-----:|:---------:|:---------:|
|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|<img src="https://cloud.githubusercontent.com/assets/1725068/22371562/1b091f0a-e4db-11e6-8458-8653954a7cce.png" width="24" height="24" />|

## Examples

```
$j:=JSON New 
JSON CLOSE ($j)
JSON CLOSE ($j)  //now checks for root validity; previously would crash

$j:=JSON New 
JSON Append node ($j;"obj1";"{\"1\":1}")  //now accepts JSON as $3
JSON Append node ($j;"array_2_3";"[{\"2\":2},{\"3\":3}]")
$json:=JSON Export to text ($j;JSON_WITHOUT_WHITE_SPACE)
JSON CLOSE ($j)

$obj1:=JSON Parse text ("{\"1\":1}")
$obj2:=JSON Parse text ("{\"2\":2}")
$obj3:=JSON Parse text ("{\"3\":3}")

$j:=JSON New 
JSON Append node ($j;"obj1";"{\"1\":1}")
$arr:=JSON Append array ($j;"array_2_3")  //shorthand for append node+set type to array
JSON Append array element ($arr;$obj2)  //appends a copy of the node
JSON Append array element ($arr;$obj3)  //appends a copy of the node
$json:=JSON Export to text ($j;JSON_WITHOUT_WHITE_SPACE)
JSON CLOSE ($j)

  //don't forget to close everything you opened, either by _New or _Parse
JSON CLOSE ($obj1)
JSON CLOSE ($obj2)
JSON CLOSE ($obj3)

```
