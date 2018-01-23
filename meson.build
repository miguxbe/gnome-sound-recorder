project('org.gnome.SpundRecorder',
  version: '3.24.0.1',
  meson_version: '>= 0.42.0',
  license: 'GPL2+'
)

gnome = import('gnome')
i18n = import('i18n')

pkgdatadir = join_paths(get_option('datadir'), meson.project_name())

subdir('data')
subdir('po')
subdir('src')
