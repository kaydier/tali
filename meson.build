project ('tali', ['c'],
         version: '3.31.1',
         license: 'GPLv2+',
         default_options: [
             'warning_level=1',
             'buildtype=debugoptimized',
         ],
         meson_version: '>= 0.37.1')

gnome = import ('gnome')
i18n = import ('i18n')

# Paths
config_h_dir = include_directories('.')
mandir = join_paths (get_option ('prefix'), get_option ('mandir'))
localedir = join_paths (get_option ('prefix'), get_option ('localedir'))
datadir = join_paths (get_option ('prefix'), get_option ('datadir'))
pkgdatadir = join_paths (datadir, 'tali')

# Dependencies
gtk_dep = dependency ('gtk+-3.0', version: '>= 3.16')

# Configuration
conf = configuration_data()
conf.set_quoted('VERSION', meson.project_version())
configure_file(output: 'config.h', configuration: conf)

subdir ('po')
subdir ('data')
subdir ('help')
subdir ('src')