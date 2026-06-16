project('bo_meson',
  version: '0.1.0'
  , license: 'BSD-3-Clause')

cp = 'cp'
sep = '/'

if build_machine.system() == 'windows'
  cp = 'copy'
  sep = '\\'
endif

compile_cmds = custom_target('compile_cmds',
  build_always: true,
  console: true,
  command: [cp, '@BUILD_ROOT@'+sep+'compile_commands.json', '@SOURCE_ROOT@'+sep+'compile_commands.json'],
  output: 'compile_commands.json'
  )

