# 扱ったコマンド一覧

docker run -d --name envoy -p 8080:8080 -v $(pwd)/envoy.yaml:/etc/envoy/envoy.yaml envoyproxy/envoy:v1.18.3
docker restart envoy

docker-compose down
docker-compose up -d

# Jenkins
sudo lsof -i :8080 | grep LISTEN
sudo kill -9 <PID>
brew services restart jenkins-lts

# sshサーバーの設定関連
## macOSの場合はデフォルトでsshサーバーが入っているので、以下コマンドでオンに設定
sudo systemsetup -setremotelogin on

# heroku
cd ~/github.com/hijjiri/core
heroku create portfolio-simulator-core
heroku git:remote -a portfolio-simulator-core

cd ~/github.com/hijjiri/web
heroku create portfolio-simulator-web
heroku git:remote -a portfolio-simulator-web

cd ~/github.com/hijjiri/envoy
heroku create portfolio-simulator-envoy
heroku git:remote -a portfolio-simulator-envoy
