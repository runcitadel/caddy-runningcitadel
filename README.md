runningcitadel.com module for Caddy
===================================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with [runningcitadel.com](https://runningcitadel.com).

## Caddy module name

```
dns.providers.runningcitadel
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "runningcitadel",
				"username": "username",
				"password": "password"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns runningcitadel username password
}
```

```
# one site
tls {
	dns runningcitadel username password
}
```
