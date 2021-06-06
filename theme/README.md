# New Self Theme

This theme was designed for a small para church organisation but can be
used for other small organisations.


## How to use

Create a page called `Home`. It should also have the page url `home`.

Under the header `Events`, up to a maximum of 6 pages with the tag `event` are
displayed in cards.

Under the header `News`, up to a maximum of 5 newest posts tagged `news` are displayed.

If you'd like to keep `reource` private, you'll need to remember to ensure that the
post can only be viewed by members of the site.

To create the navigation, we recommend having at least `News` and `Resources` in the main
navigation bar to point to the respective urls `https://<site_url>/news`
and `https://<site_url>/resources`.

The `routes.yaml` file will also need to be updated to display posts tagged `news` and `resource`.
