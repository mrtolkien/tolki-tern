# Tolki Tern Layout

## Commands memo

### Drawing the keymap

```sh
keymap -c keymap-drawer/config.yaml parse -z config/boards/shields/tern/tern.keymap > keymap-drawer/layers.yaml \
&& yq -i '.layout.qmk_info_json = "keymap-drawer/tern_layout.json"' keymap-drawer/layers.yaml \
&& yq -i '.combos.2.align = "bottom"' keymap-drawer/layers.yaml \
&& yq -i '.combos.2.offset = 1' keymap-drawer/layers.yaml \
&& keymap draw keymap-drawer/layers.yaml > layout.svg
```

You can add the following for a better-looking output:

```yaml
- p: [18, 25]
  k: Caps Word
  l: [default]
  align: bottom
  offset: 1
```

### Building locally

In the `zmk` `app` directory:

```sh
west build -b seeeduino_xiao_rp2040 --pristine -- -DSHIELD=tern -DZMK_CONFIG=/workspaces/zmk/tern
```

## Current keymap

![Tolki tern keymap]( layout.svg )
