# Shopware

After the successful installation of CCM19 on your server or setup, you will get a javascript code in the dashboard of CCM19 (seen here below in the screenshot).

![CCM19 Backend Screen](../assets/10-01.png)

After that, switch to your Shopware installation. There you go in the top menu to the item **Settings** and then to **Plugin Manager**. There you search for the plugin **CCM19-Interation** and install it in your Shopware instance.

![Shopware Menu Structure](../assets/10-02-1.png)

Once the installation is complete you can paste the CCM19 code snippet into the field provided. Please note that the item "Block Google Analytics" should be switched active.

![Shopware Screen](../assets/10-02.png)

Then go back to CCM19. Call the cookie **_ga** and insert the following line in the source code of the [cookie](https://www.ccm19.de/integration/glossar/13-Cookies.html#13):

`<script src="/custom/plugins/SwagGoogle/Resources/frontend/js/jquery.google_analytics_plugin.js"></script>`

![CCM19 Backend Screen _ga Cookie](../assets/10-03.png)

This completes the setup and CCM19 should now be active in your store.