project('yajl', 'c',
    version: '2.1.1')
pkg = import('pkgconfig')
install_headers(
    [
        'src/yajl/yajl_common.h',
        'src/yajl/yajl_gen.h',
        'src/yajl/yajl_parse.h',
        'src/yajl/yajl_tree.h'
    ],
    subdir: 'yajl'
)

yajl_inc = include_directories('src')
yajl_inc_yajl = include_directories('src/yajl')
yajl_lib = both_libraries('yajl',
    [
    	'src/yajl.c',
    	'src/yajl_alloc.c',
    	'src/yajl_buf.c',
    	'src/yajl_encode.c',
    	'src/yajl_gen.c',
    	'src/yajl_lex.c',
    	'src/yajl_parser.c',
    	'src/yajl_tree.c',
    	'src/yajl_version.c',
    ],
    include_directories: [yajl_inc, yajl_inc_yajl],
    install: true
)
yajl_dep = declare_dependency(link_with: yajl_lib,
    include_directories: yajl_inc_yajl)
pkg.generate(yajl_lib)
