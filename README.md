# 4차산업혁명 선도인재 양성 프로젝트 과정

---
## 1. Week 1 Day 19:   

***



### lightsail

https://github.com/classjohn/server_setup

os -> ubuntu 16.04



1. sudo chmod u+x
2. setup.sh 실행
3. ruby, rails 설치
4. Nginx 실행



HTTP GET / lightsail ip address ---------> Nginx + Passenger + Rails

​								web server    app server

​												app server reload 할때 touch tmp/restart.txt

​												touch로 restart.txt 파일 생성..



vi에서 v눌러서 visual mode, shift +g 누르면 전체선택, x 삭제..

rails - WEBrick 개인으로



#### Nginx & Phusion Passenger

webserver = application server



let's encrypt

http를 https



### Installing Nginx

https://gorails.com/deploy/ubuntu/16.04#nginx-passenger

sudo setup nginx start



```
sudo vi /etc/nginx/sites-enabled/default
```



rails_env에서 production -> development; 변경

root  app_name 수정..

root 폴더니까 계속 실행시켜놓도록



production 수정 후 rails 보안을 풀어줘야한다

rake secret로 보안키 확인

sudo vi config/secrets.yml에 들어가 보안키 등록



.gitignore에 추가해서 git에서 올려도 변경되지않음

/config/secrets/yml





https://github.com/classjohn/setup_guides



root로 들어갔을떄 홈을 index로

rails g controller home index



#### 배포패턴..

lightsail - production server 진짜 사람들에게 보여줄 서버

#### production변경후 할 설정

rake assets:precompile

sudo service nginx restart



로컬 컴퓨터에서 작업 ubuntu 16.04

로컬에서 project 생성 rails new

바로 서버로 올리지 않고 github에 업로드 하고  push를 통해 가지고 온다 repo생성 후

작업을 끝낸후 push를 한다..

lightsail 원격서버로 들어가서 git pull origin master

원격을 통해 pull을 통해 받아온다..



rake db:migrate RAILS_ENV=production

rake assets:precompile



database.yml

production 배포 환경 변경..



추후 capistrano를 통해 deploy 명령어로 local로 작업 끝내고 배포 쉽게 가능..





### EC2 server
