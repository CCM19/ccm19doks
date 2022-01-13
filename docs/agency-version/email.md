# Email

The email section for the Agency version is extended compared to the download version. But the basic settings are identical and can be found here: [Default Mail Settings](../system-and-co/email.md) 

## Quota mails

If you use a quota for the access numbers, automatically when approaching the quota mails go out to the customers pointing to it. You can set that the admin or another email address gets a copy of the quota mails.

![screenshot-1641988621764](../assets/screenshot-1641988621764.jpg)

Additionally you can set if a copy of the quota mails will be sent to the admin and if customers will be informed about updates via email.

If you use call limits, you can enter here the percentage thresholds from which the respective mails go out to inform the customers / clients that the maximum call count will soon be reached.



## Quota Mails Templates resp. Content

The quota mails themselves can be predefined here. The following variables are available. The synthax must be observed - the curly brackets are mandatory {{ varname }}.

| Variables | Content | Use in |
| ------------------ | ------------------------------------------------------------ | ------------------------------- |
| {{ callMaxCount }} | The number of available calls in the <br />selected rate | mail for the found cookies |
| {{ quota }}        | The numeric value of the percentage consumption - <br />i.e. if 94% is consumed the variable contains the value 94 | In the mail "Call Limit" |
| {{ username }}     | username of the customer | In the mail "Call Limit" |
| {{ email }}        | E-mail address of the customer | In the mail "Call Limit" |
| {{ domainvar }}    | The name of the domain for which the mail was sent | All email templates |

## Mail Templates

The variables can be used in the body text of the mails.

![screenshot-1641988818841](../assets/screenshot-1641988818841.jpg)
