# Baloo Boilerplate
## Only the [bare necessities](http://www.youtube.com/watch?v=TcglnY_xGfc)

Baloo Boilerplate is [HTML5 Boilerplate](http://html5boilerplate.com/) & [320andup](http://stuffandnonsense.co.uk/projects/320andup/) combined, stripped down and organized according to the [SMACSS](http://smacss.com/) principles using [SASS](http://sass-lang.com/).

Also, it uses [prefixfree](http://leaverou.github.com/prefixfree/) by [Lea Verou](https://twitter.com/LeaVerou) so you don't need to wory about writing brow

What it tries to do is: Give you what you **will** use so you can add what you *want* to use later on, instead ove giving you a whole lot of things you **might** use so you need to *remove* them afterwards, or bear (pun intended) with a messy project folder.



### CSS Structure
All the sass files are in the /css/scss folder and are imported in main.scss, which will compile to /css/main.css, in order to keep things organized.

The structure is as follows:

1. #### Reusable components
	1. _fonts.scss
		
		Put your @font-face imports here. Fonts go in /css/fonts since they're part of the *style*, not the *content*

	2. _variables.scss

		Variables go here (e.g.: colors for your color scheme, baseline height for calculations, &hellip;)

	3. _animations.scss

		CSS3 animations get their private parking spot.

	4. _mixins.scss

		and so do SASS mixins.

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

		> Theme Rules aren't as often used within a project and because of that, they aren't included as part of the core types.

		> It is probably self-evident but a theme defines colours and images that give your application or site its look and feel. Separating the theme out into its own set of styles allows for those styles to be easily redefined for alternate themes.

3. #### Responsive 320andup

	Style changes for print (_print.scss) and displays with high pixel density (e.g. retina displays on iPhone) (_2x.scss) go here.

	Along with style and layout changes for higher resolution resolutions (_480.scss to _1382.scss) (responsive webdesign, maybe you've heard of it ;)

	1. _print.scss
	2. _480.scss
	3. _600.scss
	4. _768.scss
	5. _992.scss
	6. _1382.scss
	7. _x2.scss

	In these files you will find following comments:
	
		/* 480px and up rules */
		// Base rules
		// Layout rules
		// Module rules
		// State rules
		// Theme rules
	
	in order to help you keep coding according to the SMACSS principles.

	Notice the difference in comment styles here: `/* */` and `// `. In SASS, `/* */` comments will be compiled in the actual CSS, `// ` will not.

	By putting comments like `/* 480px and up rules */` at the top of every file, they will be rendered in your `main.css` file, so you can easily trace back which file a certain rule came from when you're debugging.


Have a question? [Follow @baloobp! on Twitter](https://twitter.com/baloobp)

**Legal stuff:** I am a young webdeveloper trying to make a contribution to the web, not a lawyer. No copyright infringement intended, nor do I give you any guarantee for support or that this boilerplate is foolproof. When you launch your project using it, it is your responsibility to test everything (the code you use and the code you write) thoroughly. The packages mentioned at the beginning of this document are not created by me, and I hereby wish to thank all the people who contributed to them. If I illegaly used any of it, please contact me and I'll change it as fast as I can.
