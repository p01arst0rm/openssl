

ssl_src += files('poll_immediate.c')

if get_option('quic').enabled()
    ssl_src += files(
        'rio_notifier.c',
        'poll_builder.c')
endif
