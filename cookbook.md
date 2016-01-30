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

    (use-modules (srfi srfi-19))

### Strings

#### Reverse String
    (string-reverse str [start [end]])

#### Reverse String in Place
    (string-reverse! str [start [end]])

### Time and Date

### IO
    (open-file filename
        (if binary "wb" "w")
            #:encoding encoding)


### Network

#### Http requests
    (use-modules (web client))
    (http-get url #:streaming? #t)

#### Displaying text
    (display "Guile Cookbook")
    (newline)

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

<a href="https://github.com/pasoev"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/365986a132ccd6a44c23a9169022c0b5c890c387/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f7265645f6161303030302e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_red_aa0000.png"></a>
