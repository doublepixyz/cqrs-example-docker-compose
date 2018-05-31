install docker-compose
----------------------
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version

-- build and run app
sudo docker-compose up

-- test
curl -X POST -H 'Content-Type: application/json' -i http://localhost:8082/api/v1/downloads --data '{
  "appId": 1,
  "downloadCount": 1
}'

curl -X GET -i http://localhost:8082/api/v1/downloads/count/1