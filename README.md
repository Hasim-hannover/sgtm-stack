# Server-Side GTM Stack

Schlanker Self-Hosting-Stack für Google Tag Manager Server-Side. Docker betreibt den sGTM-Container; Caddy übernimmt HTTPS, Reverse Proxy und grundlegende Security Header.

## Architektur

```text
Browser / Website
       ↓
track.hasimuener.de
       ↓
     Caddy
       ↓
  sGTM :8080
       ↓
Analytics / Marketing APIs
```

## Stack

- Google Tag Manager Server-Side Container
- Docker Compose
- Caddy 2
- automatisches TLS
- Healthcheck für den sGTM-Container
- persistente Caddy-Daten

## Repository-Struktur

```text
caddy/
├── Caddyfile
├── docker-compose.yml
├── config/
└── README.md
```

## Sicherheitsprinzip

Die eigentliche GTM-Container-Konfiguration und Secrets gehören nicht ins Repository. `CONTAINER_CONFIG` wird zur Laufzeit über die Umgebung bereitgestellt.

## Einsatz

Der Stack dient als nachvollziehbare Infrastruktur-Basis für Server-Side-Tracking-Setups. Domains, Consent-Architektur, GA4/Ads-Endpunkte und produktive Credentials werden projektspezifisch konfiguriert.
