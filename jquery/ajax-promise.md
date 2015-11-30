Ajax Promise
============

The `$.ajax` method returns a Promise, so you can do something like this:

```coffeescript
myFunction = ->
  # ...
  
  call = $.ajax({
    # ...
  })
  
  return call
  
myFunction().done( (data) ->
  # ...
)
```
