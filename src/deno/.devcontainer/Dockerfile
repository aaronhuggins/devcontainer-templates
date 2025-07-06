FROM denoland/deno:${templateOption:denoVariant} AS deno
FROM fedora:${templateOption:imageVariant}
RUN dnf install -y --refresh curl wget ca-certificates
COPY --from=deno /deno /usr/local/bin/deno