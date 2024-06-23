# Please choose from the below set of Docker commands to complete your Dockerfile:

# COPY
# RUN
# ADD
# EXPOSE
# FROM
# CMD
# PUSH
# PULL
# WORKDIR

FROM golang:1.18 as builder

WORKDIR /app
COPY main.go /app

RUN go mod init guestbook
RUN go mod tidy

RUN go build -o main main.go

FROM ubuntu:18.04

#<Please fill in the required Docker command>
COPY --from=builder /app/main /app/guestbook

#<Please fill in the required Docker command>
COPY public/index.html /app/public/index.html
#<Please fill in the required Docker command>
COPY public/script.js /app/public/script.js
#<Please fill in the required Docker command>
COPY public/style.css /app/public/style.css
#<Please fill in the required Docker command>
COPY public/jquery.min.js /app/public/jquery.min.js

CMD ["./guestbook"]
#<Please fill in the required Docker command>
EXPOSE 3000
