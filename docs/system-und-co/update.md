# Updates

Through the update function you always get the latest and newest stable version of the CCM19 tool. In the changelog you can see what changes have been made.

![screenshot-2020.09.30-14_59_11-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-14_59_11-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)



## Automatic updates

Enabling the "Enable Automatic Updates" feature will automatically update your CCM19 system.



## Beta version

You have the possibility - absolutely on your own responsibility and **without** support - to participate in the beta channel. To do so, open the "Update" menu item and press the following keys on your keyboard in succession: <kbd>↑ ↑ ↓ ↓ ← → ← → B A</kbd>

The following entry will then appear:


![screenshot-2020.09.30-15_03_22-CCM19 - Cookie Consent Management Software](../assets/screenshot-2020.09.30-15_03_22-CCM19%20-%20Cookie%20Consent%20Management%20Software.jpg)

Select "Beta" from the select field and press Save. You are now in the beta channel for distribution of updates and upgrades.

# Errors after updates (very rare)

If cryptic error messages appear after an update the first step is to clear the cache -&gt; [edit cache](caching.md). This can happen in very rare cases when accesses go wrong in some way on the server.


Normally this is also done automatically after an update, but sometimes under certain conditions it comes to an abort - so that the cache can not be deleted completely. Then manual operation helps.

&gt; If it still doesn't work, you can try to clear the cache manually via FTP instead. To do this, navigate to the `var/cache` directory of the CCM19 installation in your webspace.
&gt
&gt; There may be several folders starting with `prod_` and ending with a longer sequence of digits - e.g. `prod_20210929152426`. The folder with the most recent modification time is probably the current cache directory.
&gt
&gt; Rename the corresponding directory before deleting it, so that CCM19 does not refill it at the same time when page visitors call the widget during the deletion process, for example. Wait about 5 seconds after processing to make sure that all requests to CCM19 that might still have used the old cache directory are completed.
&gt
&gt; Then delete the old, renamed cache directory; via FTP, this process may take a few minutes. The new cache directory will be created automatically the next time CCM19 is called.


If it still does not work - please ask the support, we will get the problem solved for you!

 
