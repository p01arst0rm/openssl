project( 
    'openssl',
    ['c','cpp'],
    meson_version : '>= 1.8')


# configure the compiler
#---------------------------------------------------
strict_warnings = 0



gcc_devteam_warn = [
    '-DPEDANTIC',
    '-pedantic' ,
    '-Wno-long-long',
    '-DUNUSEDRESULT_DEBUG',
    '-Wall',
    '-Wmissing-declarations',
    '-Wextra',
    '-Wno-unused-parameter',
    '-Wno-missing-field-initializers',
    '-Wswitch',
    '-Wsign-compare',
    '-Wshadow',
    '-Wformat',
    '-Wtype-limits',
    '-Wundef',
    '-Werror',
    '-Wmissing-prototypes',
    '-Wstrict-prototypes',
    '-Wpointer-arith',
    '-Wfloat-conversion']

# These are used in addition to $gcc_devteam_warn when the compiler is clang.
# TODO(openssl-team): fix problems and investigate if (at least) the
# following warnings can also be enabled:
#       -Wcast-align
#       -Wunreachable-code -- no, too ugly/compiler-specific
#       -Wlanguage-extension-token -- no, we use asm()
#       -Wunused-macros -- no, too tricky for BN and _XOPEN_SOURCE etc
#       -Wextended-offsetof -- no, needed in CMS ASN1 code
clang_devteam_warn = [
    '-Wconditional-uninitialized',
    '-Wincompatible-pointer-types-discards-qualifiers',
    '-Wno-unknown-warning-option',
    '-Wno-parentheses-equality',
    '-Wno-language-extension-token',
    '-Wno-extended-offsetof',
    '-Wno-missing-braces',
    '-Wno-tautological-constant-out-of-range-compare',    
    '-Wmissing-variable-declarations']

cl_devteam_warn = [ '/WX']


# As for $BSDthreads. Idea is to maintain "collective" set of flags,
# which would cover all BSD flavors. -pthread applies to them all,
# but is treated differently. OpenBSD expands is as -D_POSIX_THREAD
# -lc_r, which is sufficient. FreeBSD 4.x expands it as -lc_r,
# which has to be accompanied by explicit -D_THREAD_SAFE and
# sometimes -D_REENTRANT. FreeBSD 5.x expands it as -lc_r, which
# seems to be sufficient?
BSDthreads= [
    '-pthread',
    '-D_THREAD_SAFE',
    '-D_REENTRANT']


cflags = [gcc_devteam_warn]
cppflags = []

c = meson.get_compiler('c')
cpp = meson.get_compiler('cpp')


# Build
#============================================================================

crypto_util_common_src = files(
    'cryptlib.c',
    'params.c',
    'params_from_text.c',
    'bsearch.c',
    'ex_data.c',
    'o_str.c',
    'threads_pthread.c',
    'threads_win.c',
    'threads_none.c',
    'threads_common.c',
    'initthread.c',
    'context.c',
    'sparse_array.c',
    'asn1_dsa.c',
    'packet.c',
    'param_build.c',
    'param_build_set.c',
    'der_writer.c',
    'threads_lib.c',
    'params_dup.c',
    'time.c',
    'array_alloc.c',
    'aligned_alloc.c',
    'deterministic_nonce.c')

crypto_src = files(
    'mem.c',
    'mem_sec.c',
    'comp_methods.c',
    'cversion.c',
    'info.c',
    'cpt_err.c',
    'ebcdic.c',
    'uid.c',
    'o_dir.c',
    'o_fopen.c',
    'getenv.c',
    'o_init.c',
    'init.c',
    'trace.c',
    'provider.c',
    'provider_child.c',
    'punycode.c',
    'passphrase.c',
    'sleep.c',
    'quic_vlint.c',
    'time.c',
    'defaults.c',
    'ssl_err.c',
    'provider_conf.c',
    'indicator_core.c')

crypto_dirs = [
    'objects',
    'buffer',
    'bio',
    'stack',
    'lhash',
    'hashtable',
    'rand',
    'evp',
    'asn1',
    'pem',
    'x509',
    'conf',
    'txt_db',
    'pkcs7',
    'pkcs12',
    'ui',
    'kdf',
    'store',
    'property',
    'md2',
    'md4',
    'md5',
    'sha',
    'mdc2',
    'ml_kem',
    'hmac',
    'ripemd',
    'whrlpool',
    'poly1305',
    'siphash',
    'sm3',
    'des',
    'aes',
    'rc2',
    'rc4',
    'rc5',
    'idea',
    'aria',
    'bf',
    'cast',
    'camellia',
    'seed',
    'sm4',
    'chacha',
    'modes',
    'bn',
    'ec',
    'rsa',
    'dsa',
    'dh',
    'sm2',
    'dso',
    'err',
    'comp',
    'http',
    'ocsp',
    'cms',
    'ts',
    'srp',
    'cmac',
    'ct',
    'async',
    'ess',
    'crmf',
    'cmp',
    'encode_decode',
    'ffc',
    'hpke',
    'thread',
    'lms',
    'ml_dsa',
    'slh_dsa']

foreach dir : crypto_dirs
    subdir(dir)
endforeach

if get_option('uplink').enabled()

  # $UPLINKSRC_common=../ms/uplink.c
  # $UPLINKSRC_x86=$UPLINKSRC_common uplink-x86.S
  # $UPLINKSRC_x86_64=$UPLINKSRC_common uplink-x86_64.s
  # $UPLINKSRC_ia64=$UPLINKSRC_common uplink-ia64.s

  # IF[$UPLINKSRC_{- $target{uplink_arch} -}]
  #  $UPLINKSRC=$UPLINKSRC_{- $target{uplink_arch} -}
  #  $UPLINKDEF=OPENSSL_USE_APPLINK

