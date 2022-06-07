# Installing Snap Packages

## Introduction

Snap has to be one of the most hated package managers in the Linux community, simply because of its inconvenience as a tool.
One reason why I hate it is its fragile server structure, throwing http 408 (a timeout) when I try to use it.
This surely is stupid, because there is a workaround that fixes this issue.

## Workflow

First of all, you'll have to download the snap package manually.
I'll use Nextcloud as an example:
```bash
sudo snap download nextcloud
```
Next, you'll have to acknowledge it:
```bash
sudo snap ack nextcloud_30258.assert
```
And finally, the installation can be started:
```bash
sudo snap install nextcloud_30258.snap
```
This is basically the same as installing a .deb file with dpkg.

[Source](https://forum.snapcraft.io/t/error-http-status-code-408-snap-store/28980/5)