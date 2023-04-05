# setup qt libraries for github CI

```yaml
steps:
- uses: tlambert03/setup-qt-libs@v1
```


This is a simple action to install libraries necessary to run a Qt desktop environment on
`linux` runners (and do nothing on macos and windows runners).

Currently, this will run something like:

> ```
> sudo apt-get install -y libegl1 libdbus-1-3 libxkbcommon-x11-0 \
>      libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-randr0 \
>      libxcb-render-util0 libxcb-xinerama0 libxcb-xinput0 libxcb-xfixes0 \
>      x11-utils libxcb-cursor0
> ```

(see https://github.com/tlambert03/setup-qt-libs/blob/main/index.js for current code)