endif

# $CPUIDASM=mem_clr.c
# $CPUIDDEF=


if get_option('uplink').enabled()

    # IF[{- !$disabled{asm} && $config{processor} ne '386' -}]
    # $CPUIDASM_x86=x86cpuid.S
    # $CPUIDASM_x86_64=x86_64cpuid.s
    # $CPUIDASM_ia64=ia64cpuid.s
    # $CPUIDASM_sparcv9=sparcv9cap.c sparccpuid.S
    # $CPUIDASM_alpha=alphacpuid.s
    # $CPUIDASM_s390x=s390xcap.c s390xcpuid.S
    # $CPUIDASM_armv4=armcap.c armv4cpuid.S
    # $CPUIDASM_aarch64=armcap.c arm64cpuid.S
    # $CPUIDASM_parisc11=pariscid.s
    # $CPUIDASM_parisc20_64=$CPUIDASM_parisc11
    # $CPUIDASM_ppc32=ppccpuid.s ppccap.c
    # $CPUIDASM_ppc64=$CPUIDASM_ppc32
    # $CPUIDASM_c64xplus=c64xpluscpuid.s
    # $CPUIDASM_riscv64=riscvcap.c riscv64cpuid.s
    # $CPUIDASM_riscv32=riscvcap.c riscv32cpuid.s
    # $CPUIDASM_loongarch64=loongarchcap.c loongarch64cpuid.s

    # Now that we have defined all the arch specific variables, use the
    # appropriate one, and define the appropriate macros
    # IF[$CPUIDASM_{- $target{asm_arch} -}]
    #     $CPUIDASM=$CPUIDASM_{- $target{asm_arch} -}
    #     $CPUIDDEF=OPENSSL_CPUID_OBJ
    # ENDIF
    # ENDIF
endif


# CPUID support.  We need to add that explicitly in every shared library and
# provider module that uses it.  ctype.c is included here because the CPUID
# uses functions from there to parse magic environment variables.
# $CPUID_COMMON=$CPUIDASM cpuid.c ctype.c

# SOURCE[../libcrypto]=$CPUID_COMMON
# DEFINE[../libcrypto]=$CPUIDDEF
# SOURCE[../providers/libfips.a]=$CPUID_COMMON
# DEFINE[../providers/libfips.a]=$CPUIDDEF

# We only need to include the CPUID stuff in the legacy provider when it's a
# separate module and it's dynamically linked with libcrypto.  Otherwise, it
# already gets everything that the static libcrypto.a has, and doesn't need it
# added again.
# IF[{- !$disabled{module} && !$disabled{shared} -}]
#   SOURCE[../providers/legacy]=$CPUID_COMMON
#   DEFINE[../providers/legacy]=$CPUIDDEF
# ENDIF

# # Implementations are now spread across several libraries, so the CPUID define
# # need to be applied to all affected libraries and modules.
# DEFINE[../providers/libcommon.a]=$CPUIDDEF
# DEFINE[../providers/libdefault.a]=$CPUIDDEF

# The Core
core_common_src = files(
    'provider_core.c',
    'provider_predefined.c',
    'core_fetch.c',
    'core_algorithm.c',
    'core_namemap.c',
    'self_test_core.c')



# SOURCE[../providers/libfips.a]=$CORE_COMMON

# Central utilities


# SOURCE[../libcrypto]=$UTIL_COMMON \

# SOURCE[../providers/libfips.a]=$UTIL_COMMON

# SOURCE[../libcrypto]=$UPLINKSRC
# DEFINE[../libcrypto]=$UPLINKDEF

# DEPEND[info.o]=buildinf.h
# DEPEND[cversion.o]=buildinf.h


# GENERATE[uplink-x86.S]=../ms/uplink-x86.pl
# GENERATE[uplink-x86_64.s]=../ms/uplink-x86_64.pl
# GENERATE[uplink-ia64.s]=../ms/uplink-ia64.pl

# GENERATE[x86cpuid.S]=x86cpuid.pl
# DEPEND[x86cpuid.s]=perlasm/x86asm.pl

# GENERATE[x86_64cpuid.s]=x86_64cpuid.pl

# GENERATE[ia64cpuid.s]=ia64cpuid.S
# GENERATE[ppccpuid.s]=ppccpuid.pl
# GENERATE[pariscid.s]=pariscid.pl
# GENERATE[alphacpuid.s]=alphacpuid.pl
# GENERATE[arm64cpuid.S]=arm64cpuid.pl
# INCLUDE[arm64cpuid.o]=.
# GENERATE[armv4cpuid.S]=armv4cpuid.pl
# INCLUDE[armv4cpuid.o]=.
# GENERATE[s390xcpuid.S]=s390xcpuid.pl
# INCLUDE[s390xcpuid.o]=.
# GENERATE[riscv64cpuid.s]=riscv64cpuid.pl
# GENERATE[riscv32cpuid.s]=riscv32cpuid.pl

# GENERATE[loongarch64cpuid.s]=loongarch64cpuid.pl
# IF[{- $config{target} =~ /^(?:Cygwin|mingw|VC-|BC-)/ -}]
#   SHARED_SOURCE[../libcrypto]=dllmain.c
# ENDIF
