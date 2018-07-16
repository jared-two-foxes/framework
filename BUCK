cxx_library(
  name = 'framework',
  header_namespace = 'framework',
  srcs = glob([
    'src/**/*.cpp',
  ]),
  headers = subdir_glob([ # private include files
    ('detail', '**/*.h'), # they are only accessible inside the library
    ('detail', '**/*.hpp'),
  ]),
  exported_headers = subdir_glob([ # public include files
    ('include', '**/*.h'), # those will be exported
    ('include', '**/*.hpp'), # and accessible via <framework/header.h>
  ]),
  platform_compiler_flags = [
    ('.x86_64$',{'/EHsc'}),
  ],
  platform_preprocessor_flags = [
    ('.x86_64$', {'/DWIN32', '/D_WIN32', '/D_WINDOWS'}),
  ],
  deps = ['//externals/cppzmq:cppzmq', '//externals/libzmq:libzmq'],
  visibility = ['PUBLIC']
)
