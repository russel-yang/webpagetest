# webpagetest

in server foler
docker build -t t2gp-wptserver .
in agent folder
docker build -t t2gp-wptagent .

$ docker run -d -p 4000:80 t2gp-wptserver
$ docker run -d -p 4001:80 \
 -e "SERVER_URL=http://localhost:4000/work/" \
 -e "LOCATION=Test" \
 t2gp-wptagent
