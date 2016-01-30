---
layout: page_ads
title: Guile Cookbook
permalink: /cookbook/
published: false
---

* TOC
{:toc}

## Guile Scheme

### Modules

#### Simply Importing modules

{% highlight scheme %}
(use-modules (srfi srfi-19))
{% endhighlight %}

### Strings

#### Reverse String

{% highlight scheme %}
(string-reverse str [start [end]])
{% endhighlight %}

#### Reverse String in Place

{% highlight scheme %}
(string-reverse! str [start [end]])
{% endhighlight %}

### Time and Date

### IO

{% highlight scheme %}
    (open-file filename
        (if binary "wb" "w")
            #:encoding encoding)
{% endhighlight %}

### Network

#### Http requests
{% highlight scheme %}
(use-modules (web client))
(http-get url #:streaming? #t)
{% endhighlight %}

#### Displaying text
{% highlight scheme %}
(display "Guile Cookbook")
(newline)
{% endhighlight %}

## The C Side

### Loading a Scheme source file
{% highlight c %}

scm_c_primitive_load ("source.scm");

{% endhighlight %}

### Calling a Scheme function
{% highlight c %}
/* Declare SCM types for calling a function and reading its output */
SCM func_symbol;
SCM fun;
SCM ret_val;

/* Look up the symbol */
func_symbol = scm_c_lookup("function-name");
func = scm_variable_ref(func_symbol);
/* Call a Scheme function taking one argument */
ret_val = scm_call_1(func, scm_from_locale_string("string argument"));

/* ret_val now holds the return value from the function */

{% endhighlight %}

<a href="https://github.com/pasoev/guile-cookbook"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/365986a132ccd6a44c23a9169022c0b5c890c387/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f7265645f6161303030302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_red_aa0000.png"></a>
