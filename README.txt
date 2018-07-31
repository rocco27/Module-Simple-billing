This is a Simple Billing module, you can set as services as you want and they will create the game server once a payment is done or, manually as administrator, setting the order as paid. You can configure the currency, the available invoice types, a payment email and a tax amount(%). For each service you can set max/min slots that can be purchased, price hour/month/year per slot, a title, an image and a service description.

The biggest drawback is that the only payment gateways are PayPal, PayGol, Skrill and Robokassa.

More infos:

Hi guys!

EXIM as smarthost is only needed for hosts with dynamically assigned IP because it avoids to be blocked by some mail servers like hotmail.

Upload all files.

Login with ssh and change to the user 'www-data'(in ubuntu) or 'apache'(in centos) or any other user that manages the apache server with, for example:

sudo su - www-data

Now edit the cron tab for this user

crontab -e

and copy this line at the end of the file and save it (WARNING:modify it with the correct path):

*/1 * * * * php /var/www/html/ogp/modules/billing/cron-shop.php

Now this script searches for expired game homes every minute, and wil stop and remove them if they are expired.
If you would like to do this at midnight every day instead of every minute you should use

0 0 * * * php /var/www/html/ogp/modules/billing/cron-shop.php

TIP: Searching in google, for example, "cron every month" you will find the correct code to search expired homes and remove them every month.

