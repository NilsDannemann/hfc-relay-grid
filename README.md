![alt tag](https://dl.dropboxusercontent.com/u/7534528/HFC/Relay/relay_logo.jpg)

# HFC Relay Grid (SCSS)
The grid is a **fraction-based** grid system and uses flexible sass-mixins instead of fixed classes.<br>

This approach has the following advantages over conventional grids:<br>

- **Flexibility** - just pass any ```$fraction``` and ```$gutter``` you like
- **Cleanliness** - keep your markup clean and readable
- **Simplicity** - keep all styles & behavior in one place (separation of concerns)


<br><hr>
## Installation

####1. Install the package<br>

Option 1: Install via npm
```sass
npm install hfc-relay-grid --save-dev
```

Option 2: Install via bower
```sass
bower install hfc-relay-grid --save-dev
```


####2. Create config<br> 
Create a `_hfc-relay-grid-config.scss` with [this content](src/_hfc-relay-grid-config.scss) (but remove all the `!default` statements) <br>

In there you can now:
- safely override any defaults
- easily import/use different fonts 
- toggle features like `debug-grid`


####3. Import<br> 
Import both Files in your sass in this order.
```sass
// HFC Relay
@import 'path/to/your/hfc-relay-grid-config.scss';
@import 'node_modules/hfc-relay/hfc-relay-grid.scss';

// Your other imports below.
```

That's it. <br>
Happy coding.


####4. Optional: Install Sublime Snippets
The Snippets for Sublime Text are optional but make the workflow much faster. <br>
**Install:** [Download](https://dl.dropboxusercontent.com/u/7534528/HFC/Relay/snippets.zip) the Snippets and place them in your `(path_to_sublime)/Packages/User` folder.<br>
**Usage:** Just type `grid` or `column` and hit `TAB` to place your include.


<br><hr>
## Usage

- [Container](docs/container.md)
- [The Grid](docs/grid.md)
- [Mediaqueries](docs/mediaqueries.md)
