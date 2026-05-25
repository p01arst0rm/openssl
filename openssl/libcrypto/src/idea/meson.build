
crypto_idea_src = files(
    'i_cbc.c',
    'i_cfb64.c',
    'i_ofb64.c',
    'i_ecb.c',
    'i_skey.c')

# TODO
# When all deprecated symbols are removed, libcrypto doesn't export the
# idea functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=$ALL
# ENDIF

crypto_src += crypto_idea_src
