project('bo_meson', license: 'mit')

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

