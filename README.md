# Purpose
This was used to build  services to demo a deployment for Check Point's open-telemetry project, [Skyline](https://support.checkpoint.com/results/sk/sk178566)

This is a sample docker_compose that will build three containers to provide Grafana and Prometheus while using Traefik as the proxy service.
Traefik is configured to use a cloudflare API key to validate the Let's Encrypt DNS challenge.


# Assumptions
- Registered domain managed via Cloudflare
- Appropriate Cloudflare API Tokens
	- https://dash.cloudflare.com/profile/api-tokens
	- https://developers.cloudflare.com/fundamentals/api/
	- https://certbot-dns-cloudflare.readthedocs.io/en/stable/
- Standalone Docker

# Requirements
- Create a **.env** file with the following required parameters
	- CF_DNS_API_TOKEN=___DNSAPITOKEN___
	- CF_ZONE_API_TOKEN=___ZONEAPITOKEN___
	- CF_API_EMAIL=___CLOUDFLARE_EMAIL___
- **Optional:** _(must edit docker-compose.yml, if not using environment variable)_
	- TRAEFIKIP=_\<ip from skyline subnet\>_
	- PROMIP=_\<ip from skyline subnet\>_
	- GRAFANAIP=_\<ip from skyline subnet\>_

# To-Do

- Include the Grafana Dashboards 
