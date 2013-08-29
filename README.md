CSSZeus version 0.1 - june 2013

ABOUT
========================================================================
This CSS Framework is designed for responsive/adaptive website layout
creation based on simplicity, compatiblity, and flexiblity. It has all
the required calculations done in "cheatsheet.pdf" you can get from the
site. You could design your layout with the use of the cheatsheet and
then implement that in an HTML file very fast and easy. feel free to add
mediaqueries for your custom styles to make your site more responsive.
In the CSS Framework you don't see any visual styles like '.error',
'.form', '.message' and so forth because CSSZeus is invented to make
design layouts easy, not for visual styles.

Please read this file completely. You may find something infinitely
useful.

FEATURES
========================================================================
1. Responsive layout (7 fluid grids: 2, 3, 4, 6, 8, 12, and 16 splits)
2. Addaptive layout (6 break points: @480, @720, @960, @1200, @1440,
  @1920 pixels)
3. Progressive Enhancement with delivering smaller images first.
4. We didn't use mediaquery or javascript for
  our basic layout implementation to make it more cross-browser
  compatible. The only use of mediaquery in this framework was for
  fluid.css because we believe fluid layout is for smart phones which
  support mediaqueries naturaly.
5. Since this framework is tested on many of browsers and sizes, it
  makes your life easy as an designer.
6. CSSZeus is easy to implement:
    - Just add main.css to your HEAD section,
    - Enable required modules by just removing 3 characters for each
      one,
    - And finally copy snippets to your BODY section.
7. This software is 100% free for commercial use. We believe the main
  feature of CSSZeus is its being opensource. Commit to git to help us
  to develope this project if:
    - you are able to write better codes,
    - you found a way to make TODO/ROADMAP/WISHES items possible,
    - you could do more tests or more subtle ones,
    - you could document it better,
    - you could publicize it more,
    - or even you have a good idea,
    - or anything else.
8. Implementation of adaptive images is made easy:
    - Just read the cheatsheet and find your required image placemnets,
    - Then make an image containing defferent versions of your graphical
      item placed at their specified spots.
9. Also image sprites are ready to use:
    - Merge adaptive images with the same tile size into a single image
      file according to the instruction descibed in the cheatsheet.
    - Then just add '.sprite-?' classes to each one which makes them
      show the specified image.
10. Complex layouts are easy to make too: Just ommit '.tilec' and append
  layouts continuesly into each other. The only important limitation is
  that inner tiles should be smaller than outer ones.
11. Usage of defferent splites side by side is possible as CSSZeus
  uses no container that limits your content column to be devided by
  a constant number.
12. Understanding the meaning of the tiles are very simple and easy:
  '.tile-xy' covers y/x of page width and its '.tilec' covers its width
  minus 20px. Pay attention to these points:
    a) Always, even in appended layout, calculate based on page width,
      not based on the width of the outer tag.
    b) Consider page width equal to the larger breakpoint smaller than
      current page width, not the real page width.
    c) Since 20 pixel margin is because of using '.tilec' in '.tile-xy',
      there is no margin when you are appending layouts but for the last
      '.tile-xy' that contains content.
13. No server side programming is required. There is no required CSS
  class for the first and the last columns of the content, and the tiles
  after covering the page width (or the width of the outer '.tile-xy')
completely will arrange at the next row for layouting.
14. Using vertical-align CSS property makes it possible for the tiles to
  make content alignment easier. Use of "display: inline-block" (instead
  of float) provides better content arrangement.
15. removing or changing margin and padding of '.tilec' is available,
  and won't damage the designed layout. But read more about it in the
  CAUTION section.
16. Included GZipped
17. Debug ready
18. Modular
19. Consider http://cssze.us as an example.

CAUTION
========================================================================
1. Don't change the margins, or the paddings of '.tilec' when it
  contains adaptive image because all the calculated sizes and
  placements in the cheatsheet will become wrong and unusable. But if
  you could calculate it again for your new modification, you are
  welcome to do so.
2. Add your text styles within '.tilec' and its inner tags as
  CSSZeus uses text CSS properties to arrange '.tile-xy's and adapts
  sizes of their outer tags. Also direction is one of these CSS
  properties.
3. If you are trying to make smaller versions of this framework for your
  own design by removing unused CSS rules or changing some other
  modifications for specific design use, follow these two best
  practices:
    a) Make sure you didn't remove any CSS rule attached for used tiles.
      You may need to pay more attention when you are modifying
      append.css.
    b) Change the name of CSS files of the framework or its directory
      to some name describing "this is a modified version for specific
      use, not general". And always keep an original complete version
      somewhere near the modified version.
4. We didn't gzip compress main.css because it may be modified to
  enable or disable modules. If you want to compress it, remember to
  recompress it after any modifications.
5. You are to comment out (using <!-- and -->, consider cssze.us as an
  example) any whitespaces between '.tile-xy's, its necessary for
  compatiblity.

LICENSE
========================================================================
  CSSZeus is a CSS framework providing some responsive web design tools.
  CSSZeus is free software and open source under GNU GPLv3 license.

    Copyright (C) 2013  Hadi Sadeqi

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>
  
  * If you want to contribute to the source code development contact us
  at github: https://github.com/HadiSadeqi/CSSZeus
  * If you want to contact the author, send an email to:
  hadi-sadeqi@cssze.us

INSTALL
========================================================================
To add this to your designed HTML document:
1. Copy files somewhere relative to your HTML document.
2. Add the following line to the HEAD section of the document before
  your custom CSS files and STYLE tags:
    <link rel="stylesheet" type="text/css" href="main.css"/>
  if you copied library files elsewhere change the 'href' attribute
3. Use snippets in the following section to design your HTML structure
4. To enable library modules edit the lines under "MODULES" at the
  begining of main.css and uncomment lines related to the modules you
  need.

SNIPPETS
========================================================================
1. for responsive layouts use:
  <body>
    <div class="tile-??">
      <div class="tilec">[your contents here]</div>
    </div>
  </body>
2. for adaptive layouts use:
  <body>
    <div class=”adaptive”>
      <div id="wrapper">
        <div id="adaptor">
          <a></a><b></b><b></b><b></b><b></b><b></b><a></a>
        </div>
        <div id="tiles">
          <div class="tile-??">
            <div class="tilec">
            [your contents here]
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
3. for responsive images use:
  <div class=”tile-??”>
    <div class=”tilec rspimg”>
      <img src=”[your image path here]”/>
    </div>
  </div>
4. for adaptive images use:
  <div class=”tile-??”>
    <div class=”tilec adpimg”><img src=”[your image path here]”/></div>
  </div>
5. for progressive enhanced adaptive images use:
  <div class=”tile-??”>
    <div class=”tilec adpimg vertical-??”
        style=”height: [your used height here];”>
      <img src=”[your image path here]”/>
    </div>
  </div>
6. for adaptive images with aspect ratio use:
  <div class=”tile-??”>
    <div class=”tilec adpimg (vartical|horizontal)-??”>
      <img src=”[your image path here]”/>
      <div class=”height-fix”></div>
    </div>
  </div>
Check out the cheatsheet in the site to see more snippets plus design
guide lines and calculated sizes.

TODO
========================================================================
[ ] - implementing adaptive background
[ ] - implementing responsive image
[ ] - testing and completing compatibilities
[ ] - adding javascript event for turnpoints

ROADMAP
========================================================================
[ ] - creating server side real time minifier
[ ] - creating javascript preprocessor

WISHES
========================================================================
[ ] - image load control using javascript
[ ] - implementing responsive background
[ ] - mobile first
