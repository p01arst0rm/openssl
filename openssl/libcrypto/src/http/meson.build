
crypto_http_src = files(
    'http_lib.c')

if get_option('http').enabled()
    crypto_http_src += files(
        'http_client.c',
        'http_err.c')
endif

crypto_src += crypto_http_src
