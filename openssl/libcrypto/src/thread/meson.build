crypto_thread_arch_src = files(
    'arch.c',
    join_paths('arch', 'thread_win.c'),
    join_paths('arch', 'thread_posix.c'),
    join_paths('arch', 'thread_none.c'))

# IF[{- !$disabled{'thread-pool'} -}]
#   IF[{- !$disabled{quic} -}]
#     SHARED_SOURCE[../../libssl]=$THREADS_ARCH
#   ENDIF
#   $THREADS=\
#         api.c internal.c $THREADS_ARCH
# ELSE
#   IF[{- !$disabled{quic} -}]
#     SOURCE[../../libssl]=$THREADS_ARCH
#   ENDIF
#   $THREADS=api.c arch/thread_win.c
# ENDIF

# SOURCE[../../providers/libfips.a]=$THREADS

crypto_src += crypto_thread_arch_src
