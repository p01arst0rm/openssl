
crypto_inc = include_directories('.')

#  perl to h example 
# # Generate dso_conf.h
# dso_conf_pl = configure_file(
#     configuration : crypto_configdata,
#     input : 'dso_conf.pl.in',
#     output : 'dso_conf.pl.in'
# )

dso_conf_h = custom_target(
    capture : true,
    input : dso_conf_pl,
    output : 'dso_conf.h',
    install : true,
    install_dir : meson.current_build_dir(),
    command : [
        perl,
        '@INPUT@'
    ],
)



crypto_gen_h = [
    dso_conf_h 
]
