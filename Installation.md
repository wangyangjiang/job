### How to Install BillingTrack

1. Clone or download the repository to a new web directory.

2. Run "composer install" in web directory

3. create a NEW BillingTrack database.

4. Copy .env.example to .env

5. edit .env and change:

-   DB\_HOST=
-   DB\_DATABASE=
-   DB\_USERNAME=
-   DB\_PASSWORD=

- to your \*\*NEW\*\* database settings.

6. save .env file.

-   Run "php artisan key:generate"
-   This copies the app key into the .env file, attached to the APP_KEY= line.


7. Set permissions for your site.

8. Start YOUR\_BILLINGTRACK\_WEBSITE/setup

9. After database configuration finishes (this may take a couple of
minutes):

- Create new account -&gt; creates fresh installation with account


10. sign in
