#About this Guide
This Guide will show you the features & usage of this grid step by step.

Just starting out? <br>
Then just "code along" with the examples.

**For this you have two options:**

1. Either install the grid locally<br>
[Installation Guide](http://codepen.io/NilsDannemann/pen/MKZQxe?editors=1100)

1. Or use the Playground on Codepen<br>
[Open Playground](http://codepen.io/NilsDannemann/pen/MKZQxe?editors=1100)

Both Options are fine.


<br>
#A quick Example
Before we begin, here's the most basic usage pattern.

```sass
.parent {
	@include grid();

	.children {
		@include column('1/4');
	}
}
```

The steps are always the same:

1. Activate the grid on the parent container. <br>
```@include grid();```

1. Define columns for the children. <br>
```@include column('1/4');```

That's it.


<br><hr>
# The Guide
So let's begin.

<br><hr>
###Using Columns
You have quite a few options to define the widths of your columns.

**Fractions:** The simplest way is to use fractions.
```sass
@include column('1/4'); 	
@include column('2/9');
@include column('14/23');
```

**Values:** Just pass any value. (px, em, %, rem, anything really).
```sass
@include column('20%'); 	
@include column('15em');
@include column('200px');
```

**Auto:** Automatically fills the available space.
```sass
@include column('auto'); 	
```

**Content:** Let's the content of the column determine the width.
```sass
@include column('content'); 	
```


<br><hr>
###Adding Gutters

By default a column has no gutters. You can add gutters like so:

```sass
@include column('1/6', $gutter: true); 		// adds global gutters (use: 'true' or 'false')
@include column('1/6', true); 				// shorthand 
```
**Note:** This uses the global ```$whitespace``` variable from the config for gutters.

You can also specify your own gutters like so:
```sass
@include column('1/6', $gutter: 10px); 		// adds px gutters
@include column('1/6', $gutter: 2em); 		// adds em gutters
@include column('1/6', $gutter: 3%); 		// adds % gutters
@include column('1/6', $gutter: $var); 		// you can also use sass-variables
@include column('1/6', $gutter: $var/2); 	// you can even do math with them
```



<br><hr>
###Behavior

By default a column has no special behavior.
Currently you can add one behavior: "stacking".

**Stacking:** This causes the columns to stack on mobile (common pattern).
The default breakpoint for this to happen is "l". But you can just pass a different breakpoint to change this to your liking.

```sass
@include column('1/6', $gutter: true, $stacking: true); //stack below l
@include column('1/6', $gutter: true, $stacking: s); 	//stack below s
```



<br><hr>
###Using !important

Simply pass a $important variable.

```sass
@include column('1/6', $important: true); 	// adds the !important
```



<br><hr>
###Snippets
The Snippets for Sublime Text are optional but make the workflow much faster. <br>
**Install:** [Download](https://dl.dropboxusercontent.com/u/7534528/HFC/Relay/snippets.zip) the Snippets and place them in your `(path_to_sublime)/Packages/User` folder.<br>
**Usage:** Just type `column` and hit `TAB` to place your include.

<br><hr>
###Playground
You can test the mixin over here:<br>
![alt tag](https://dl.dropboxusercontent.com/u/7534528/HFC/Relay/code-playground.svg)
[Open Playground](http://codepen.io/NilsDannemann/pen/MKZQxe?editors=1100)