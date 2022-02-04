---
title: Themes
---

# Set up and use themes

CCM19 is completely themeable - that means you can customize the look of all elements of the frontend. You can try as many themes as you like.

If you click on the menu item "Themes" you will first see the overview of the existing themes.

![screenshot-1641895769313](../assets/screenshot-1641895769313.jpg)



Clicking on the **green** pencil icon will take you to the edit screen, the **red** recycle bin will delete your theme ( after asking ), clicking on the double **green** folders will copy the existing theme 

Clicking on the **blue** icon sets the theme as default for the frontend.

## Create new theme

If you want to create a new theme you can either click on the button "Create" or you can copy an existing theme and adapt it.

Copying is the recommended procedure by CCM19 - also for individual adjustments to existing themes. This way you always have a fallback at hand.

## Customize Layout / Theme

In each theme you can define the theme with the help of various buttons and setting options. In addition, you have the possibility to customize every visual detail with the help of CSS instructions. The complete frontend mask can be influenced by CSS.

![Theme-Edit-Dialog](../assets/screenshot-1641896393753.png)

**Use `!important` for the individual CSS settings in case of doubt to override settings of your content management system.** In the interface you can set a lot of things. The settings you see here result in the following frontend.



## Preview

The Preview button allows you to preview the frontend widget. The click will not open your page but a page inside the CCM19 admin area. A reload is required after any change to the layout. The widget is fully functional - that means you can visually customize and test all elements of the widget.

In the background your current start page is always loaded as a screenshot so you can see the effect directly.

![screenshot-1641897784213 (1)](../assets/screenshot-1641897784213%20(1).jpg)

Preview with widget.



The buttons and background colors you set in the administration arrive directly in the frontend. You can also visually customize the links "Imprint" and "Privacy Policy".



## Buttons &amp; Settings

Furthermore, there are the following setting options:

### Position

Here you position the cookie banner on the website. You can choose the following positions:

* center
* top
* bottom
* bottom left
* bottom right

### Selection type

You can select whether the settings in the banner for categories and individual embeddings are displayed with checkmarks or buttons:

#### Checkmark

