# OpenSSL project build file
#============================================================================


project( 
    'openssl',
    ['c','cpp'],
    meson_version : '>= 1.8',
    subproject_dir : 'openssl')




subproject('depends')
subproject('libcrypto')
# subproject('libssl')
# subproject('openssl')

# if get_option('apps').enabled()
#     project_dirs += 'apps'
# endif

# if get_option('demos').enabled()
#     project_dirs += 'demos'
# endif

# if get_option('docs').enabled()
#     project_dirs += 'docs'
# endif

# if get_option('extras').enabled()
#     project_dirs += [
#         'test',
#         'fuzz',
#         'NOTES',
#         'doc',
#         'external',
#         'include',
#         'platforms',
#         'ssl',
#         'VMS']
# endif

# foreach dir : project_dirs
#     subdir(dir)
# endforeach

# crypto_lib = library(
#     'crypto',
#     crypto_src,
#     util_generated_h,
#     crypto_gen_h,
#     include_directories : [
#         openssl_inc
        
#     ]
# )

# # ssl_lib = library(
# #     'libssl',
# #     ssl_src,
# #     include_directories : [
# #         openssl_inc
# #     ]
# # )