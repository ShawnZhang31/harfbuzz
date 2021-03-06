hb_base_sources = [
  'hb-blob.cc',
  'hb-buffer-serialize.cc',
  'hb-buffer.cc',
  'hb-draw.cc',
  'hb-common.cc',
  'hb-face.cc',
  'hb-font.cc',
  'hb-map.cc',
  'hb-ot-cff1-table.cc',
  'hb-ot-cff2-table.cc',
  'hb-ot-name.cc',
  'hb-ot-tag.cc',
  'hb-set.cc',
  'hb-shape.cc',
  'hb-shape-plan.cc',
  'hb-shaper.cc',
  'hb-static.cc',
  'hb-unicode.cc',
  'hb-ucd.cc',
  'hb-number.cc'
]

hb_base_headers = files([
  'hb.h',
  'hb-blob.h',
  'hb-buffer.h',
  'hb-draw.h',
  'hb-common.h',
  'hb-deprecated.h',
  'hb-face.h',
  'hb-font.h',
  'hb-map.h',
  'hb-set.h',
  'hb-shape.h',
  'hb-shape-plan.h',
  'hb-unicode.h',
  'hb-version.h',
  'hb-number.hh'
])

hb_base_ragel_sources = [
  'hb-buffer-deserialize-json.rl',
  'hb-buffer-deserialize-text.rl',
]

hb_fallback_sources = [
  'hb-fallback-shape.cc',
]

hb_ot_sources = [
  'hb-aat-layout.cc',
  'hb-aat-map.cc',
  'hb-ot-face.cc',
  'hb-ot-font.cc',
  'hb-ot-metrics.cc',
  'hb-ot-layout.cc',
  'hb-ot-color.cc',
  'hb-ot-map.cc',
  'hb-ot-math.cc',
  'hb-ot-shape.cc',
  'hb-ot-shape-complex-arabic.cc',
  'hb-ot-shape-complex-default.cc',
  'hb-ot-shape-complex-hangul.cc',
  'hb-ot-shape-complex-hebrew.cc',
  'hb-ot-shape-complex-indic.cc',
  'hb-ot-shape-complex-indic-table.cc',
  'hb-ot-shape-complex-khmer.cc',
  'hb-ot-shape-complex-myanmar.cc',
  'hb-ot-shape-complex-thai.cc',
  'hb-ot-shape-complex-use.cc',
  'hb-ot-shape-complex-use-table.cc',
  'hb-ot-shape-complex-vowel-constraints.cc',
  'hb-ot-shape-normalize.cc',
  'hb-ot-shape-fallback.cc',
  'hb-ot-cff1-table.cc',
  'hb-ot-cff2-table.cc',
  'hb-ot-var.cc',
]

hb_ot_headers = files([
  'hb-ot.h',
  'hb-ot-deprecated.h',
  'hb-ot-metrics.h',
  'hb-ot-color.h',
  'hb-ot-font.h',
  'hb-ot-layout.h',
  'hb-ot-math.h',
  'hb-ot-name.h',
  'hb-ot-shape.h',
  'hb-ot-var.h',
])

hb_ot_ragel_sources = [
  'hb-ot-shape-complex-indic-machine.rl',
  'hb-ot-shape-complex-khmer-machine.rl',
  'hb-ot-shape-complex-myanmar-machine.rl',
  'hb-ot-shape-complex-use-machine.rl',
]

hb_ft_sources = [
  'hb-ft.cc',
]

hb_ft_headers = files([
  'hb-ft.h',
])

hb_glib_sources = [
  'hb-glib.cc',
]

hb_glib_headers = files([
  'hb-glib.h',
])

hb_graphite2_sources = [
  'hb-graphite2.cc',
]

hb_graphite2_headers = files([
  'hb-graphite2.h',
])

hb_icu_sources = [
  'hb-icu.cc',
]

hb_icu_headers = files([
  'hb-icu.h',
])

hb_subset_sources = [
  'hb-ot-cff1-table.cc',
  'hb-ot-cff2-table.cc',
  'hb-static.cc',
  'hb-subset.cc',
  'hb-subset-cff1.cc',
  'hb-subset-cff2.cc',
  'hb-subset-cff-common.cc',
  'hb-subset-input.cc',
  'hb-subset-plan.cc',
  'hb-number.cc',
  'hb-ot-meta.cc'
]

