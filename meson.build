project('meson-vcpkg', 'c', default_options: ['c_std=c11'])

sdl3_dep = dependency('sdl3')
libyaml_dep = dependency('yaml-0.1')

deps = [sdl3_dep, libyaml_dep]

executable('deptest', 'main.c', dependencies: [deps])
