link_to Punctuation
===================

In Haml, to add punctuation after a `link_to`:

```haml
# Option 1:
= link_to('Text', '#') + '.'

# Option 2:
= succeed '.' do
  = link_to 'Text', '#'
  
# Option 3:
#{ link_to 'Text', '#' }.
```
