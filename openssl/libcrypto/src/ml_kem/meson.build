
crypto_ml_kem_common_src = files(
    'ml_kem.c')


# TODO
# $MLKEMASM=
# IF[{- !$disabled{asm} -}]
#   $MLKEMDEF_ppc64=MLKEM_NTT_PPC_ASM

#   IF[{- $target{sys_id} ne "AIX" && $target{sys_id} ne "MACOSX" -}]
#     $MLKEMASM_ppc64=asm/mlkem_ntt_ppc64le.S asm/mlkem_intt_ppc64le.S
#   ENDIF

#   # Now that we have defined all the arch specific variables, use the
#   # appropriate one, and define the appropriate macros
#   IF[$MLKEMASM_{- $target{asm_arch} -}]
#     $MLKEMASM=$MLKEMASM_{- $target{asm_arch} -}
#     $MLKEMDEF=$MLKEMDEF_{- $target{asm_arch} -}
#   ENDIF
# ENDIF

#crypto_ml_kem_common_src += $MLKEMASM

# IF[{- !$disabled{'ml-kem'} -}]
#     SOURCE[../../libcrypto]=$COMMON
#     SOURCE[../../providers/libfips.a]=$COMMON
# ENDIF

# Implementations are now spread across several libraries, so the defines
# need to be applied to all affected libraries and modules.
# DEFINE[../../libcrypto]=$MLKEMDEF
# DEFINE[../../providers/libfips.a]=$MLKEMDEF