hb_subset_headers = files([
  'hb-subset.h',
  'hb-number.hh',
  'hb-ot-meta.h'
])

hb_gobject_sources = [
  'hb-gobject-structs.cc'
]

hb_gobject_headers = files([
  'hb-gobject.h',
  'hb-gobject-structs.h',
])

incucdn = []
incsrc = include_directories('.')

hb_sources = hb_base_sources + hb_fallback_sources + hb_ot_sources
hb_headers = hb_base_headers + hb_ot_headers

if conf.get('HAVE_FREETYPE', 0) == 1
  hb_sources += hb_ft_sources
  hb_headers += hb_ft_headers
endif

if conf.get('HAVE_GDI', 0) == 1
  hb_sources += ['hb-gdi.cc']
  hb_headers += ['hb-gdi.h']
endif

if conf.get('HAVE_GRAPHITE2', 0) == 1
  hb_sources += hb_graphite2_sources
  hb_headers += hb_graphite2_headers
endif

if conf.get('HAVE_GLIB', 0) == 1
  hb_sources += hb_glib_sources
  hb_headers += hb_glib_headers
endif

if conf.get('HAVE_UNISCRIBE', 0) == 1
  hb_sources += ['hb-uniscribe.cc']
  hb_headers += ['hb-uniscribe.h']
endif

if conf.get('HAVE_DIRECTWRITE', 0) == 1
  hb_sources += ['hb-directwrite.cc']
  hb_headers += ['hb-directwrite.h']
endif

if conf.get('HAVE_CORETEXT', 0) == 1
  hb_sources += ['hb-coretext.cc']
  hb_headers += ['hb-coretext.h']
endif

if get_option('amalgam')
  # replace the array if is amalgam build
  hb_sources = ['harfbuzz.cc']
endif

# FIXME: move into harfbuzz-icu module
if conf.get('HAVE_ICU', 0) == 1
  hb_sources += hb_icu_sources
  hb_headers += hb_icu_headers
endif

# harfbuzz
gen_def = find_program('gen-def.py')
harfbuzz_def = custom_target('harfbuzz.def',
    command: [gen_def, '@OUTPUT@', '@INPUT@'],
    input: hb_headers,
    output: 'harfbuzz.def')

version = '0.' + '0'.join(meson.project_version().split('.')) + '.0'

extra_hb_cpp_args = []
if cpp.get_id() == 'msvc'
  if get_option('default_library') == 'shared'
    extra_hb_cpp_args += '-DHB_DLL_EXPORT'
  endif
  hb_so_version = ''
  hb_lib_prefix = ''
else
  hb_so_version = '0'
  hb_lib_prefix = 'lib'
endif

libharfbuzz = library('harfbuzz', hb_sources,
  include_directories: [incconfig, incucdn],
  dependencies: deps,
  cpp_args: cpp_args + extra_hb_cpp_args,
  soversion: hb_so_version,
  version: version,
  install: true,
  name_prefix: hb_lib_prefix)

libharfbuzz_dep = declare_dependency(
  link_with: libharfbuzz,
  include_directories: [incsrc, incucdn],
  dependencies: deps)

# harfbuzz-subset
harfbuzz_subset_def = custom_target('harfbuzz-subset.def',
    command: [gen_def, '@OUTPUT@', '@INPUT@'],
    input: hb_subset_headers,
    output: 'harfbuzz-subset.def')

libharfbuzz_subset = library('harfbuzz-subset', hb_subset_sources,
  include_directories: incconfig,
  link_with: [libharfbuzz],
  cpp_args: cpp_args + extra_hb_cpp_args,
  soversion: hb_so_version,
  version: version,
  install: true,
  name_prefix: hb_lib_prefix)

libharfbuzz_subset_dep = declare_dependency(
  link_with: libharfbuzz_subset,
  include_directories: incsrc,
  dependencies: deps)

pkgmod.generate(libharfbuzz,
  description: 'HarfBuzz text shaping library',
  subdirs: [meson.project_name()],
  version: meson.project_version(),
)

pkgmod.generate(libharfbuzz_subset,
  description: 'HarfBuzz font subsetter',
  subdirs: [meson.project_name()],
  version: meson.project_version(),
)

