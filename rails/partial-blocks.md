Partial Blocks
==============

Let's say that we want to render a partial with a block of content that will be nested inside the partial.

```haml
= card 'primary' do
  %h2 Card title!
  %p Here is some content that will render in the card.
```

To do that, we can create two helper methods:

```ruby
def block_to_partial(partial_name, options = {}, &block)
  options.merge!(body: capture(&block))
  render(partial: partial_name, locals: options)
end

def card(type, options = {}, &block)
  block_to_partial 'templates/card', options.merge(type: type), &block
end
```

And then, in the partial:

```haml
.card{ class: "card--#{ type }" }
  = body
```

Now we can write it like we did before:

```haml
= card 'primary' do
  %h2 Card title!
  %p Here is some content that will render in the card.
```

And the generated HTML will look like so:

```html
<div class='card card--primary'>
  <h2>Card title!</h2>
  <p>Here is some content that will render in the card.</p>
</div>
```

As you can imagine, this can make authoring complex markup with several classes much simpler.

Credit: http://stackoverflow.com/questions/7399192/how-to-make-this-work-in-rails-3
