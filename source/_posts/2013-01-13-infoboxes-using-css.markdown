---
layout: post
title: "InfoBoxes using CSS"
date: 2013-01-13 16:22
comments: true
categories: [CSS, Snippets, Open Source]
---

In my old blog framework I've used a lot of `InfoBoxes` that were heavily influenced by a series of Macros provided in [Confluence](http://www.atlassian.com/software/confluence/).

These `InfoBoxes` were used to display notes, warnings and the like whenever it seemed appropriate. Here are links to the original macros from Confluence.

* [Info Macro](https://confluence.atlassian.com/display/DOC/Info+Macro)
* [Tip Macro](https://confluence.atlassian.com/display/DOC/Tip+Macro)
* [Note Macro](https://confluence.atlassian.com/display/DOC/Note+Macro)
* [Warning Macro](https://confluence.atlassian.com/display/DOC/Warning+Macro)

<!-- more -->

#### Old InfoBoxes:

And here's what the old `InfoBoxes` looked like:

<div class="oldinfo">This is an example of the Old InfoBox.</div>

<div class="oldsuccess">This is an example of the Old SuccessBox.</div>

<div class="oldwarning">This is an example of the Old WarningBox.</div>

<div class="olderror">This is an example of the Old ErrorBox.</div>

Here's the old CSS that generated these old `InfoBoxes`

{% codeblock CSS for Confluence Style Macro Boxes %}
.oldinfo, .oldsuccess, .oldwarning, .olderror {
    border: 1px solid;
    margin: 10px 0px;
    padding:15px 10px 15px 50px;
    background-repeat: no-repeat;
    background-position: 10px center;
    }
    
.oldinfo {
    color: #00529B;
    background-color: #BDE5F8;
    background-image: url('/images/info.png');
    -moz-border-radius: 10px;
	border-radius: 10px;
    }
    
.oldsuccess {
    color: #4F8A10;
    background-color: #DFF2BF;
    background-image:url('/images/success.png');
    -moz-border-radius: 10px;
	border-radius: 10px;    
    }
    
.oldwarning {
    color: #9F6000;
    background-color: #FEEFB3;
    background-image: url('/images/warning.png');
     -moz-border-radius: 10px;
	border-radius: 10px;   
    }
    
.olderror {
    color: #D8000C;
    background-color: #FFBABA;
    background-image: url('/images/error.png');
    -moz-border-radius: 10px;
	border-radius: 10px;    
    }
{% endcodeblock %}

#### New InfoBoxes:

The new `InfoBoxes` no longer use an image and use pure CSS 3. Here is what they look like:

__Style 1__

<div class="info">Info: This is an example of the New InfoBox.</div>

<div class="success">Success: This is an example of the New SuccessBox.</div>

<div class="warning">Warning: This is an example of the New WarningBox.</div>

<div class="error">Error: This is an example of the New ErrorBox.</div>

__Style 2__

<div class="infobox">Info: This is an example of the New InfoBox.</div>

<div class="successbox">Success: This is an example of the New SuccessBox.</div>

<div class="warningbox">Warning: This is an example of the New WarningBox.</div>

<div class="errorbox">Error: This is an example of the New ErrorBox.</div>

And here's the new CSS that generates these new `InfoBoxes`

{% codeblock New InfoBoxes using Pure CSS 3 %}
.info {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#075698; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#2e88c4), to(#075698));
	background:-moz-linear-gradient(#2e88c4, #075698);
	background:-o-linear-gradient(#2e88c4, #075698);
	background:linear-gradient(#2e88c4, #075698);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.success {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#5a8f00; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#b8db29), to(#5a8f00));
	background:-moz-linear-gradient(#b8db29, #5a8f00);
	background:-o-linear-gradient(#b8db29, #5a8f00);
	background:linear-gradient(#b8db29, #5a8f00);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.warning {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#f3961c; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#f9d835), to(#f3961c));
	background:-moz-linear-gradient(#f9d835, #f3961c);
	background:-o-linear-gradient(#f9d835, #f3961c);
	background:linear-gradient(#f9d835, #f3961c);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.error {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#c81e2b; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#f04349), to(#c81e2b));
	background:-moz-linear-gradient(#f04349, #c81e2b);
	background:-o-linear-gradient(#f04349, #c81e2b);
	background:linear-gradient(#f04349, #c81e2b);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.infobox {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#075698; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#2e88c4), to(#075698));
	background:-moz-linear-gradient(#2e88c4, #075698);
	background:-o-linear-gradient(#2e88c4, #075698);
	background:linear-gradient(#2e88c4, #075698);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.infobox:after {
	content:"";
	position:absolute;
	bottom:-20px; /* value = - border-top-width - border-bottom-width */
	left:50px; /* controls horizontal position */
	border-width:20px 0 0 20px; /* vary these values to change the angle of the vertex */
	border-style:solid;
	border-color:#075698 transparent; 
    /* reduce the damage in FF3.0 */
    display:block; 
    width:0;  
}

.successbox {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#5a8f00; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#b8db29), to(#5a8f00));
	background:-moz-linear-gradient(#b8db29, #5a8f00);
	background:-o-linear-gradient(#b8db29, #5a8f00);
	background:linear-gradient(#b8db29, #5a8f00);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.successbox:after {
	content:"";
	position:absolute;
	bottom:-20px; /* value = - border-top-width - border-bottom-width */
	left:50px; /* controls horizontal position */
	border-width:20px 0 0 20px; /* vary these values to change the angle of the vertex */
	border-style:solid;
	border-color:#5a8f00 transparent; 
    /* reduce the damage in FF3.0 */
    display:block; 
    width:0;  
}

.warningbox {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#f3961c; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#f9d835), to(#f3961c));
	background:-moz-linear-gradient(#f9d835, #f3961c);
	background:-o-linear-gradient(#f9d835, #f3961c);
	background:linear-gradient(#f9d835, #f3961c);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.warningbox:after {
	content:"";
	position:absolute;
	bottom:-20px; /* value = - border-top-width - border-bottom-width */
	left:50px; /* controls horizontal position */
	border-width:20px 0 0 20px; /* vary these values to change the angle of the vertex */
	border-style:solid;
	border-color:#f3961c transparent; 
    /* reduce the damage in FF3.0 */
    display:block; 
    width:0;  
}

.errorbox {
	position:relative;
	padding:15px;
	margin:1em 0 3em;
	color:#fff;
	background:#c81e2b; /* default background for browsers without gradient support */
	/* css3 */
	background:-webkit-gradient(linear, 0 0, 0 100%, from(#f04349), to(#c81e2b));
	background:-moz-linear-gradient(#f04349, #c81e2b);
	background:-o-linear-gradient(#f04349, #c81e2b);
	background:linear-gradient(#f04349, #c81e2b);
	-webkit-border-radius:10px;
	-moz-border-radius:10px;
	border-radius:10px;
}

.errorbox:after {
	content:"";
	position:absolute;
	bottom:-20px; /* value = - border-top-width - border-bottom-width */
	left:50px; /* controls horizontal position */
	border-width:20px 0 0 20px; /* vary these values to change the angle of the vertex */
	border-style:solid;
	border-color:#c81e2b transparent; 
    /* reduce the damage in FF3.0 */
    display:block; 
    width:0;  
}
{% endcodeblock %}

Feel free to use whichever bits you like if you've found this to be useful.
