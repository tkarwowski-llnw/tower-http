# EOS not triggering

## Repoduce steps
Start server.
```
RUST_LOG=axum_key_value_store=trace,tower_http=trace \
    cargo run --bin axum-key-value-store
```

Send a request.
```
curl -vX GET 0.0.0.0:3000/xxx
```

## Expected behaviour
In logs, we should see a warning with contents `stream closed after ...`.

## Actual behaviour
We see some `DEBUG` level logs, but not the `steam closed after ...` warning.
