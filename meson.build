project('bo_meson',
  version: '0.1.0'
  , license: 'BSD-3-Clause')

sep = '/'
cp = ['cp', '@BUILD_ROOT@'+sep+'compile_commands.json', '@SOURCE_ROOT@'+sep+'compile_commands.json']

if build_machine.system() == 'windows'
  powershell = find_program('powershell', required: true)
  sep = '\\'
  cp = [powershell,
    '-Command', 'Copy-Item', '-Path',
    '@BUILD_ROOT@'+sep+'compile_commands.json',
    '-Destination',
    '@SOURCE_ROOT@'+sep+'compile_commands.json'
    ]
endif

compile_cmds = custom_target('compile_cmds',
  build_always: true,
  console: true,
  command: cp,
  output: 'compile_commands.json'
  )