![screenshot-2020.09.29-13_53_33-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_53_33-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

#### switch

![screenshot-2020.09.29-13_54_35-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_54_35-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Of course, you can adjust the colors via the individual CSS settings.

### Show categories in main window

This option places all categories in the main window for quick selection.

* A new "Save" button appears next to "Accept All" and "Reject". (if the latter is active)
* To deal with the widget space, the "Settings" button is removed and replaced with a simple text link below the remaining buttons.

  

  ![screenshot-2020.09.29-13_56_09-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_56_09-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

### Blocking

Blocking means that - as you can see on the screenshot - the page is darkened and blocked in the background. Only when a visitor has definitely decided whether to accept the [cookies](https://www.ccm19.de/glossar/13-Cookies.html#13) or not, he will be allowed on the page.

### Show settings icon

If this checkmark is set, a settings icon will be displayed on the website via Javascript after the cookie banner has been confirmed. In this way, the revocation option required by the GDPR and the TTDSG can be provided easily and without further intervention on the page. The icon is placed in the bottom left corner by default.

![screenshot-2020.09.29-13_59_03-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-13_59_03-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)



### Settings icon opens..

Here you set which window a click on the settings icon should open; the 1st or the 2nd layer of the widget, i.e. the general home view or the detail view with the corresponding selection.

### "Do not Track" respect

If this setting is enabled, then the "Do not Track" (DNT) setting in the browser is automatically respected and implemented - i.e. no cookie banner is displayed, but only technically necessary elements are loaded directly if the visitor has enabled DNT in his browser.

However, it should be noted that this setting is usually disabled in most browsers and is already considered obsolete by some browsers.

### Show only in the EU

With this setting you can specify that the cookie notice is only displayed to visitors from the EU. The resolution is based on the visitor's IP used and therefore cannot be 100% accurate. For visitors from other countries, all cookies will be enabled unless the visitor signals "Do Not Track" and "Respect Do Not Track" has been enabled.

This product contains GeoLite2 data from MaxMind, available at [https://www.maxmind.com](https://5f3c395.ccm19.de/app/public/themes/&amp;guot;https://www.maxmind.com&amp;guot;).

### Tamper protection

This setting prevents simulated clicks on the Accept buttons in order to protect the user's cookie selection and thus strengthen your legal position when submitting the Consent.

Unfortunately, some scripts like "fastclick" that interfere with finger touch and mouse click processing can trigger this protection. If you use such a script, please check if you really need it and if the cookie dialog is still usable in the usual mobile browsers. Otherwise it may be necessary to disable the tamper protection.


**Do not disable this feature unless you are sure it is absolutely necessary. This could weaken your legal position when proving that consent was given

## Main window buttons

Here you can specify the order and selection of the buttons in the main window of the cookie banner.

Additionally, with the "Show close button" setting, a ✖ can be displayed in the upper right corner of the banner.
Clicking on it temporarily closes the cookie dialog until the browser tab is closed and only technically necessary cookies are loaded.

Notice:

According to TTDSG and DSGVO, there needs to be an equivalent option in a Consent widget to reject or cancel the cookies as to accept the cookies.
Therefore, it is automatically ensured that the Settings button is always active and the Reject button is active as soon as the Accept All button is activated.

In the exceptional case that you can comply with the relevant regulations for your target markets without a reject button, the latter security feature can be disabled in the "Developer Settings".

## Categories main window

Here you can define the functionality in the categories window (2nd level) of the cookie banner.

### Show "Accept All" button in the Categories window

With this setting, an additional "Accept All" button will be displayed in the Categories window.

![screenshot-2020.09.29-14_03_37-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-14_03_37-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

### Show all off/unselect buttons

![screenshot-1641902729730](../assets/screenshot-1641902729730.jpg)

If you check the box here, a corresponding selection will be offered, allowing a visitor to enable/disable all embeddings at once.

### Extra footer with links to imprint &amp; co.

![screenshot-1641902822676](../assets/screenshot-1641902822676.jpg)

If this checkmark is set, a footer with links to imprint and privacy &amp; co. is also shown in the 2nd level.

Not active by default.

### Logo of the page operator

Here you can upload a logo for the cookie banner. This will be displayed in the cookie banner above the text. By default, no logo is displayed.

If you have already uploaded a logo and want to delete it again, click on the arrow to the right of "Select file", then on "Reset image" and finally on Save.

### Show logo

This allows you to set whether the logo should be displayed in the cookie banner.

### Remove Powered By CCM19

By default, the cookie banner links to the CCM19 website in the bottom right corner with the text "Powered by CCM19".
This link can be removed by checking this box.
However, this is only possible if a whitelabel license for this installation has been purchased before.

### Colors

Here you can set the colors for the various buttons and backgrounds in the frontend - please note that frames are also partially dependent on this, if you set a white frame on a white background with white text, you will of course no longer see anything. It is best to check each change once in the frontend by calling the overlay again!

Please note that the contrast for the colors should also meet certain minimum requirements to achieve a certain level of accessibility.
To help with this, the contrast ratio between text and background is displayed to the right of the color settings.

![screenshot-1641902924696](../assets/screenshot-1641902924696.jpg)

That the contrast is high enough is shown by color. For the buttons, for example, a measure of 5:1 should be reached at least. If the number is red, the contrast is too low.

Please note that the contrast indicators must be green if you use TCF / IAB.

### CSS

Here you can enter completely individual CSS - for the individual elements please have a look at the page inspector of your browser. In case of doubt you have to overwrite settings by `!important` - **Example:**

``css
.ccm-root button {
    border:1px solid #c2bcbc 
}
.ccm-control-panel--purpose &gt; input[type="checkbox"] + label {
	color:#ccc;
} 
.ccm-modal--footer {
    background-color:#26282f 
} 
 
```

### Custom CSS iframe blocker

Here you can assign individual CSS instructions for the iframe blocker, e.g. for special background images.
To make it easier to set targeted CSS, the blocked domain is set as a CSS class on the HTML element.

Example:
- Blocked is ``https://www.google.com/maps/...``
- In the iframe, the HTML element gets the class as follows: ``domain--www-google-com``
- Possible CSS:

~~~``css
```
html.domain--www-google-com body {
    background-image: url('google-maps-placeholder.jpg');
}
html.domain--www-facebook-com body {
    background-image: url('facebook-placeholder.jpg');
}
~~~
