# Baloo Boilerplate
## Only the [bare necessities](http://www.youtube.com/watch?v=TcglnY_xGfc)

Baloo Boilerplate is [HTML5 Boilerplate](http://html5boilerplate.com/) & [320 and Up](http://stuffandnonsense.co.uk/projects/320andup/) combined, stripped down and organized according to the [SMACSS](http://smacss.com/) principles using [SASS](http://sass-lang.com/).

Also, it uses [prefixfree.js](http://leaverou.github.com/prefixfree/) by [Lea Verou](https://twitter.com/LeaVerou) which allows you to use the official CSS3 syntax without having to worry about vendor prefixes like `-webkit-`, `-moz-` etc. It’s a JavaScript file that detects *which* vendor prefixes your visitors browser needs, and then crawls through your CSS adding **only the necessary** prefixed rules to the CSS file.

What Baloo tries to do is: Give you what you **will** use so you can add what you **want** to use later on, instead of giving you a whole lot of things you **might** use so you need to **clean up** afterwards or bear with a messy project folder and prefab CSS code that conflicts with yours while you don’t even use it.

It is not meant to be **something** for **everyone**, it’s meant to be **it** for **some people**: people who create [mobile-first](http://www.abookapart.com/products/mobile-first) responsive websites using [SASS](http://sass-lang.com/) and who want to write [maintainable an reusable code](http://smacss.com/).

This project is new: comments, questions and suggestions can be [tweeted to Baloo (@baloobp)](https://twitter.com/baloobp)

In the following sections we will be discussing *Workflow*, *CSS structure*, *Folder structure* and some *Things you might want to add*.

### Workflow

This boilerplate is meant to be used for mobile first development, so you might want to go through the SCSS files top to bottom. Of course you don't need to finish the first file 100% before you can go on to the next one, but consider it good practice:

1. **Base:** Style your HTML elements

	So you got your raw HTML file: style your headings, paragraphs, links, &hellip; so they look like you want them to in **mobile** view.

2. **Layout:** Create the **mobile layout** (not design) for your page’s sections

	Chances are there's not that much layout to be done, since most mobile layouts are just the HTML components right beneath each other.

3. **Modules:** Create the look and layout for the reusable modules (menus, buttons, sliders, &hellip;) of your site (once again, **mobile** view only)

4. **States:** Create the look and layout for the different elements in their different states.

5. **Theme:** *If you have different themes*, design them here.

6. Create layout and design adjustments for different screen sizes in **_480.scss** to **_1392.scss**.

	You will be adding a lot under the `// Layout rules` comments in these files, continue reading CSS Structure for more on that.

7. Make adjustments for devices with high pixel density (e.g. retina displays on iPhone) and print in **_2x.scss** and **_print.scss**



### CSS Structure

All the sass files are in the /css/scss folder and are imported in main.**scss**, which will compile to /css/main.**css**, in order to keep things organized.

The files are structured as follows:

1. #### Reusable components

	1. _fonts.scss
		
		Put your @font-face imports here. Fonts go in /css/fonts since they're part of the *style*, not the *content*

	2. _variables.scss

		Variables go here (e.g.: colors for your color scheme, baseline height for calculations, &hellip;)

	3. _animations.scss

		CSS3 animations get their private parking spot.

	4. _mixins.scss

		and so do SASS mixins.

	They are orderd like this because: variables might use fonts (e.g.: store your fontstacks in a variable), animations might use variables (e.g.: your colors) and mixins might use all of the above.

	(If you don't know what mixins are, this boilerplate is not for you, [go check up on SASS first](http://sass-lang.com/), you'll love it!)



2. #### SMACSS

	I will paste short excerpts from the SMACSS website here for clarity, but [I strongly advise you to read up on it and make this knowledge your own](http://smacss.com/): your coding skills will be better for it.

	1. _base.scss

		Direct styling for page elements (e.g. h1, a, em, &hellip;)

		> It is defining the default styling for how that element should look in all occurrences on the page.

	2. _layout.scss

		Major layout rules (e.g. header, sidebar, contentarea). Not layout for modules (e.g. formfield positioning).

		> There is a distinction between layouts dictating the major and minor components of a page. The minor components—such as a callout, or login form, or a navigation item—sit within the scope of major components such as a header or footer.

	3. _modules.scss

		Layout and design for reusable components of your website.

		> A Module is a more discrete component of the page. It is your navigation bars and your carousels and your dialogs and your widgets and so on. &hellip; Each Module should be designed to exist as a standalone component. In doing so, the page will be more flexible.

	4. _states.scss

		Layout and design for page elements in a certain state.

		> For example, an accordion section may be in a collapsed or expanded state. A message may be in a success or error state.

	5. _theme.scss

		If your site uses multiple themes, or you plan to in the future: separate all style rules that are specific to that theme in this file.

		Like that, you could easily switch themes by creating _themeA.scss, _themeB.scss, &hellip;

		> Theme Rules aren't as often used within a project and because of that, they aren't included as part of the core types.

		> It is probably self-evident but a theme defines colours and images that give your application or site its look and feel. Separating the theme out into its own set of styles allows for those styles to be easily redefined for alternate themes.



3. #### Responsive 320 and Up

	Style changes for print (_print.scss) and displays with high pixel density (e.g. retina displays on iPhone) (_2x.scss) go here.

	Along with style and layout changes for higher resolutions (_480.scss to _1382.scss) (responsive webdesign, maybe you've heard of it ;)

	1. _print.scss
	2. _480.scss
	3. _600.scss
	4. _768.scss
	5. _992.scss
	6. _1382.scss
	7. _x2.scss

	In these files you will find these comments:
	
		/* 480px and up rules */
		// Base rules
		// Layout rules
		// Module rules
		// State rules
		// Theme rules
	
	in order to help you keep coding according to the SMACSS principles.

	Notice the difference in comment styles here: `/* */` and `// `. In SASS, `/* */` comments will be compiled in the actual CSS, `// ` will not.

	By putting comments like `/* 480px and up rules */` at the top of every file, this comment will be rendered in your `main.css` file. With that, you can easily trace back which file a certain rule belongs to when you're debugging your code.



### Folder Structure

1. /css
	1. /fonts

		Font files go here (in css folder because they are part of **styling** the page)

	2. /img

		**Style** images go here (any image you link to in CSS like backgrounds etc.)

	3. /scss

		Sass files are here (see “CSS Structure” beneath)

2. /images

	**Content** images go here (any image you link to in HTML)

3. /js
	1. /coffee

		CoffeeScript goes here (/js/coffee/main.coffee compiles to /js/main.js)

	2. /vendor

		JavaScript plugins go here (e.g. jQuery, slider plugins, &hellip;)



### Things you *might* want to add

More info on these is coming.

- [picturefill.js](https://github.com/scottjehl/picturefill)
	Responsive images the right way, it’s syntax lies very close to the pending W3C proposal.

- [CSSComb](http://csscomb.com/)
	Not a plugin for this boilerplate but for your code editor. Sorts your CSS properties so your code is uniform everywhere without having to worry about it. This increases it's readability and by that, it's maintainability.



Have a question? [Tweet Baloo! (@baloobp)](https://twitter.com/baloobp)

**Legal stuff:** I'm a young frontend webdeveloper trying to make a contribution to the web, not a lawyer, so this stuff is new for me. No copyright infringement intended, nor do I give any guarantees for support or that this boilerplate is foolproof. When you launch your project using it, it is your responsibility to test everything (the code you use and the code you write) thoroughly. The packages mentioned at the beginning of this document are not created by me, and I hereby wish to thank all the people who contributed to them. If I used any of it illegaly, please contact me and I'll change it as fast as I can.
