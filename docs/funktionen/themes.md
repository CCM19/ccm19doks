---
title: Themes
---

# Set up and use themes

CCM19 is completely themeable - that means you can customize the look of all elements of the frontend. You can try as many themes as you like 

If you click on the menu item Themes you will first see the overview of the existing themes.

![screenshot-1641895769313](../assets/screenshot-1641895769313.jpg)



Clicking on the **green** pencil icon will take you to the edit screen, the **red** trash will delete your theme ( after asking ), clicking on the double **green** folders will copy the existing theme 

Clicking on the **blue** icon sets the theme as default for the frontend.

## Create new theme

If you want to create a new theme you can click on the button "Create" or you can copy an existing theme and adapt it 

Copying is the recommended procedure by CCM19 - also for individual adjustments to existing themes. This way you always have a fallback at hand.

## Customize Layout / Theme

In each theme you can define the theme with the help of various buttons and setting options. In addition, you have the possibility to customize every visual detail with the help of CSS instructions, the complete frontend mask is accessible via CSS.

![screenshot-1641896393753](../assets/screenshot-1641896393753.jpg)

**Use in the individual CSS settings in doubt !important to overwrite settings of your CMS system. ** In the interface you can set some things. The settings you see here result in the following frontend.



## Preview

The Preview button allows you to preview the frontend widget. The click will not open your page but a page inside the CCM19 admin area. A reload is required after any change to the layout. The widget is fully functional - that means you can visually customize and test all elements of the widget.

In the background your current start page is always loaded as a screenshot so you can see the effect directly.

![screenshot-1641897784213 (1)](../assets/screenshot-1641897784213%20(1).jpg)

Preview with widget.



The buttons and background colors you set in the administration arrive directly in the frontend. You can also customize the imprint and privacy policy links.



## Buttons &amp; Settings

Furthermore there are the following buttons:

### Position

Here you position the overlay in the frontend, you can choose the following settings:

* left
* right
* top
* bottom
* center

### Selection type

You can define checkmarks or switches for the view in the categories and individual embeddings.

#### Checkmark



![screenshot-2020.09.29-13_53_33-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_53_33-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

#### Switch

![screenshot-2020.09.29-13_54_35-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_54_35-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Of course, you can adjust the colors using the individual CSS settings.

### Show categories in main window

This option places all categories in the main window for quick selection.

- A new "Save" button appears next to "Accept All" and "Reject". (if the latter is active)

- To deal with the widget space, the "Settings" button is removed and replaced with a simple text link below the remaining buttons.

  

  ![screenshot-2020.09.29-13_56_09-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_56_09-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

### Blocking

Blocking means that as you can see on the screenshot the page is blocked in the background and only when a visitor has definitely decided whether to accept the [Cookies](https://www.ccm19.de/glossar/13-Cookies.html#13) or not he will be allowed to enter the page.

### Show settings icon

If this checkmark is set, a settings icon will be set via Javascript after the consent over the page. In this way, the revocation required by the GDPR can be set as easily as possible. The icon is placed by default in the bottom left corner.

![screenshot-2020.09.29-13_59_03-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_59_03-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)



### Settings icon opens

Here you set which window the icon should open, the 1st or the 2nd layer of the widget, i.e. the general home view or the detail view with the corresponding selection.

### Do not track respect

If this setting is checked - then the Do not Track setting in the browser is automatically respected and implemented - i.e. no tracking cookies are set, only technically necessary elements are loaded.

However, please note that this setting is usually disabled in most browsers.

### Show only in the EU

With this setting you can specify that the cookie notice is only displayed to visitors from the EU. The resolution is based on the visitor's IP used and therefore cannot be 100% accurate. For visitors from other countries, all cookies will be enabled unless the visitor signals "Do Not Track" and "Respect Do Not Track" has been enabled.

This product contains GeoLite2 data from MaxMind, available at [https://www.maxmind.com](https://5f3c395.ccm19.de/app/public/themes/&amp;guot;https://www.maxmind.com&amp;guot;).

### Tamper protection

Prevents simulated clicks on the Accept buttons to protect the user's cookie selection. **Do not disable this feature unless you are sure it is absolutely necessary. This could weaken your legal position in proving that Consent was granted



## Main window buttons

According to TTDSG and DSGVO, there needs to be an equivalent option in a Consent Widget to reject or cancel the cookies as to accept the cookies.

Therefore it is checked here if at least these 2 buttons are active and also the reject button is activated.

With the settings you define which buttons come to which position.



### Show "Accept all" button in the Categories window

With this setting, the "Accept All" button will be displayed additionally in the Categories window.

![screenshot-2020.09.29-14_03_37-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-14_03_37-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)



### Show all off/unselect buttons

![screenshot-1641902729730](../assets/screenshot-1641902729730.jpg)

If you set the checkmark here a corresponding selection will be offered in the 2nd layer. The check mark is not active by default.

### Extra footer with links to imprint &amp; co.

![screenshot-1641902822676](../assets/screenshot-1641902822676.jpg)

If this check mark is set, an additional area is also displayed in the 2nd layer where the links to imprint and privacy &amp; Co. are displayed.

Not active by default.

### Logo of the site operator

Here you upload your logo which will be displayed in the frontend - your website - in the overlay. In the screenshot above you can see the logo of ccm19 there - you can exchange it for yours.

### Show logo

Here you can set whether the logo should be displayed in the frontend overlay.

### Remove Powerd By CCM19

This is about the link in the frontend overlay that is on the bottom right. This is a link that links to the CCM19 page. This can be removed by checking this box. However, this is only possible if a whitelabel license for this installation has been purchased before.

### Colors

Here you can set the colors for the different buttons and backgrounds in the frontend - please note that frames are also partially dependent on this, if you set a white frame on a white background with white text, you will of course not see anything. It is best to check each change once in the frontend by calling the overlay again!

Please note that the entries for the colors must also meet certain minimum contrast requirements to achieve a certain degree of accessibility.

![screenshot-1641902924696](../assets/screenshot-1641902924696.jpg)

That the contrast is high enough is shown next to the color ranges, a measure of 5:1 should be reached at least. If the number is red, the contrast is too low.

Please note that these areas must be green if you use TCF / IAB.

### CSS

Here you can enter completely individual CSS - for the individual elements please have a look at the page inspector of your browser. In case of doubt you have to overwrite settings with "!important" - **Example:**

`` css
.ccm-root button  
{ 
    border:1px solid #c2bcbc 
} 
.ccm-control-panel--purpose &gt; input[type="checkbox"] + label 
{ 
	color:#ccc;
} 
.ccm-modal--footer 
{ 
    background-color:#26282f 
} 
 
```

### Custom CSS iframe blocker

Here you can assign individual CSS instructions for the iframe blocker, special background images, etc. You can assign the blocked domain as a class to then define more specific CSS 
Example:
\- Blocked is ``https://www.google.com/maps/...``
\- In the iframe the HTML element gets the class e.g. as follows: ``domain--www-google-com``
\- Possible CSS

~~css
```
html.domain--www-google-com body {
    background-image: url('google-maps-placeholder.jpg');
}
html.domain--www-facebook-com body {
    background-image: url('facebook-placeholder.jpg');
}
~~~