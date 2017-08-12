---
title: Jekyll, SASS fragments, and DRY
---

This is how I configured Jekyll on this site, so I can display the SASS code I am using for some example without having to duplicate the sass code both in the head and in the post text: 

I put SASS fragments in **_includes/*.sass**, for example _includes/generated.sass and _includes/quotes.sass

On a page where I am using these sass fragments, I define a page variable **page.sass** in the Jekyll's page configuration: 
 
{% highlight txt %}
---
title: Generate content with :before and :after
sass:
  - generated.sass
  - quotes.sass
---
{% endhighlight %} 

In the default layout file **default.html** I convert the sass fragments to css and include the css code inline in the head of the page. This css code is included only on that page that defines the sass variable: 
 
{% highlight liquid %}{% raw %}
{% for sass in page.sass %}
  <style>{% capture include_to_sassify %}{% include {{sass}} %}{% endcapture %}{{ include_to_sassify | sassify }}</style>
{% endfor %}
{% endraw %}{% endhighlight %}    

To display the sass fragment as syntax-highlighted text on that page: 

{% highlight liquid %}{% raw %}
{% highlight sass %}
{% include generated.sass %}
{% endhighlight %}
{% endraw %}{% endhighlight %}   

