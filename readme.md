# attr-range

## Mixin to pass in desired attribute and range of values

Have you ever needed to create a mixin where you want to set the padding or margin as a default value? Ok, this is simple enough, but what if you want to pass those values into other functions, like the `em()` function for example? 

Using a simple Sass list and creating a mixin you can inset in your selector, this helps to manage this need.

### Example Sass
	$marginWidths: 10 30 15 10 !default;
	$paddingWidths: 0 20 !default;
	
	.block-element {
	  @include attr-range(margin, $marginWidths);
	}
	
	.header {
	  @include attr-range(padding, $paddingWidths);
	}
	
	aside {
	  @include attr-range(margin, 0 20 10);
	}

### Output CSS
	.block-element {
	  margin: 0.625em 1.875em 0.9375em 0.625em; }
	
	.header {
	  padding: 0em 1.25em; }
	
	aside {
	  margin: 0em 1.25em 0.625em; }
	  
	  
## To install

A few choices, you could simple copy and paste the code into your project or Bower all the things! 

	$ bower install attr-range --save
	
In your Grunt file (using Grunt-Sass):

	sass: {
      dist: {
        files: {
          'application.css': 'sass/application.scss'
        },
        options: {
          includePaths: [
            './bower_components/attr-range'
          ]
        }
      }
    }
    
In your Sass manifest:

	@import "attr-range";
