
crypto_dsa_src = files(
    'dsa_asn1.c',
    'dsa_err.c',
    'dsa_ameth.c',
    'dsa_prn.c',
    'dsa_meth.c')

crypto_dsa_common_src = files(
    'dsa_sign.c',
    'dsa_vrf.c',
    'dsa_lib.c',
    'dsa_ossl.c',
    'dsa_check.c',
    'dsa_key.c',
    'dsa_backend.c',
    'dsa_gen.c')


# IF[{- !$disabled{'deprecated-0.9.8'} -}]
#   SOURCE[../../libcrypto]=dsa_depr.c
# ENDIF
# SOURCE[../../providers/libfips.a]=$COMMON

crypto_dsa_src += crypto_dsa_common_src
crypto_src += crypto_dsa_src
