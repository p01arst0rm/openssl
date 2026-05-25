crypto_rc5_src = files(
    'rc5_skey.c',
    'rc5_ecb.c',
    'rc5cfb64.c',
    'rc5ofb64.c')

# was RC5ASM
crypto_rc5_asm_src = files(
    'rc5_enc.c')

# IF[{- !$disabled{asm} -}]
#   $RC5ASM_x86=rc5-586.S

#   # Now that we have defined all the arch specific variables, use the
#   # appropriate one, and define the appropriate macros
#   IF[$RC5ASM_{- $target{asm_arch} -}]
#     $RC5ASM=$RC5ASM_{- $target{asm_arch} -}
#     $RC5DEF=RC5_ASM
#   ENDIF
# ENDIF

# When all deprecated symbols are removed, libcrypto doesn't export the
# rc5 functions, so we must include them directly in liblegacy.a
# IF[{- $disabled{'deprecated-3.0'} && !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../../providers/liblegacy.a]=$ALL
# ENDIF

# GENERATE[rc5-586.S]=asm/rc5-586.pl
# DEPEND[rc5-586.S]=../perlasm/x86asm.pl ../perlasm/cbc.pl

crypto_rc5_src += crypto_rc5_asm_src
crypto_src += crypto_rc5_src
