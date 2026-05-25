
crypto_bio_base_src = files(
    'bio_lib.c',
    'bio_cb.c',
    'bio_err.c',
    'bio_print.c',
    'bio_dump.c',
    'bio_addr.c',
    'bio_sock.c',
    'bio_sock2.c',
    'bio_meth.c',
    'ossl_core_bio.c')

# Source / sink implementations
crypto_bio_srcsink_src = files(
    'bss_null.c',
    'bss_mem.c',
    'bss_bio.c',
    'bss_fd.c',
    'bss_file.c',
    'bss_sock.c',
    'bss_conn.c',
    'bss_acpt.c',
    'bss_dgram.c', 
    'bss_log.c',
    'bss_core.c',
    'bss_dgram_pair.c')

# Filters
crypto_bio_filters_src = files(
    'bf_null.c',
    'bf_buff.c',
    'bf_lbuf.c',
    'bf_nbio.c',
    'bf_prefix.c',
    'bf_readbuff.c')

crypto_src += [
    crypto_bio_base_src,
    crypto_bio_srcsink_src,
    crypto_bio_filters_src]

