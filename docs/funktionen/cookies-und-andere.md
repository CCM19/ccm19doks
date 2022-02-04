# Cookies &amp; Embeddings

With CCM19 you can give your visitors the opportunity to decide for themselves what data is collected about them.

For this to work, all relevant data must be available in CCM19 and the bindings must be tested. Even if CCM19 can do a lot of automatic tests - it is always up to the operator to check all functions.

You can find an overview of existing bindings under the menu item "Bindings &amp; Cookies".

## Overview about the existing bindings

![screenshot-2020.09.29-16_01_49-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-16_01_49-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Here you can see listed which embeds are used on your site. You can see at a glance which bindings are active, what they are called and who they are from.

Click on the green icon to enter the edit mode, click on the red trash can to delete an entry.

The button "Create new entry" leads you to the creation mask. Usually the blue button "Select entry from database" makes more sense. Here your CCM19 instance connects to our central database and lists the available entries.

## Available bindings

![screenshot-2020.09.29-16_05_01-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.29-16_05_01-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Here you see listed the entries from our database that are available to you. Click on the green button Apply to transfer the data into the edit mask.

Sometimes an adjustment to your company or website is necessary, you should check this so that everything is legally on the safe side.

## Edit mask of the embeddings

![screenshot-1641903648518](../assets/screenshot-1641903648518.jpg)

In the edit mask you can enter the following:

### Name of the integration / inclusion

The name of the integration - this can be Matomo, for example. You should use a meaningful name here.

### Purpose

Here the categories already mentioned above appear again. You can assign any entry to any category. Please note, however, that you must observe the legal framework. Facebook Pixel, for example, will hardly be categorized under technically necessary. For an exact legal classification you should consult a lawyer in any case.

### Activate

Here you activate the entry so that it can also be checked off in the frontend

### Source code of the integration

In the source code of the embedding you have to insert the code by which the embedding is generated. In our example, this would be Matomo. \*\*If you insert a code, it must be unique and must not be entered in any other cookie. \*\*

&gt; **In addition, it must be removed from the direct web page text, otherwise you would include the code twice. This leads to technical problems!**

#### Example Matomo

``html
<!-- Matomo / voll anonymisiert, Daten verbleiben auf Firmeneigenen Servern -->
 <script type="text/javascript">
    var _paq = window._paq || [];
    /* tracker methods like "setCustomDimension" should be called before "trackPageView" */
    _paq.push(["setDocumentTitle", document.domain + "/" + document.title]);
    _paq.push(["setCookieDomain", "*.www.xy.de"]);
    _paq.push(["setDomains", ["*.www.xy.de"]]);
    _paq.push(['trackPageView']);
    _paq.push(['enableLinkTracking']);
    (function() {
        var u="//analytics.xy.com/";
        _paq.push(['setTrackerUrl', u+'matomo.php']);
        _paq.push(['setSiteId', '1']);
        var d=document, g=d.createElement('script'), s=d.getElementsByTagName('script')[0];
        g.type='text/javascript'; g.async=true; g.src=u+'matomo.js'; s.parentNode.insertBefore(g,s);
    })();
 </script>
<!-- End Matomo Code -->
```

### Provider

The provider - here you must enter the company name of the provider offering the script. In our case it would be your company. You can also enter the complete address of the company here.

### Block scripts

Here you can block scripts that are embedded in the source code of your page by CCM19. If you use e.g. Matomo: Then enter in the field e.g. "matomo" - then every Javascript on your page will be blocked that contains these characters (string) and the script will not be executed as long as no consent was given.

This way you don't have to rebuild your page.

&gt; But please note the following:
&gt
&gt; The browser manufacturers are always trying to load all content as fast as possible, so it can happen that despite the correct blocking a browser loads a file anyway, the loading process was triggered faster than it can be blocked by CCM19. This is a matter of milliseconds. No cookie manager in the world can stop this process, because it is **not** possible to interfere with the internal processes of the browser.
&gt
&gt; If you want to be on the safe side, you have to integrate the scripts via the mask "Source code of the integration" into the page after successful consent and rebuild your page.

### Script loader

If you use the function "Block scripts that contain the following text", your scripts can stay on the website and CCM19 will block them while building the page. However, all current browsers load these resources before CCM19 intervenes, despite correct integration, because they are loaded by automatic preloading by the browsers. Neither CCM19 nor other tools can prevent this, as the download of the resources starts before the execution of scripts by browsers begins.

To prevent this after all, you can assign our CCM19-specific value for the `type` attribute to your scripts. By this adjustment, a browser will now no longer recognize the corresponding script as Javascript code to be executed and will refrain from processing it at first.

CCM19 is able to process scripts of this type and releases the script for loading, provided that according to your CCM19 configuration nothing speaks against it.

**Our type attribute looks like this: `type="text/x-ccm-loader"`**

Use this value for each `script` tag on your page that should be blocked or unblocked and reloaded according to this function. For example, it will look like this:
`html
<script src="https://your.site/script.js" type="text/x-ccm-loader"></script>
```

#### Group for the script loader

If you have manually equipped your scripts on the website with our type attribute `type="text/x-ccm-loader"`, you can use this function to group these scripts and block them uniformly.

You define the group name per inclusion yourself and add this to the corresponding script as well. The group name always consists of the following part: `data-ccm-loader-group="example_name"`.

Together with the `type` attribute it then looks like this:
`html
<script src="https://your.site/script.js" type="text/x-ccm-loader" data-ccm-loader-group="beispiel_bezeichnung"></script>
```

Enter the group name in the relevant inclusion under the item "Group for the script loader" to link the inclusion with the marked scripts of your website.

As soon as a page visitor allows such an inclusion, the grouped scripts will be reloaded.

### Enable iframes

&gt; For enabling via embeddings to work, you must enable the IFrame blocker via the **Iframes &gt; Enable Iframe Blocking** item.

Recently it is possible to enable iframes (e.g. from Youtube, Google Maps and Co.) via the cookie banner.

To enable iframes via the cookie banner, enter strings that appear in the IFrame in the "Block iframes containing the following text" field.

For example, for a Youtube iFrame, the string would be "youtube.com"

For a Google Maps iFrame, the string would be, for example, "maps.google.com"

Accepting the category will automatically unlock all corresponding IFrames.

**Please continue to observe the legal regulations regarding IFrames and the correct categorization

## Entries per language

![screenshot-2020.10.29-13_10_37-1603973437002](../assets/screenshot-2020.10.29-13_10_37-1603973437002.jpg)

For each language used, the following language-dependent content can still be created.

### Description

In the description, enter the task of the inclusion. Why is it set? What does this integration do?

### Privacy link

This is where the link to the provider's privacy policy belongs. You can usually find this when you go to the provider's website.

### What data is collected?

What data is collected exactly? Only the IP? Or also click data, browser data, logins, behavior, etc.? Find out exactly from the provider of the script and enter as precisely as possible what happens to the data. This is the only way to get informed consent from your visitors.

### For what purpose is the data collected?

Why are you collecting this data? What do you want to do with it? Conversion optimization? Improve user experience? Or just implement a shopping cart function?

### Legal basis

Here you define the legal basis on the basis of which you want to make this integration. In the case of tracking scripts, usually only "consent, Art. 6 para. 1 lit. a DSGVO" applies - consent of the visitor through an informed decision. So purely voluntary.

### Place of processing

Where the data is processed. Here is not only the address of your office but also where is the server located? Please also consider that you are currently not allowed to transfer data to unsafe third countries. Providers who export data to the USA are currently legally probably not possible (as of 29.09.2020).

## List of cookies and storage elements

![screenshot-2020.10.29-13_11_42-1603973502795](../assets/screenshot-2020.10.29-13_11_42-1603973502795.jpg)

Here are all cookies and storage elements listed that the script sets. You can add more elements by hand, because the automatic scan cannot always find all data. E.g. the scanner cannot find data for a logged in state. Also, the database hand-maintained by CCM19 may not be complete - always check the data carefully.

#### Name

The name in the browser - e.g. _ga for a Google Analytics cookie or _pk_id.\* for Matomo - the \* is a placeholder.

#### dyn.

This determines if it is a dynamic variable - e.g. _pk_id.\* will block all cokies that start with _pk_id. i.e. _pk_id.123 etc.

#### Memory type

How the data is stored in your browser.

#### Livetime / Expires

When does the memory entry expire automatically.

#### Value

What value does the cookie transport - usually it is cryptic data that is stored here.



## Google Consent Mode (beta)

![screenshot-1641904109779](../assets/screenshot-1641904109779.jpg)

Beta because it still has beta status at Google - not at CCM19. Google Consent Mode is a new functionality for websites that use Google Tag Manager to include Google services like Google Ads, Floodlight or Google Analytics.

If you use Google Tag Manager, please select which consent types for Google should be implied with this inclusion.

For more information on Google's Google Consent Mode (beta), please see here: [https://support.google.com/analytics/answer/9976101?hl=de](https://support.google.com/analytics/answer/9976101?hl=de)

## Exclude urls

![screenshot-1641904161415](../assets/screenshot-1641904161415.jpg)

Do NOT play out the embedding on these pages, this means that the currently selected embedding will not activate the embedding in tag manager mode resp. will not release it in block mode 

This can make sense under different circumstances 

Enter one URL per line. At the end you can use a * as a placeholder. Without placeholder the URL will be compared exactly! So please enter only complete and valid URLs.

Example: https://www.ccm19.de/data.html* affects

- https://www.ccm19.de/data.html
- https://www.ccm19.de/data.htmlx
- https://www.ccm19.de/data.html?var1=test

... and so on.

## Save

With a click on the Save button the data will be transferred to the CCM19 administration of your page and will be directly available for the frontend widget.Set cookies of your own page manually