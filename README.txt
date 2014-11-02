cd /home/ubuntu/gocode/src/github.com/buger/gor

# print one GET request per sec
sudo ./gor --input-dummy=true --output-dummy=true

# print incoming requests
sudo ./gor --input-raw :80 --output-dummy=true

# send a copy of incoming requests to a heroku app
sudo ./gor --input-raw :80 --output-http http://us-east-1-a.route.herokuapp.com --output-http-header "Host: my-app.herokuapp.com"

# send a copy of 20% of incoming requests to heroku app
sudo ./gor --input-raw :80 --output-http "http://us-east-1-a.route.herokuapp.com|20" --output-http-header "Host: my-app.herokuapp.com"