have_gobject = conf.get('HAVE_GOBJECT', 0) == 1

cmake_config = configuration_data()
cmake_config.set('libdir', '${prefix}/@0@'.format(get_option('libdir')))
cmake_config.set('includedir', '${prefix}/@0@'.format(get_option('includedir')))
cmake_config.set('HB_LIBTOOL_VERSION_INFO', hb_libtool_version_info)
cmake_config.set('have_gobject', have_gobject ? 'true' : 'false')
configure_file(input: 'harfbuzz-config.cmake.in',
  output: 'harfbuzz-config.cmake',
  configuration: cmake_config,
  install_dir: join_paths(get_option('libdir'), 'cmake', 'harfbuzz'))

if have_gobject
  gnome = import('gnome')

  h_templ = configure_file(
    input: 'hb-gobject-enums.h.tmpl',
    output: 'hb-gobject-enums-tmp.h.tmpl',
    configuration: configuration_data(),
    format: 'cmake')

  cc_templ = configure_file(
    input: 'hb-gobject-enums.cc.tmpl',
    output: 'hb-gobject-enums-tmp.cc.tmpl',
    configuration: configuration_data(),
    format: 'cmake')

  enums = gnome.mkenums('hb-gobject',
    sources: hb_headers,
    h_template: h_templ,
    c_template: cc_templ,
    identifier_prefix: 'hb_',
    symbol_prefix: 'hb_gobject',
  )

  enum_c = custom_target('hb-gobject-enums.cc',
    input: enums[0],
    output: 'hb-gobject-enums.cc',
    command: [python3, files('fix_get_types.py')[0], '@INPUT@', '@OUTPUT@']
  )

  enum_h = custom_target('hb-gobject-enums.h',
    input: enums[1],
    output: 'hb-gobject-enums.h',
    command: [python3, files('fix_get_types.py')[0], '@INPUT@', '@OUTPUT@'],
    install: true,
    install_dir: join_paths(get_option('prefix'), get_option('includedir'), meson.project_name()),
  )

  hb_gobject_sources += [enum_c]

  harfbuzz_gobject_def = custom_target('harfbuzz-gobject.def',
    command: [gen_def, '@OUTPUT@', '@INPUT@'],
    input: [hb_gobject_headers, enum_h],
    output: 'harfbuzz-gobject.def')

  libharfbuzz_gobject = library('harfbuzz-gobject', [hb_gobject_sources, enum_c, enum_h],
    include_directories: incconfig,
    dependencies: deps,
    link_with: [libharfbuzz],
    cpp_args: cpp_args + extra_hb_cpp_args,
    soversion: hb_so_version,
    version: version,
    install: true,
    name_prefix: hb_lib_prefix)

  gir = find_program('g-ir-scanner', required: get_option('introspection'))
  build_gir = gir.found() and not meson.is_cross_build()

  if build_gir
    hb_gen_files_gir = gnome.generate_gir(libharfbuzz, libharfbuzz_gobject,
      sources: [hb_headers, hb_sources, hb_gobject_headers, hb_gobject_sources, enum_h],
      namespace: 'HarfBuzz',
      nsversion: '0.0',
      identifier_prefix: 'hb_',
      symbol_prefix: 'hb_',
      includes: ['GObject-2.0'],
      install: true,
      extra_args:  ['--cflags-begin',
                    '-DHB_H',
                    '-DHB_H_IN',
                    '-DHB_OT_H',
                    '-DHB_OT_H_IN',
                    '-DHB_GOBJECT_H',
                    '-DHB_GOBJECT_H_IN',
                    '-DHB_EXTERN=',
                    '--cflags-end'])
  endif

  libharfbuzz_gobject_dep = declare_dependency(
    link_with: libharfbuzz_gobject,
    include_directories: incsrc,
    sources: build_gir ? hb_gen_files_gir : hb_gobject_sources,
    dependencies: deps)

  pkgmod.generate(libharfbuzz_gobject,
    description: 'HarfBuzz text shaping library GObject integration',
    subdirs: [meson.project_name()],
    version: meson.project_version(),
  )
else
  libharfbuzz_gobject_dep = dependency('', required: false)
endif

install_headers(hb_headers + hb_gobject_headers + hb_subset_headers, subdir: meson.project_name())
