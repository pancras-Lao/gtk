# demos/widget-factory

widgetfactory_resources = gnome.compile_resources('widgetfactory_resources',
                                                  'widget-factory.gresource.xml',
                                                  source_dir: '.')

executable('gtk4-widget-factory',
           'widget-factory.c', widgetfactory_resources,
           dependencies: libgtk_dep,
           include_directories: confinc,
           gui_app: true,
           link_args: extra_demo_ldflags,
           install: true)

# desktop file
install_data('org.gtk.WidgetFactory.desktop', install_dir: gtk_applicationsdir)

# icons
icontheme_dir = join_paths(gtk_datadir, 'icons/hicolor')

foreach size: ['scalable', 'symbolic']
  install_subdir('data/' + size,
    install_dir: icontheme_dir
  )
endforeach

# appdata
install_data('org.gtk.WidgetFactory.appdata.xml', install_dir: gtk_appdatadir)
