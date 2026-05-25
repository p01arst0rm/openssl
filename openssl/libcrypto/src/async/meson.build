
crypto_async_src = files(
    'async.c',
    'async_wait.c',
    'async_err.c',
    join_paths('arch', 'async_posix.c'),
    join_paths('arch', 'async_win.c'),
    join_paths('arch', 'async_null.c'))

crypto_src += crypto_async_src