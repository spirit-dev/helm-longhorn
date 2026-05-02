# longhorn



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
``
