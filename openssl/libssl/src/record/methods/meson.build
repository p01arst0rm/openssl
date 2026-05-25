

ssl_src += files(
    'tls_common.c',
    'tls1_meth.c',
    'tls13_meth.c',
    'tlsany_meth.c',
    'dtls_meth.c',
    'tls_multib.c')


ktls_src = []
if get_option('ktls').enabled()
    ktls_src += files('ktls_meth.c')
endif

if get_option('deprecated-3_0').enabled()
    ssl_src += files('ssl3_cbc.c')
endif

# TODO: out of tree include. needs a fix
# SOURCE[../../../providers/libdefault.a ../../../providers/libfips.a]=ssl3_cbc.c

# For shared builds we need to include the sources needed in providers
ssl_shared_src += 'tls_pad.c'

# TODO: out of tree include. needs a fix
# SOURCE[../../../providers/libcommon.a]=tls_pad.c

