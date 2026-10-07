# Conflict Resolution Tool "Amitee" (Headless Drupal 11 + React)

A self-directed project with Drupal 11, headless architecture, and custom module development. The idea: a tool that helps document workplace interpersonal conflicts and prepares structured data for analysis by an AI API.

**Status: early development.** The infrastructure is in place; the application layer is being built.

## What works today

- Drupal 11 base install running on a DigitalOcean droplet (Ubuntu, Caddy, PHP 8.4-FPM, MariaDB 11.8)
- Local development environment with DDEV
- Configuration management with Drush (`config:export` / `config:import`), with config tracked in this repo
- GitHub Actions pipeline that deploys to the server on push

## Planned

- [ ] Content types: **Employee** and **Event** (an event records a conflict and its history)
- [ ] Custom module that outputs an event and its history as JSON
- [ ] Connection from that module to an AI API
- [ ] React front end consuming Drupal's API (headless)
- [ ] Accessibility pass (WCAG) on the front end

## Stack

| Layer | Tools |
|---|---|
| CMS | Drupal 11 |
| Front end (planned) | React |
| Local dev | DDEV |
| Hosting | DigitalOcean, Caddy, PHP 8.4, MariaDB 11.8 |
| CI/CD | GitHub Actions |
| Config | Drush, Drupal configuration management |

## Running locally

```bash
git clone https://github.com/TheJDexp/amitee.git
cd amitee
ddev start
ddev composer install
ddev drush config:import -y
ddev launch
```

## Known limitations

- **Database sync is manual.** The deploy pipeline pushes code and configuration, but pulling the production database down to a local DDEV environment isn't automated yet. For now it's a manual dump and import.

(Content isn't included in the repo. Config import gives you the structure; the production database must be pulled manually if you want existing content.)


## Author

Jean-David Ouellette: [\[LinkedIn link\]](https://www.linkedin.com/in/jean-david-ouellette/)