# longhorn

<!-- More info: https://github.com/Ileriayo/markdown-badges -->
<!-- More info: https://shields.io/badges -->
<!-- More info: https://badgesgenerator.com/ -->

[![GitLab Sync](https://img.shields.io/badge/gitlab_sync-longhorn-blue?style=for-the-badge&logo=gitlab)](https://gitlab-internal.spirit-dev.net/github-mirror/helm-longhorn) <!-- markdownlint-disable MD041 -->
[![GitHub Mirror](https://img.shields.io/badge/github_mirror-longhorn-blue?style=for-the-badge&logo=github)](https://github.com/spirit-dev/helm-longhorn)
[![App Status](https://argocd-internal.spirit-dev.net/api/badge?name=longhorn-turingpi&revision=true&showAppName=true)](https://argocd-internal.spirit-dev.net/applications/longhorn-turingpi)

<!--TOC-->

- [Table of content](#table-of-content)
- [CronJobs](#cronjobs)
- [Installation process](#installation-process)

<!--TOC-->

## Table of content

[[_TOC_]]

## CronJobs

There are 2 important cronjobs set up for longhorn

1. Drives backup (for drives tagged with `custom-backup`)
2. Longhorn system

The array below describes the schedules

| Job                    | cron          | Description                     |
| ---------------------- | ------------- | ------------------------------- |
| drives backup          | 0 0 \* \* \*  | at 20:00 every days (00:00 UTC) |
| longhorn system backup | 40 0 \* \* \* | at 20:40 every days (00:40 UTC) |

## Installation process

The installation is entirely managed by Argocd.

A `Makefile` is present here to ease the first and one-time deployment or in case of an issue.
The installation should be done in two steps:

```shell
#> make dry-run ENV=<ENV>
#> make install ENV=<ENV>
```
