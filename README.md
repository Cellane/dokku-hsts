# Dokku HSTS Plugin

Dokku HSTS Plugin is a simple plugin that gives the ability to enable HSTS on a
per-app basis.

## Installation

```shell
# on 0.4.x+
sudo dokku plugin:install https://github.com/Cellane/dokku-hsts.git
```

## Usage

```shell
# To enable HSTS for application, set the `HSTS_ENABLED` environmental variable
# to `true`.
#
# By default, this will enable HSTS for the particular application only (in
# other words, the `includeSubdomains` clause is ommitted).
#
# By default, the max-age clause is set to 31536000 seconds, which is a period
# of one year.
dokku config:set <app> HSTS_ENABLED=true

# If you wish to customize the max-age value, then this is what you’re looking
# for.
dokku config:set <app> HSTS_MAX_AGE=15768000

# If you wish to include the `includeSubdomains` clause (this could be
# useful for applications deployed to apex domain), set this to `true`.
# Bear in mind, however, that this will NOT automatically add the HSTS header
# to other applications deployed to Dokku.
dokku config:set <app> HSTS_INCLUDE_SUBDOMAINS=true
```
