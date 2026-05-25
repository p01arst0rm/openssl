
crypto_src += files(
    'md2_dgst.c',
    'md2_one.c')

# TODO
# When all deprecated symbols are removed, libcrypto doesn't export the
# MD2 functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=md2_dgst.c md2_one.c
# ENDIF
