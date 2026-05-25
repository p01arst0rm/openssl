

# IF[{- !$disabled{asm} -}]
#   $AESASM_x86=aes-586.S
#   $AESDEF_x86=AES_ASM
#   $AESASM_x86_sse2=vpaes-x86.S aesni-x86.S
#   $AESDEF_x86_sse2=VPAES_ASM OPENSSL_IA32_SSE2

#   $AESASM_x86_64=\
#         aes-x86_64.s vpaes-x86_64.s bsaes-x86_64.s aesni-x86_64.s \
#         aesni-sha1-x86_64.s aesni-sha256-x86_64.s aesni-mb-x86_64.s \
#         aesni-xts-avx512.s aes-cfb-avx512.s
#   $AESDEF_x86_64=AES_ASM VPAES_ASM BSAES_ASM

#   $AESASM_ia64=aes_core.c aes_cbc.c aes-ia64.s
#   $AESDEF_ia64=AES_ASM

#   $AESASM_sparcv9=\
#         aes_core.c aes_cbc.c aes-sparcv9.S aest4-sparcv9.S aesfx-sparcv9.S
#   $AESDEF_sparcv9=AES_ASM

#   $AESASM_mips32=aes_cbc.c aes-mips.S
#   $AESDEF_mips32=AES_ASM
#   $AESASM_mips64=$AESASM_mips32
#   $AESDEF_mips64=$AESDEF_mips32

#   $AESASM_s390x=aes-s390x.S
#   # aes-390x.S implements AES_ctr32_encrypt and AES_xts_[en|de]crypt
#   $AESDEF_s390x=AES_ASM AES_CTR_ASM AES_XTS_ASM

#   $AESASM_armv4=aes_cbc.c aes-armv4.S bsaes-armv7.S aesv8-armx.S
#   $AESDEF_armv4=AES_ASM BSAES_ASM
#   $AESASM_aarch64=\
#         aes_core.c aes_cbc.c aesv8-armx.S bsaes-armv8.S vpaes-armv8.S \
#         aes-sha1-armv8.S aes-sha256-armv8.S aes-sha512-armv8.S
#   $AESDEF_aarch64=BSAES_ASM VPAES_ASM

#   $AESASM_parisc11=aes_core.c aes_cbc.c aes-parisc.s
#   $AESDEF_parisc11=AES_ASM
#   $AESASM_parisc20_64=$AESASM_parisc11
#   $AESDEF_parisc20_64=$AESDEF_parisc11

#   IF[{- $target{sys_id} ne "MACOSX" -}]
#     $AESASM_ppc32=aes_core.c aes_cbc.c aes-ppc.s vpaes-ppc.s aesp8-ppc.s
#   ELSE
#     $AESASM_ppc32=aes_core.c aes_cbc.c aes-ppc.s vpaes-ppc.s
#   ENDIF
#   $AESDEF_ppc32=AES_ASM VPAES_ASM
#   $AESASM_ppc64=$AESASM_ppc32
#   $AESDEF_ppc64=$AESDEF_ppc32

#   $AESASM_c64xplus=aes-c64xplus.s aes_cbc.c
#   # aes-c64xplus.s implements AES_ctr32_encrypt
#   $AESDEF_c64xplus=AES_ASM AES_CTR_ASM

#   $AESASM_riscv64=aes_cbc.c aes-riscv64.s aes-riscv64-zkn.s aes-riscv64-zvkb-zvkned.s aes-riscv64-zvkned.s aes-riscv64-zvbb-zvkg-zvkned.s
#   $AESDEF_riscv64=AES_ASM
#   $AESASM_riscv32=aes_core.c aes_cbc.c aes-riscv32-zkn.s

#   $AESASM_loongarch64=aes_core.c aes_cbc.c vpaes-loongarch64.S
#   $AESDEF_loongarch64=VPAES_ASM

#   # Now that we have defined all the arch specific variables, use the
#   # appropriate one, and define the appropriate macros
#   IF[$AESASM_{- $target{asm_arch} -}]
#     $AESASM=$AESASM_{- $target{asm_arch} -}
#     $AESDEF=$AESDEF_{- $target{asm_arch} -}
#     IF[{- !$disabled{sse2} -}]
#       $AESASM=$AESASM $AESASM_{- $target{asm_arch} -}_sse2
#       $AESDEF=$AESDEF $AESDEF_{- $target{asm_arch} -}_sse2
#     ENDIF
#   ENDIF
# ENDIF
