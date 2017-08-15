include_defs('//BUCKAROO_DEPS')

prebuilt_cxx_library(
  name = 'autotools-generated',
  header_namespace = '',
  header_only = True,
  exported_platform_headers = [
    (
      'default',
      subdir_glob([
        ('autotools-generated/macosx-x86_64/src/mongoc', '**/*.h'),
      ])
    ),
    (
      '^macosx.*',
      subdir_glob([
        ('autotools-generated/macosx-x86_64/src/mongoc', '**/*.h'),
      ])
    ),
  ]
)

cxx_library(
  name = 'mongoc',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('src/mongoc', '**/*.h'),
    ('src/mongoc', '**/*.def'),
  ]),
  preprocessor_flags = [
    '-DMONGOC_COMPILATION=1',
  ],
  srcs = glob([
    'src/mongoc/**/*.c',
  ]),
  deps = BUCKAROO_DEPS + [
    ':autotools-generated',
  ],
  visibility = [
    'PUBLIC',
  ],
)
