# Dashboard

The domain dashboard. Here you land directly after you have selected a domain in the Domain Manager. In this dashboard some basic functions are listed.


![screenshot-1641854392504](../assets/screenshot-1641854392504.jpg)


## Quicksetup

If you click the link, you will be taken directly back to the onboarding for this domain. You can run through this as often as you like, but old data will always be overwritten.

## Include CCM19 in your page

The most important point at this point - here you will find the HTML snippet that you need to establish the connection between your site and CCM19.

Copy the entry that is listed there - as you can see here for example.

![screenshot-1641854392504 (1)](../assets/screenshot-1641854392504%20(1).jpg)

Of course you should use the entry from the interface and not the one here from the documentation :-)

In the mask you can select in which language the mask should be displayed, generally it is also possible that the mask reads the language of the visitor from the browser **and** there is the possibility to select the language in the frontend widget.


## Open configuration box again via link

You would like to give your visitors the possibility to change their mind later on and not allow analysis cookies after all? Simply insert the following HTML snippet:

``` html
<a href="#" onclick="CCM.openWidget();return false;">Open configuration box
</a>```

Thus, when clicking on this link, the configuration pop-up is opened again for the visitor.

Alternatively, if you cannot insert Javascript links, you can use the following target in a link: **#CCM.openWidget**.

``html
<a href="#CCM.openWidget">Open configuration box
</a>```

## Statistics

In the small statistic you get an overview about the usage of the CCM19 widget on the selected domain. It shows how often the widget was shown, how often the script was called and some more.

## Cookie used

The short list of cookies and bindings gives you a small overview about the used data on your site.
