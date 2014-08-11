## Ansibles - apt [![Build Status](https://travis-ci.org/Ansibles/apt.png)](https://travis-ci.org/Ansibles/apt)

Ansible role which executes apt-get update to ensure the local APT package cache is up to date. At the same time, it cleans it from packages and .deb files which are no longer needed.


#### Variables

```yaml
apt_reset_source_list: no         # reset the /etc/apt/sources.list to the default
apt_cache_valid_time: 3600        # Time (in seconds) the apt cache stays valid
apt_install_recommends: no        # whether or not to install the "recommended" packages
apt_install_suggests: no          # whether or not to install the "suggested" packages
apt_autoremove: yes               # remove packages that are no longer needed for dependencies
apt_autoclean: yes                # remove .deb files for packages no longer on your system
```

Remark: Beware that setting `apt_install_recommends` and `apt_install_suggests` to `yes` may heavily increase the apt-requirements (and hence disk usage). You should proceed cautiously changing these.


#### License

Licensed under the MIT License. See the LICENSE file for details.


#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/ansibles/apt/issues)!
