

ssl_src = files(
    'bio_ssl.c',
    'methods.c',
    's3_lib.c',
    'ssl_cert_comp.c',
    'ssl_init.c',
    'ssl_utst.c',
    'tls13_enc.c',
    'd1_lib.c',
    'd1_msg.c',
    'pqueue.c',
    's3_msg.c',
    'ssl_ciph.c',
    'ssl_lib.c',
    'ssl_sess.c',
    't1_enc.c',
    'tls_depr.c',
    'ssl_asn1.c',
    'ssl_conf.c',
    'ssl_mcnf.c',
    'ssl_stat.c',
    't1_lib.c',
    'tls_srp.c',
    'd1_srtp.c',
    's3_enc.c',
    'ssl_cert.c',
    'ssl_err_legacy.c',
    'ssl_rsa.c',
    'ssl_txt.c',
    't1_trce.c')

if get_option('deprecated-3_0').enabled()
   ssl_src += files('ssl_rsa_legacy.c')
endif


if get_option('quic').enabled()

    ssl_src += files('priority_queue.c')
    ssl_shared_src += crypto_hashtable_hashfunc_c

    if get_option('siphash')
        ssl_src += crypto_siphash_c
    else 
        ssl_shared_src += crypto_siphash_c
    endif

endif


# Configure Shared Source 
#---------------------------------------------------
ssl_shared_src = ssl_src

# TODO: out of tree includes 
# include the libcrypto packet.c, time.c, and quic_vlint.c
# ssl_shared_src += [
#     crypto_packet_c,
#     crypto_quic_vlint_c,
#     crypto_time_c]


ssl_dirs = [
    'statem',
    'record',
    'rio',
    'quic']

if get_option('ech').enabled()
    ssl_dirs += 'ech'
endif

foreach dir : ssl_dirs
    subdir(dir)
endforeach

