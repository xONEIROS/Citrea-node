![image](https://github.com/user-attachments/assets/184a68f7-3692-402c-9820-2edf91d9cfdd)

# نصب Citrea روی اوبونتو 

 ## 1. اپدیت سرور و نصب نیازمندی ها:
```
apt update && apt upgrade -y
```
```
apt install wget curl gnome-terminal ca-certificates screen
```

## 2. میریم سراغ نصب داکر
اول دستور زیر رو کامل تو ترمینال وارد کنید :
```sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
حالا دستور زیر برای اجرای اخرین ورزن داکر :
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

خب نصب تموم شد
برای این که تست کنید درست انجام شده دستور زیر رو وارد میکنیم و اگر همه چی درست پیشرفته باشه پیام موفقیت امیز بودن میده و از صفحه خارج میشه:
```
sudo docker run hello-world
```

## 3. نصب داکر کامپوز :
با دستور زیر فایل رو از ریپازیتوری به سرور وارد میکنیم :
```
wget https://github.com/chainwayxyz/citrea/blob/v0.4.0/docker-compose.yml
```
الان کافیه با دستور زیر اسکرین جدید باز کنیم :
```
screen -S citrea
```
و در نهایت با دستور زیر نود رو ران میکنیم :
```
docker-compose up -d
```
خب نود اجرا شده و بعد از چند دقیقه نود با شبکه سینک میشه و تمام

# نکته : بهتره برای نصب این نود با یک اپ مثل `Termius` وصل بشید به سرور و دستورات رو اجرا کنید.

> ---------------------------------------

<div align="center">
    <p>
        <a href="Https://x.com/0xOneiros">
            <small>🆔 twitter </small>  
        </a>
        | 
        <a href="Https://t.me/xOneiros">
            <small>🆔 telegram </small>  
        </a>
    </p>
</div>
