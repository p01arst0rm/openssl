
subdir('methods')

ssl_src += files(
    'rec_layer_s3.c',
    'rec_layer_d1.c')


# Needed for the multiblock code in rec_layer_s3.c
if get_option('asm').enabled()
    AESDEF_x86='AES_ASM'
    AESDEF_x86_64='AES_ASM'

    #  TODO: what does this do? :)
    # IF[$AESDEF_{- $target{asm_arch} -}]
    #     $AESDEF=$AESDEF_{- $target{asm_arch} -}
    # ENDIF

endif

# TODO: what does this do? :)  
# DEFINE[../../libssl]=$AESDEF

