
crypto_dh_src = files(
    'dh_asn1.c',
    'dh_err.c',
    'dh_ameth.c',
    'dh_prn.c',
    'dh_rfc5114.c',
    'dh_meth.c')

crypto_dh_common_src = files(
    'dh_lib.c',
    'dh_key.c',
    'dh_group_params.c',
    'dh_check.c',
    'dh_backend.c',
    'dh_gen.c',
    'dh_kdf.c')


# IF[{- !$disabled{'deprecated-0.9.8'} -}]
#   SOURCE[../../libcrypto]=dh_depr.c
# ENDIF

# SOURCE[../../providers/libfips.a]=$COMMON

crypto_src += [
    crypto_dh_src,
    crypto_dh_common_src]