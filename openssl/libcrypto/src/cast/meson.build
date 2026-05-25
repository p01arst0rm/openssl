
crypto_cast_src = files(
    'c_skey.c',
    'c_ecb.c',
    'c_cfb64.c',
    'c_ofb64.c')

crypto_cast_asm_src = files(
    'c_enc.c')

# CAST assembly source is not PIC
# IF[{- !$disabled{asm} && $disabled{pic} -}]
#   $CASTASM_x86=cast-586.S

#   # Now that we have defined all the arch specific variables, use the
#   # appropriate one
#   IF[$CASTASM_{- $target{asm_arch} -}]
#     $CASTASM=$CASTASM_{- $target{asm_arch} -}
#   ENDIF
# ENDIF

# When all deprecated symbols are removed, libcrypto doesn't export the
# cast functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=$ALL
# ENDIF

# GENERATE[cast-586.S]=asm/cast-586.pl
# DEPEND[cast-586.S]=../perlasm/x86asm.pl ../perlasm/cbc.pl


crypto_cast_src += crypto_cast_asm_src
crypto_src += crypto_cast_src
