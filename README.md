# Tolki Tern Layout

## Commands memo

### Drawing the keymap

```sh
keymap parse -z config/boards/shields/tern/tern.keymap > keymap-drawer/layers.yaml \
&& echo 'layout: {qmk_info_json: keymap-drawer/tern_layout.json}' >> keymap-drawer/layers.yaml \
&& keymap draw keymap-drawer/layers.yaml > layout.svg
```

### Building locally

In the `zmk` `app` directory:

```sh
west build -b seeeduino_xiao_rp2040 --pristine -- -DSHIELD=tern -DZMK_CONFIG=/workspaces/zmk/tern
```

## Current keymap

![Tolki tern keymap]( layout.svg )
