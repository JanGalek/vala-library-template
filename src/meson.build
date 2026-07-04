lib_sources = files('vala-library-template.vala')

vala_lib_deps = [
  dependency('glib-2.0'),
  dependency('gio-2.0'),
  dependency('libsoup-3.0')
]

vala_lib = shared_library(
  'vala-library-template',
  lib_sources,
  dependencies: vala_lib_deps,
  install: true,
  vala_vapi: 'vala-library-template.vapi',
  vala_header: 'vala-library-template.h'
)

vala_lib_dep = declare_dependency(
  link_with: vala_lib,
  include_directories: include_directories('.'),
  sources: lib_sources
)

pkg = import('pkgconfig')
pkg.generate(
  vala_lib,
  version: '1.0',
  name: 'vala-library-template',
  filebase: 'vala-library-template',
  description: 'Vala Library Template.'
)
