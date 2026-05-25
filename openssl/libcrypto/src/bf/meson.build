
crypto_bf_src = files(
    'bf_skey.c',
    'bf_ecb.c',
    'bf_cfb64.c',
    'bf_ofb64.c')

# was BFASM
crypto_bf_asm_src = files(
    'bf_enc.c')


# IF[{- !$disabled{asm} -}]
#   $BFASM_x86=bf-586.S

#   # Now that we have defined all the arch specific variables, use the
#   # appropriate one
#   IF[$BFASM_{- $target{asm_arch} -}]
#     $BFASM=$BFASM_{- $target{asm_arch} -}
#   ENDIF
# ENDIF



# When all deprecated symbols are removed, libcrypto doesn't export the
# blowfish functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=$ALL
# ENDIF

# GENERATE[bf-586.S]=asm/bf-586.pl
# DEPEND[bf-586.S]=../perlasm/x86asm.pl ../perlasm/cbc.pl
# LIBS=../../libcrypto

# $BFASM=bf_enc.c
# IF[{- !$disabled{asm} -}]
#   $BFASM_x86=bf-586.S

  # Now that we have defined all the arch specific variables, use the
  # appropriate one
#   IF[$BFASM_{- $target{asm_arch} -}]
#     $BFASM=$BFASM_{- $target{asm_arch} -}
#   ENDIF
# ENDIF


# When all deprecated symbols are removed, libcrypto doesn't export the
# blowfish functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=$ALL
# ENDIF

# GENERATE[bf-586.S]=asm/bf-586.pl
# DEPEND[bf-586.S]=../perlasm/x86asm.pl ../perlasm/cbc.pl


crypto_bf_src += crypto_bf_asm_src
crypto_src += crypto_bf_src
