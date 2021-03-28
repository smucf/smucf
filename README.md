# SMU Christian Fellowship

Everything that is behind the website https://smucf.org

It is single server setup using [docker compose](https://docs.docker.com/compose/),
and using [ghost](https://ghost.org) for the website CRM and members management.


## Theme Development

Styles are compiled using Gulp/PostCSS to polyfill future CSS spec.
You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and
[Gulp](https://gulpjs.com) installed globally. After that, from the root directory:


```bash
# Install
yarn --cwd theme

# Run build & watch for changes
yarn --cwd theme dev
```

Now you can edit `theme/assets/css/` files, which will be compiled to `theme/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `theme/dist/new-self.zip`, which is used for the theme.

```bash
yarn --cwd theme zip
```

## Integration Test

If you want to see how your theme might look like before deploying, you'll need to setup ghost locally.
To ensure we have a clean directory, we'll be using a directory called `ghost-local`.

```bash
ghost install local --dir ghost-local
# Create your admin user

# symbolically link theme directory with local ghost theme directory
ln -fs ${PWD}/theme/ ghost-local/content/themes/new-self
ghost start --dir ghost-local

# for future changes, ghost needs to reload the theme so ghost needs to be restarted.
# ghost restart

# Alternatively, you can watch for changes in the assets directory with a separate process and restart on changes
# rg . -l | rg assets | entr ghost restart -d ghost-local
```
