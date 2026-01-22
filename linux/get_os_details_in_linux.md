# Get OS Details in Linux

You can find a bunch of details about your OS in `/etc/os-release`. You
probably know most of these details if you're running it on your main machine,
but it can come in handy if you're on a VM or in a container.

``` bash
% cat /etc/os-release
NAME="Fedora Linux"
VERSION="43 (Sway)"
RELEASE_TYPE=stable
ID=fedora
VERSION_ID=43
VERSION_CODENAME=""
PRETTY_NAME="Fedora Linux 43 (Sway)"
REDHAT_BUGZILLA_PRODUCT="Fedora"
REDHAT_BUGZILLA_PRODUCT_VERSION=43
REDHAT_SUPPORT_PRODUCT="Fedora"
REDHAT_SUPPORT_PRODUCT_VERSION=43
SUPPORT_END=2026-12-02
```

The `ID_LIKE` field can be particularly useful if the distro is a derivative of
another distro. For example, if the OS is Oracle Linux, the `ID-LIKE` value
will be `fedora`, from which it's derived. Very useful for troubleshooting.

```
NAME="Oracle Linux Server"
ID="ol"
ID_LIKE="fedora"
VERSION_ID="8.9"
```

More info about `os-release` can be found
[here](https://www.freedesktop.org/software/systemd/man/latest/os-release.html)

via https://til.hashrocket.com/posts/2qnduofrsd-get-os-details-in-linux-with-os-release
