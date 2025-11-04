FROM tinygo/tinygo:0.29.0 AS builder

WORKDIR /workspace

COPY fullcycle/ .

ENV GOOS=linux
ENV GOARCH=386

RUN tinygo build -o /tmp/fullcycle

FROM scratch

WORKDIR /app

COPY --from=builder /tmp/fullcycle /app/fullcycle

CMD ["./fullcycle"]