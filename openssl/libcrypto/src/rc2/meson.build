
crypto_rc2_src = files(
    'rc2_ecb.c',
    'rc2_skey.c',
    'rc2_cbc.c',
    'rc2cfb64.c',
    'rc2ofb64.c')


# TODO
# When all deprecated symbols are removed, libcrypto doesn't export the
# rc2 functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=$ALL
# ENDIF

crypto_src += crypto_rc2_src
