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
>      x11-utils libxcb-cursor0 libopengl0 libegl1-mesa
> ```

(see <https://github.com/tlambert03/setup-qt-libs/blob/main/index.js> for current code)

**See also**:  
[pyvista/setup-headless-display-action](https://github.com/pyvista/setup-headless-display-action),
which additionally prepares both windows and linux for offscreen opengl tests,
and, when used with the [qt option]([pyvista/setup-headless-display-action](https://github.com/pyvista/setup-headless-display-action#options)),
can replace this action

### to release new version (for maintainers)

1. `npm install`
2. `npm run prepare`
3. `git commit -am "new version"`
4. `git tag -a 'vX.X.X' -m 'vX.X.X'`
5. `git push --follow-tags`
6. `gh release create vX.X.X --generate-notes`
