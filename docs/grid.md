#Welcome to the Guide
This Guide will show you the features & usage of this grid step by step.

Just starting out? <br>
Then just "code along" with the examples.

**For this you have two options:**

1. Either install the grid locally<br>
[Installation Guide](https://github.com/NilsDannemann/hfc-relay-grid)

1. Or use the Playground on Codepen<br>
[Open Playground](http://codepen.io/NilsDannemann/pen/MKZQxe?editors=1100)

Both Options are fine.


<br>
##A quick Example
Before we begin:<br> 
Here's the most basic usage pattern.

```sass
.parent {
	@include grid();

	.children {
		@include column('1/4');
	}
}
```

The pattern is always the same:

1. Activate the grid on the parent. <br>
```@include grid();```

1. Define columns on the children. <br>
```@include column('1/4');```

That's it.


<br>
# The Guide
So let's begin.

<br>
##Step 1 - Defining Columns
You have quite a few options to define the widths of your columns.

**Fractions** <br> 
The simplest way is to use fractions.
```sass
@include column('1/4'); 	
@include column('2/9');
@include column('14/23');
```

**Values** <br> 
Just pass any value. (px, em, %, rem, anything really).
```sass
@include column('20%'); 	
@include column('15em');
@include column('200px');
```

**Auto** <br> 
Automatically fills the available space.
```sass
@include column('auto'); 	
```

**Content** <br> 
Let's the content of the column determine the width.
```sass
@include column('content'); 	
```


<br>
##Step 2 - Adding Gutters

By default a column has no gutters. You can add gutters like so:

```sass
@include column('1/6', $gutter: true); 		// use: 'true' or 'false'
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



<br>
##Step 3 - Adding Behavior

By default a column has no special behavior.<br>
Currently you can add one behavior: "stacking".

**Stacking** <br>
This causes the columns to stack on mobile (common pattern).<br>
The default breakpoint for this to happen is "l". But you can just pass a different breakpoint to change this.

```sass
@include column('1/6', $gutter: true, $stacking: true); //stack below l
@include column('1/6', $gutter: 10px, $stacking: s); 	//stack below s
```



<br>
##Optional - Using !important

Simply pass a $important variable.

```sass
@include column('1/6', $important: true); 	// adds !important
```

