FROM dhi/nginx:1-debian12 AS nginx

COPY --from=laurentgoderre689/msbuild:certs        --chown=65532:65532 --link / /certs
COPY --from=laurentgoderre689/msbuild:certs-debian --chown=65532:65532 --link /ca-certificates.crt /etc/ssl/certs/ca-certificates.crt

# ---

FROM dhi/curl:7-debian12 AS curl

COPY --from=laurentgoderre689/msbuild:certs-debian --link /ca-certificates.crt /etc/ssl/certs/ca-certificates.crt
