---
layout: post
title:  "Call-By-Sharing in Javascript"
categories: javacript
---
{% highlight javascript %}
function increment(value = 0) {
  return value + 1;
}
const initial = 0;
const incrementedValue = increment(initial);
console.log(initial); // logs 0
console.log(incrementedValue); // logs 1
console.log(initial === incrementedValue); // logs false
{% endhighlight %}

{% highlight javascript %}
function increment(valueObject) {
  valueObject.value = valueObject.value + 1;
  return valueObject;
}
const initial = {
  value: 0
};
const incrementedValue = increment(initial);
console.log(initial); // logs { value: 1 }
console.log(incrementedValue); // logs { value: 1 }
console.log(initial === incrementedValue); // logs true
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
