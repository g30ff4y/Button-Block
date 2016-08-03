# Button-Block
A block for making buttons in the UMT Ponderosa Template in the Cascade CMS.
The following was originally documented with Bitbucket markdown intended for internal use and is provided here for reference.

Updated 7/12/2016 @g30ff4y

[TOC]

##Overview
At it's base, the button block is simply a layout tool for links.  By default the Button Block displays links as "buttons."  This block allows for numerous types of customization and layout options based on the Bootstrap 12-column grid approach.

###Examples
* [Spectral Fusion Designs Portfolio](http://cas.umt.edu/sfdesigns/portfolio/default.php) (In Development as of Spring 2016)
* [Crown Reporting Project](http://jour.umt.edu/crown/)
* [UM Paleontology Center](http://hs.umt.edu/paleo/links/default.php)
* [Geosciences Water/Earth Buttons](http://hs.umt.edu/geosciences/) 

##Implementation
###Connecting the Block
1. Browse to the starter block: SFD - New Templates > Blocks > blankSiteBlocks > Button Block
2. Select **Copy** from the fly-out menu to the right of the file name.
     1. Rename the block in the **System Name** line
     2. Select a new **Parent Folder** in the site you are working on.
     3. Click **Submit**. You will be automatically be taken to your new site.
3. Go to the page you need the buttons on.
     1. Click the **Edit** tab.
     2. Click **Outputs** in the blue bar below the Edit Tab.
     3. Select where you want the buttons to appear on the page; either above or below the main page content.  This will most likely be in either **DEFAULT-AFTER** or **DEFAULT-BEFORE** System Regions:
          1. **BLOCK:** Search for the button block you just copied.
          2. **FORMAT:** Search, then **Browse** to SFD - New Templates > scripts > Block Scripts > sfdBlockScripts > Button Block

###Adding Links
1. Edit the block you just connected.
2. If you need a Heading for the block add one in the **Block Heading** line. This text will be formatted as a Heading Level 2 (H2).
3. Next you will have the option to build groups (rows) of individual buttons (columns).  You can add up to six buttons per row. Use the standard Cascade Plus( ![Cascade+.png](https://bitbucket.org/repo/G9KG4E/images/663325588-Cascade+.png) ) and Minus( ![Cascade-.png](https://bitbucket.org/repo/G9KG4E/images/1118161342-Cascade-.png) ) signs to add/delete either Groups or Buttons. Groups can be reordered with the black up ( ![Cascade-UP.png](https://bitbucket.org/repo/G9KG4E/images/125490116-Cascade-UP.png) ) and down ( ![Cascade-DOWN.png](https://bitbucket.org/repo/G9KG4E/images/3844159667-Cascade-DOWN.png) ) arrows next to the add/delete options.
4. Groups also have an option for a Heading.  Use the **Button Group Heading** line. This text will be formatted as a Heading Level 2 (H2).  
5. Buttons can also be reordered within in a group with the black up and down arrows next to the add/delete options. Each button will have these fields to enter:
     1. **Button Label:** This is the title of the link, formatted as a Heading Level 3 (H3). You may include inline HTML elements like the break tag `<br />`. If you need to use a special character like the ampersand (&), use the HTML code to display the special character `$amp;`.
     2. **Link:** The link can be either internal (part of the current site) or a separate external site:
          1. **Internal Link:** Click search to browse to the page on the site to link to.
          2. **External Link:** Type specific url here, include http://
     3. **Button Image:** Browse for image to attach to the button if needed.
     4. **Type of Image**
          1. **Functional/Logo:** inserts the 'Button Label' as the alt text.
          2. **Conetexual:** allows you to add a custom alt description. For help with alt text descriptions refer to the Web AIM [Alternative Text Article](http://webaim.org/techniques/alttext/).  
     5. **Custom Button Class:** Add a class to the button. This custom class is passed to the <a> tag of the markup structure. Multiple classes can be added using spaces to separate the class names.
##Setup
###Advanced Button Setup
Use these additional parameters to configure the buttons individually.

1. **Render As:**  Use these check boxes to render the button as a gradient button and/or button with text content.  
     1. **Gradient Button Options:** Activates when **Gradient Button** is checked. Chooses the color of the Gradient Button. These color styles follow the "Featured Links" style of buttons on the Ponderosa Template Setup Block.
     2. **Button Content Text:** Activates when **Content Button** is checked.  Use this area to include a very short paragraph of text on the button.
     3. **Image Button:** helps to style buttons where the image is used as the button link.
3. **Custom Layout:** This selection/custom text field is activated in the Group Setup area. The layout override is a very powerful selector which works as a bridge between v2 and v3 of the Bootstrap Framework. Use this line to select the span number for the button (Bootstrap v2 by default). 
     * If you are using offsets you will need to rewrite the span class with the offset. Ex: span3 offset3.  
     * For Bootstrap 3 classes write the combinations of different classes.
     * You may also write custom classes here in addition to Bootstrap column classes.  *Buttons may not work properly if column classes are not used in this field.*
     * Make sure all button widths in a group add to 12.

###Button Group Setup
Use these parameters to control how each row of buttons behaves.

1. **Button Layout:** There are two basic layouts based on how the buttons fit or fill the parent element. Note that groups of 5 or 6 buttons will behave the same in each layout option. These are based on uniform button sizes based on the 12 column layout. 
     1. **Fill Content Area:** This makes each button the largest possible column width to reach the width of the parent element.
     2. **Fixed Button Width Centered:** This makes each button the same width and centers the button in the parent element.  The markup here is fixed to span2 with appropriate offsets to center the buttons.
     3. **Custom Layout:** This selector enables the **Custom Layout** tool. This selector gives total freedom of the block on a per group basis if you wish to use non-uniform button widths on a row. If you use this feature the Layout Overrides section on each button will be active allowing for a selection of any column width of each button (Bootstrap 2 Spans by default).  
2. **Height Equalize Row:** Select or deselect this to include or exclude the row from the height equalizer.
3. **Custom Button Group Class:** Add a class to the group or row of buttons. This is passed to the same div as the row, so you don't have to modify Bootstrap default behavior.

###Button Block Setup
This area has parameters that set up the entire block.

####Custom Block ID
Use an ID regardless if you are only using a single button block on a site.  The will insure that any custom styling from the first instance will not affect any future instances.

####Height Equalizer
Use the radio buttons to connect or disconnect to the Ponderosa Height Equalizer. *The height equalizer script is maintained by UM IT and may change without notice.*

1. **Yes:** The Height Equalizer makes all buttons in all groups the same height and is enabled by default.
2. **Manual:** This allows for more control of connecting to the Height Equalizer. When this mode is active a check box will appear in the Button Group Setup section for each row. Check the box to height equalize the buttons on that row. If multiple rows are being height equalized, buttons will equalize to the tallest overall button on the selected rows.  
3. **No:** Selecting "No" will not connect the buttons to the Height Equalizer. Tip: If you are building non gradient, image buttons (Crown Reporting) you will need to select "No".    
4. **Exclude Require jQuery:** Select this option if you are connecting the Button Block to a page that is already using another block element that connects to the Height Equalizer, like Tiles.
  
####Include Page Container
Use this check box to place the buttons and optional additional content in a container div to match native page content on the Ponderosa Template. Checked by default, but in rare cases exists if the button block does not need to be in the regualr page container.
###Other Features
* **Additional Content:**  Add some content above or below the buttons with the appropriate WYSIWYG editor.

##Customizing
###Anatomy of a Button
The button block follows Ponderosa Featured Links Button markup from the Setup Block, but also adds ways for more customization with styling options.

####Default Button
```
#!html

<div id="custom-block-id" class="row-fluid separatedButtons"> <!-- Block Wrapper Div -->
     <div class="row-fluid button_groups"> <!-- Button Groups Wrapper Div -->
          <div class="row-fluid button_row featured_site_links row1 custom-button-group-class"> <!-- Button Group Row Wrapper -->
               <div class="featured_link bootstrap-classes"> <!-- Button Wrapper -->
                    <a class="btn custom-button-class" target="_blank" style="display: block; white-space:normal;" href="link url"> <!-- Link -->
                         <div class="btn-content">
                              <span class="button-label feature_title"> <!-- Button Label Wrapper-->
                                   <h3>Button Label</h3> <!-- Label Text -->
                              </span>
                         </div>
                    </a>
               </div>
          </div>
     </div>
</div>
```
####Gradient Button
```
#!html

<div class="featured_link bootstrap-classes button-count"> <!-- Button Wrapper -->
     <a class="btn grad_button featurebutton_*color custom-button-class" target="_blank" style="display: block; white-space:normal;" href="Link url"> <!-- Link -->
     <!-- notice the extra classes of grad_button and featurebutton_*color can be used to target the gradient background of the button -->
          <div class="btn-content"> <!-- Button Content Wrapper -->
               <span class="button-label feature_title"> <!-- Button Label Wrapper -->
                    <h3>Gradient Button</h3> <!-- label text -->
               </span>
          </div>
     </a>
</div>
```

####Image Button
```
#!html

<div class="featured_link bootstrap-classes button-count img-btn"> <!-- Button Wrapper -->
     <a style="white-space:normal; display:block;" href="Link url" class="btn  img-btn "> <!-- Link -->
          <div class="row-fluid btn-content"> <!-- Button Content Wrapper -->
               <span class="row-fluid"> <!-- Places image on it's own row -->
                    <img src="Image Source" alt="dependent on type of image">
               </span>    
               <span class="image_label feature_title row-fluid"> <!-- Button Label Wrapper -->
                    <h3>Image Button</h3> <!-- label text -->
               </span>
          </div>
     </a>
</div>

```

####Content Button
```
#!html
<div class="featured_link bootstrap-classes"> <!-- Button Wrapper -->
     <a href="Link url" class="btn custom-button-class" style="display: block; white-space:normal;"> <!-- Link -->
          <div class="btn-content"> <!-- Button Content Wrapper -->
               <span class="row-fluid"> <!-- Places image on it's own row -->
                    <img src="Image Source" alt="dependent on type of image"/>
               </span>     
               <span class="image_label feature_title"> <!-- Button Label Wrapper -->
                    <h3>Content Button</h3> <!-- label text -->
               </span>
               <p class="btn-text">Text content for button</p> <!-- content text -->
          </div>
     </a>
</div>
```

###CSS Tips and Tricks
####Custom Classes and ID
If you plan to customize the buttons, it is strongly encouraged to use custom classes on the buttons and the button groups.  This way you are sure to not interfere with classes that are used for structure; ex: anything that starts with the word "feature."

The Custom ID on the block can go a long way in simplifying your CSS customization.  This way you can target each block individually to behave differently.

If you are having trouble, use firebug to target the element and experiment with different ways various CSS parameters will effect different parts of the button 

####Examples
#####Word Wrap

As of the 7/30/15 release of the Button Block, word wrap is handled inline by default.
```
#!css
.feature_title {
    white-space: normal;
}
```
#####Flat Button
```
#!css
.featured_site_links .featured_link .featurebutton_*yourcolor {
    background-image: none;
}
```
