# TYPO3

To install our Cookie Consent Manager for your TYPO3 site, simply follow the steps below:

## Select Dashboard in CCM19

After successful installation of CCM19 on your server or setup you will get a javascript code.

![CCM19 Backend Screen](../assets/10-01.png)

## TYPO3 Backend

Afterwards, log in to the TYPO3 backend as usual. Once there, open the menu item "Template".

![Typo 3 Template Menu](../assets/TYPO3/typo3_01.png)

In the menu item "Template", open the template, which is currently active for your website.

![Typo 3 Template Tools](../assets/TYPO3/typo3_02.png)

Once in this template, edit the setup.

![Edit Typo 3 Template](../assets/TYPO3/typo3_03.png)

In the setup insert now the following code (Attention: This code may not be correct with different TYPO3 version):

``html
page.headerData.1 = TEXT
page.headerData.1.value (
   <script src="https://www.xy.de/ccm19/public/ccm19.js?apiKey=123a&amp;domain=123&amp;lang=de_DE" referrerpolicy="origin"></script>
)
```

Then just save this change and empty the cache of your TYPO3 page.

![Edit Typo 3 Template](../assets/TYPO3/typo3_04.png)

This completes the setup and CCM19 should now be active in your site.