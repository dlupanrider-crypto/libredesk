FROM alpine:3.20
RUN apk add --no-cache ca-certificates tzdata
WORKDIR /libredesk
COPY libredesk /libredesk/libredesk
COPY config.sample.toml /libredesk/config.toml
RUN chmod 755 /libredesk/libredesk && mkdir -p /libredesk/uploads
EXPOSE 9000
CMD ["sh", "-c", "./libredesk --install --idempotent-install --yes --config /libredesk/config.toml && ./libredesk --upgrade --yes --config /libredesk/config.toml && exec ./libredesk --config /libredesk/config.toml"]
