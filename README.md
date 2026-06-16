# A collection of Meson/Muon utils

## Feature utils
- Auto copy compile_commands.json to root dir for lsp support

### How to import using wrap files
Put a bo_meson.wrap file inside ./subprojects directory of root
and add the following lines to import

```toml
[wrap-git]
url = https://github.com/Borwe/bo_meson.git
depth = 1
revision = HEAD
```

### How to use the compile commands migration util
Inside your meson.build add the following lines after including this project as a wraped

```meson
msn = subproject('bo_meson')
compile_cmds = msn.get_variable('compile_cmds')
```

and then you can run the target directly or link it to another target eg:

```meson
run_target('run', command: portgen_cli, depends: [portgen_cli, compile_cmds])
```
now when whenever you run the target with meson or muon, it will copy `compile_commands.json`
