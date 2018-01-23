src_res = gnome.compile_resources('org.gnome.SoundRecorder.src',
  'org.gnome.SoundRecorder.src.gresource.xml',
  gresource_bundle: true,
  install: true,
  install_dir: pkgdatadir,
)

bin_conf = configuration_data()
bin_conf.set('GJS', find_program('gjs').path())
bin_conf.set('PACKAGE_VERSION', meson.project_version())
bin_conf.set('PACKAGE_NAME', meson.project_name())
bin_conf.set('prefix', get_option('prefix'))
bin_conf.set('libdir', join_paths(get_option('prefix'), get_option('libdir')))
bin_conf.set('datadir', join_paths(get_option('prefix'), get_option('datadir')))

gio = dependency('gio-2.0', version: '>= 2.43.4')
gdk = dependency('gdk-3.0')
gtk3 = dependency('gtk+-3.0', version: '>= 3.12')
glib = dependency('gobject-introspection-1.0', version: '>= 1.31.6')

configure_file(
  input: 'org.gnome.SoundRecorder.in',
  output: 'org.gnome.SoundRecorder',
  configuration: bin_conf,
  install: true,
  install_dir: get_option('bindir')
)

run_target('run',
  command: join_paths(meson.build_root(), 'src', 'org.gnome.SoundRecorder'),
  depends: [
    src_res,
    data_res,
  ]
)
