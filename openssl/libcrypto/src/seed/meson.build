
crypto_seed_src = files(
    'seed.c',
    'seed_ecb.c',
    'seed_cbc.c',
    'seed_cfb.c',
    'seed_ofb.c')

# TODO
# When all deprecated symbols are removed, libcrypto doesn't export the
# seed functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=$ALL
# ENDIF

crypto_src += crypto_seed_src
