---
layout: post
title:  Powerful things you can do with the Markdown editor
image: assets/images/16.jpg
summary: This is the summary
mathjax: true
update_date: 2019-09-14
---
There are lots of powerful things you can do with the Markdown editor. If you've gotten pretty comfortable with writing in Markdown, then you may enjoy some more advanced tips about the types of things you can do with Markdown!

As with the last post about the editor, you'll want to be actually editing this post as you read it so that you can see all the Markdown code we're using.


## Special formatting

As well as bold and italics, you can also use some other special formatting in Markdown when the need arises, for example:

+ ~~strike through~~
+ ==highlight==
+ \*escaped characters\*
+ > Quote here

- ```html
  <span class="spoiler">My hidden paragraph here.</span>
  ```

## Writing code blocks

There are two types of code elements which can be inserted in Markdown, the first is inline, and the other is block. Inline code is formatted by wrapping any word or words in back-ticks, `like this`. Larger snippets of code can be displayed across multiple lines using triple back ticks:

```
.my-link {
    text-decoration: underline;
}
```

#### HTML

```html
<li class="ml-1 mr-1">
    <a target="_blank" href="#">
    <i class="fab fa-twitter"></i>
    </a>
</li>
```

#### CSS

```css
.highlight .c {
    color: #999988;
    font-style: italic; 
}
.highlight .err {
    color: #a61717;
    background-color: #e3d2d2; 
}
```

#### JS

```js
// alertbar later
$(document).scroll(function () {
    var y = $(this).scrollTop();
    if (y > 280) {
        $('.alertbar').fadeIn();
    } else {
        $('.alertbar').fadeOut();
    }
});
```

#### Python

```python
print("Hello World")
```

#### Ruby

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

#### C

```c
printf("Hello World");
```



{% include image.html
            img="assets/images/20190914-markdown/monte_carlo_gridworld.png"
            title="gridworld"
            caption="Snapshot Ensemble is created by saving a model each time the learning rate cycle is at the end. Then the saved models are used together during prediction. <a href=\"https://arxiv.org/abs/1704.00109\">Source</a>." %}

![walking]({{ site.baseurl }}/assets/images/20190914-markdown/monte_carlo_gridworld.png)

## Reference lists

The quick brown jumped over the lazy.

Another way to insert links in markdown is using reference lists. You might want to use this style of linking to cite reference material in a Wikipedia-style. All of the links are listed at the end of the document, so you can maintain full separation between content and its source or reference.

## Equations

You can write equations too:

$$
a^2 + b^2 = c^2
$$

Inline equation $\sigma^2 = \frac{a}{b}$  is also possible

## Diagrams

```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```



## Tweet embedding

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Lyft open-sourced their autonomous driving dataset from its Level 5 self-driving fleet. <br><br>- 55k human-labeled 3D frames<br>- 7 cameras, 3 lidars<br>- HD spatial semantic map: lanes, crosswalks, etc<br>- Drivable surface map<a href="https://t.co/KDvvKRWX2w">https://t.co/KDvvKRWX2w</a> <a href="https://t.co/uvQ8jmw2UG">pic.twitter.com/uvQ8jmw2UG</a></p>&mdash; Reza Zadeh (@Reza_Zadeh) <a href="https://twitter.com/Reza_Zadeh/status/1153745243029700608?ref_src=twsrc%5Etfw">July 23, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


## Full HTML

Perhaps the best part of Markdown is that you're never limited to just Markdown. You can write HTML directly in the Markdown editor and it will just work as HTML usually does. No limits! Here's a standard YouTube embed code as an example:

<p><iframe style="width:100%;" height="480" src="https://www.youtube.com/embed/Cniqsc9QfDo?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></p>