# Go to https://mesonbuild.com/Reference-manual_functions.html# to read about functions
project(
    'tutorial',
    'cpp',
    version : '0.0.1',
    license : 'GPL3',
    default_options : ['warning_level=3']
)
project_description = 'A simple test Windows RT application'

add_global_arguments('-DSOME_TOKEN=value', language : 'cpp')

inc = include_directories(
    'include',
    'D:/Program Files (x86)/Windows Kits/10/Include/10.0.22621.0/cppwinrt' #How can this be specified in meson invocation?
)

# subdir() enters the specified subdirectory and executes the meson.build file in it
subdir('include')
subdir('src')
subdir('test')

project_source_files = [
    'src/main.cpp'
]

project_dependencies = [
  dependency('mylib', fallback : ['mylib', 'mylib_dep']),
  dependency('headeronly', fallback : ['headeronly', 'headeronly_dep']),
]

build_args = [
]

project_target = executable(
    meson.project_name(),
    project_source_files,
    include_directories : inc,
    dependencies: project_dependencies,
    install : true,
    cpp_args: build_args
)
