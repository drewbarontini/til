Regex Variables
===============

In Ruby, you can store regular expressions in variables like so:

```ruby
regex = '^Hello'

file.gsub(/#{ regex }/, 'Goodbye')
```
