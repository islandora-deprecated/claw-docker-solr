# Islandora CLAW: Solr Docker Image

[![Docker Stars](https://img.shields.io/docker/stars/islandora/claw-solr.svg)](https://hub.docker.com/r/islandora/claw-solr/)
[![Docker Pulls](https://img.shields.io/docker/pulls/islandora/claw-solr.svg)](https://hub.docker.com/r/islandora/claw-solr/)
[![Contribution Guidelines](http://img.shields.io/badge/CONTRIBUTING-Guidelines-blue.svg)](./CONTRIBUTING.md)
[![LICENSE](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)

# :heavy_exclamation_mark: :heavy_exclamation_mark: :heavy_exclamation_mark:

Since Islandora CLAW has moved development to Drupal 8, our Docker images **no longer** function properly. We recommend using the [vagrant](https://github.com/Islandora-CLAW/CLAW/tree/master/install) build instead. Please follow the Islandora [listserv](https://groups.google.com/forum/?hl=en&fromgroups=#!forum/islandora) and weekly [CLAW Tech Calls](https://github.com/Islandora-CLAW/CLAW/wiki#islandora-claw-tech-calls) for updates about the status of Docker and Ansible with Islandora CLAW. 

 Please note that even with vagrant, there is not yet a stable release of Islandora CLAW. We welcome your volunteer contributions to help get the project to production. 
 
 :heavy_exclamation_mark: :heavy_exclamation_mark: :heavy_exclamation_mark:
 
## Introduction

Defines the Solr Docker Image.

Based on the [Tomcat Docker Image](https://github.com/Islandora-CLAW/docker-tomcat).

## Includes

* Solr 4

## Build Arguments

| Variable          | Required | Default                                                      |
|-------------------|----------|--------------------------------------------------------------|
| SOLR_VERSION      | no       | 4.10.3                                                       |
| SOLR_DEPENDENCIES | no       | log4j-1.2.17.jar slf4j-api-1.7.6.jar slf4j-log4j12-1.7.6.jar |

**SOLR_DEPENDENCIES** are the jar files to copy from `example/lib/ext` into `$CATALINA_HOME/lib`.

**Example:**
```bash
docker build -t islandora/claw-solr .
```

## Environment Variables

No additional environment variables provided.

Please consult the [parent image](https://github.com/Islandora-CLAW/docker-tomcat).

**Example (foreground, port 8080, auto-remove):**
```bash
docker run --rm -ti -p 8080:8080 -e "TOMCAT_ADMIN_PASSWORD=your_super_secure_password" islandora/claw-solr
```

## Commands

For convenience a number of commands are provided in the [commands](/commands) folder.

| Command    | Arguments               | Defaults    | Notes                                                            |
|------------|-------------------------|-------------|------------------------------------------------------------------|
| build      |                         |             | Build this image with the default settings.                      |
| foreground | [port] [admin password] | 8080 random | Start tomcat in the foreground with the given port and password. |
| background | [port] [admin password] | 8080 random | Start tomcat in the background with the given port and password. |

## Maintainers/Sponsors

* UPEI
* discoverygarden inc.
* LYRASIS
* McMaster University
* University of Limerick
* York University
* University of Manitoba
* Simon Fraser University
* PALS
* American Philosophical Society
* common media inc.

## Maintainers

* [Nigel Banks](https://github.com/nigelgbanks)
* [Nick Ruest](https://github.com/ruebot)

## Development

If you would like to contribute, please get involved by attending our weekly [Tech Call](https://github.com/Islandora-CLAW/CLAW/wiki). We love to hear from you!

If you would like to contribute code to the project, you need to be covered by an Islandora Foundation [Contributor License Agreement](http://islandora.ca/sites/default/files/islandora_cla.pdf) or [Corporate Contributor Licencse Agreement](http://islandora.ca/sites/default/files/islandora_ccla.pdf). Please see the [Contributors](http://islandora.ca/resources/contributors) pages on Islandora.ca for more information.

## License

[MIT](https://opensource.org/licenses/MIT)
