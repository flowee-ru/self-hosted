<div align="center">

# self-hosted
*Deploy Flowee using Docker*

</div>

## Configure
```
# Clone files
$ git clone https://github.com/flowee-ru/self-hosted
$ cd self-hosted

# Copy and edit config
$ cp .env.example .env
$ nano .env
```

**Change `example.com` to your host that can be accessed on public**

List of the environment variables for configuration:
| Variable              | Description                                               | Default value             |
|-----------------------|-----------------------------------------------------------|---------------------------|
| RTMP_PORT             | RTMP server port                                          | 1935                      |
| CADDY_HOST            | Public host for Caddy                                     | http://example.com        |
| APP_HOST              | Public host of web application (Flovite)                  | http://example.com        |
| VITE_API_HOST         | Public host of API                                        | http://example.com/api    |
| VITE_EVENTS_HOST      | Public host of websocket server (currently a part of API) | ws://example.com/api/ws   |
| VITE_MONDAY_HOST      | Public host of Monday FLV output                          | http://example.com/monday |
| VITE_HCAPTCHA_SITEKEY | HCaptcha sitekey                                          | None                      |
| CAPTCHA_SECRET        | HCaptcha secret                                           | None                      |
| SMTP_HOST             | SMTP server host                                          | None                      |
| SMTP_PORT             | SMTP server port                                          | None                      |
| SMTP_USER             | SMTP user                                                 | None                      |
| SMTP_PASSWORD         | SMTP user's password                                      | None                      |

## Run
```
# Run in detached mode
$ docker compose up -d
```

## Update
Update Flowee to the newest version
```
# Download the latest images
$ docker compose pull

# Restart
$ docker compose down
$ docker compose up -d
```
