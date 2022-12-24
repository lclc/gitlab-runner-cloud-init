# GitLab Runner cloud-init

Set up your own [GitLab Runner](https://docs.gitlab.com/runner/) within seconds using [cloud-init](https://cloud-init.io/).

Make sure you adjust the following points in the cloud-ini file:

- Set your own SSH Keys at ssh_authorized_keys
- Set your GitLab `registration-token`
- Set the instances name in `description`
- Adjust the `tag-list` (optional)
- Allow port 9252 to be accessible from your Prometheus instance for monitoring (optional)

It will also configure [Unattended-Upgrades](https://manpages.ubuntu.com/manpages/kinetic/en/man8/unattended-upgrade.8.html) to automatically install security upgrades and the latest versions of GitLab Runner (they update every month).

This has been **tested with Ubuntu LTS 20.04 and 22.04** on [Hetzner Cloud](https://www.hetzner.com), [Exoscale](https://exoscale.com), and [Microsoft Azure](https://www.azure.com).

Note: GitLab-Runner version 16.0 will remove the current registration-token approach and replace it with something new (which hasn't been implemented yet). For more information see the [Next GitLab Runner Token Architecture-epic](https://gitlab.com/groups/gitlab-org/-/epics/7663). This repositories cloud-init file will have to be updated.
