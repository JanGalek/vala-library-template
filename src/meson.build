library_sources = files('library.vala')

library_deps = [
  dependency('glib-2.0'),
  dependency('gio-2.0'),
  dependency('gee-0.8'),
]

library_shared = shared_library(
  meson.project_name(),
  library_sources,
  dependencies: library_deps,
  install: true,
  vala_vapi: 'vapi/' + meson.project_name() + '.vapi',
  vala_header: meson.project_name() + '.h'
)

library_dep = declare_dependency(
  link_with: library_shared,
  include_directories: include_directories('.'),
  sources: library_sources
)

pkg = import('pkgconfig')
pkg.generate(
  library_shared,
  version: meson.project_version(),
  name: meson.project_name(),
  filebase: meson.project_name(),
  description: 'Vala Library Template.'
)
