#QUIC TLS API is available even in the event of no-quic
ssl_src += files(
    'quic_tls.c',
    'quic_tls_api.c')

if get_option('quic').enabled()
    ssl_src += files(
        'quic_method.c',
        'quic_impl.c',
        'quic_wire.c',
        'quic_ackm.c',
        'quic_statm.c',
        'cc_newreno.c',
        'quic_demux.c',
        'quic_record_rx.c',
        'quic_record_tx.c',
        'quic_record_util.c',
        'quic_record_shared.c',
        'quic_wire_pkt.c',
        'quic_rx_depack.c',
        'quic_fc.c',
        'uint_set.c',
        'quic_cfq.c',
        'quic_txpim.c',
        'quic_fifd.c',
        'quic_txp.c',
        'quic_stream_map.c',
        'quic_sf_list.c',
        'quic_rstream.c quic_sstream.c',
        'quic_reactor.c',
        'quic_reactor_wait_ctx.c',
        'quic_channel.c',
        'quic_port.c',
        'quic_engine.c',
        'quic_tserver.c',
        'quic_thread_assist.c',
        'quic_trace.c',
        'quic_srtm.c',
        'quic_srt_gen.c',
        'quic_lcidm.c',
        'quic_rcidm.c',
        'quic_types.c',
        'qlog_event_helpers.c',
        'quic_obj.c')
    
    if get_option('qlog').enabled()
        
        ssl_src += files(
            'json_enc.c',
            'qlog.c')

        # TODO: Out of Tree build        
        # ssl_shared_src += [
        #     crypto_getenv_c,
        #     crypto_ctype_c]
    endif
endif