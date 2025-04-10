# Quick Start for Drupal CMS and Lando

**Requirements:** [Lando](https://lando.dev/).

_See [lando-drupal-core-quick-start](https://github.com/Binbiriz/lando-drupal-core-quick-start) repository for Drupal Core Quick Start._

All of the bash commands in this document must be run in repo root.

After cloning the repo, you're free to delete the `.git` directory.

```bash
rm -rf ./.git/
```

## Prepare Code base

```bash
lando start
```

After starting Lando, you will see the URLs. Please do not visit them at this moment.

![Lando Start URLs](https://i.imgur.com/hOwdA1e.png)

Continue running the command below:

```bash
lando composer create-project drupal/cms /app/temp --no-install

rsync -rtv --remove-source-files ./temp/ ./drupal/

find ./temp -type d -empty -delete # or run `rm -rf ./temp/`

rm ./drupal/web/.gitkeep

lando composer install # do not forget to confirm plugins when prompted
```

## Install Site

### Manual Installation via Browser

You can now visit the URLs mentioned above and perform an installation via browser:

[Manual Drupal CMS Installation video](https://www.awesomescreenshot.com/video/38434797?key=4ca919163118c0ce5befa1636a971d58)

## Admin Interface

Visit [https://dev-drupalcms.lndo.site/user/login](https://dev-drupalcms.lndo.site/user/login).

![Drupal Login Page](https://i.imgur.com/1AR4mnt.png)
