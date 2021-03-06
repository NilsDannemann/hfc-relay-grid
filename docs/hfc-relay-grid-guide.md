![alt tag](https://dl.dropboxusercontent.com/u/7534528/HFC/Relay/relay_logo.jpg)

<br>
#The Grid
This Guide will show you the features & usage of this grid step by step.

<br>
##Step 1 - Activate Grid
This activates the grid and gives you some layout-options via flexbox.<br> 

```sass
.parent {
	@include grid();

	.children {

	}
}
```

####Options
```$align``` - Equal Column Height - Usage: ```@include grid($align:stretch);```<br>
```$justify``` - RTL Column Layout - Usage: ```@include grid($justify:end);```


<br>
##Step 2 - Define Columns
You have quite a few options to define the widths of your columns.

####Option 1: Use Fractions 
Pass any fraction you like.
```sass
.parent {
	@include grid();

	.children {
		// Pass any fraction...
		@include column('1/4');
		@include column('2/9');
		@include column('14/23');
	}
}
```

####Option 2: Use Values
Just pass any value. (px, em, %, rem...)
```sass
.parent {
	@include grid();

	.children {
		// ...or pass any value...
		@include column('20%'); 	
		@include column('15em');
		@include column('200px');
	}
}
```

####Option 3: Use 'auto'
Let columns automatically fill the available space.
```sass
.parent {
	@include grid();

	.children {
		// ...or use the kayword 'auto'...
		@include column('auto'); 
	}
}	
```

####Option 4: Use 'content'
Let's the content of the column determine the width.
```sass
.parent {
	@include grid();

	.children {
		// ...or use the kayword 'auto'...
		@include column('content'); 
	}
}		
```


<br>
##Step 3 - Add Gutters

By default a column has no gutters.<br>
You can add gutters like so:

```sass
.parent {
	@include grid();

	.children {
		@include column('1/4', $gutter: true);
	}
}	
```

####Customize Gutters
By default gutters use the global ```$whitespace``` variable from the config. <br>
But you can also specify your own gutters like so:
```sass
.parent {
	@include grid();

	.children {
		@include column('1/4', $gutter: 10px); 		// adds px gutters
		@include column('1/4', $gutter: 2em); 		// adds em gutters
		@include column('1/4', $gutter: 3%); 		// adds % gutters
		@include column('1/4', $gutter: $var); 		// you can also use sass-variables
		@include column('1/4', $gutter: $var*0.5); 	// you can even do math with them
	}
}	
```



<br>
##Step 4 - Go Responsive (optional)

To go responsive you can use the [responsive mixins](https://github.com/NilsDannemann/hfc-relay-grid/docs/hfc-relay-grid-queries.md).<br>


```sass
.parent {
	@include grid();

	.children {
		@include column('1/2');
		
		// From 2 to 4 columns above the breakpoint 'm'
		@include respond-above(m) {
			@include column('1/4');
		}
	}
}	
```




<br>
##Step 5 - Add Behavior (optional)

Behaviors are basically a **shorthand for the responsive mixins**.

By default a column has no special behavior.<br>
Currently there is only one behavior: "stacking"

####Stacking
This causes the columns to stack on mobile (common pattern).<br>
The default breakpoint for this to happen is "l", but you can just pass a different breakpoint to change this.

```sass
.parent {
	@include grid();

	.children {
		@include column('1/4', $stacking: true); //stack below breakpoint 'l' (default)
		@include column('1/4', $stacking: s); 	 //stack below breakpoint 's'
	}
}
```

<br>
<hr>
##Other - !important

Simply pass a $important variable. <br>
This adds !important to the width of the column.

```sass
@include column('1/4', $important: true); 	// adds !important
```

