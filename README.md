<h1 align="center"> Madara & Karnot
  
![image](https://pbs.twimg.com/media/GEs4hlUXAAEf03M?format=jpg&name=large)

## حداقل سیستم مورد نیاز
### Ubunutu 20.04 or 22.04
Node name | CPU     | RAM      | SSD     |
| ------------- | ------------- | ------------- | -------- |
| Avail  | 4         | 8         | 160  |
  
## سیستم پیشنهادی
### Ubunutu 20.04 or 22.04
Node name | CPU     | RAM      | SSD     |
| ------------- | ------------- | ------------- | -------- |
| Avail  | 8         | 16         | 300  |

# اماده سازی سرور 

```
sudo apt-get update -y && sudo apt-get upgrade -y
```
### نصب rust
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```


![Ekran görüntüsü 2024-01-25 231300](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/fcfb956e-ab50-4e9d-a957-41556e883f41)
```
source $HOME/.cargo/env
```
* برای اطمینان از نصب راست کد زیررا اجرا کنید

```
rustc --version
```
* خروجی : rustc 1.75.0 (82e1608df 2023-12-21)

### نصب گیت.
```
sudo apt install git
```
### نصب داکر.

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
```
sudo apt update
```
```
sudo apt install docker-ce
```
```
sudo systemctl start docker
```
```
sudo systemctl enable docker
```

### پیش نیاز های اصلی.
```
sudo apt-get update -y && sudo apt-get upgrade -y
```
```
sudo apt install build-essential
```
```
sudo apt install pkg-config
```
```
sudo apt install libssl-dev
```
```
sudo apt install clang
```
```
sudo apt install protobuf-compiler
```

## فراخوانی برنامه;
```
git clone https://github.com/karnotxyz/madara-cli
```
```
cd madara-cli
```
```
cargo build --release
```
# کد زیر را اجرا کنید.
```
./target/release/madara init
```
* در اینجا اسم نود خود را انتخاب کنید.

![Ekran görüntüsü 2024-01-25 232028](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/855de031-ad14-46b7-88bc-011333f8765f)

* کلید ENTER را بزنید .

![Ekran görüntüsü 2024-01-25 232058](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/5de29fce-115c-42cf-a055-fcb30d827486)

* در اینجا DA مورد نظر را انتخاب میکنیم که AVAIL است .

![Ekran görüntüsü 2024-01-25 232115](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/ae813da1-c25c-4181-bda3-515043599c32)

# برنامه برای شما یک ولت جدید میسازد چنانچه به RAW SEED خود دسترسی دارید ولت خود را اضافه کنید در غیر این صورت ولتی که در اختیار شما قرار داده شده را حداقل 5 توکن شارژ کنید

# اگر کیت کوین بالای 20 دارید میتونید در دیسکورد پروژه فست دریافت کنید .


در کد زیر نام پروژه را پاک کرده و اسم پروژه خودتون را بگذارید.
```
nano /root/.madara/app-chains/"نام پروژه"/da-config.json
```
![Ekran görüntüsü 2024-01-25 232340](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/88e2fd32-1109-4d78-8f1a-dce8902d44be)

* اینجا میتوانید ولت ساخته شده توسط برنامه را با ولت خودتان تعویض کنید.

* کلید enter را بزنید .

### برای راه اندازی فایر وال و باز کردن پورت های لازم دستورات زیر را وارد کنید .
```
sudo ufw enable
sudo ufw allow 22
sudo ufw allow 4000
sudo ufw allow 5353
sudo ufw allow 47250
sudo ufw allow 39276
sudo ufw allow 36347
sudo ufw allow 43759
sudo ufw allow 40815
sudo ufw allow 30333
sudo ufw allow 9944
sudo ufw allow 9615
```
### برنامه screen را نصب میکنیم
```
sudo apt install screen
```
```
screen -S roller
```
### زنجیره را شروع میکنیم.

```
./target/release/madara run
```
زمانی که بلاک ها شروع به صادر شدن کردند کلید CTRL + A + D را میفشاریم.

### برای ساخت صفحه اکسپلورر کد های زیر را اجرا میکنیم 
```
cd
cd madara-cli
./target/release/madara explorer --host=آیپی شما
```
به جای your ip ادرس ایپی خود را وارد کنید . http://yourip:4000 تا وارد اکسپلور شوید.

![Ekran görüntüsü 2024-01-26 003113](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/b568b4b2-d4ab-4e9d-a2df-92c06fe9afb3)

### پابلیش نود

کد زیر را کپی کنید.
```
  {
    "name": "App Name",
    "logo": "Your Image Link",
    "rpc_url": "http://IP:9944",
    "explorer_url": "http://IP:4000",
    "metrics_endpoint": "http://IP:9615/metrics", 
    "id": "812de564-4f60-4ea0-b35f-5e7143769fbc"
  }
```
* برای دریافت uid به این  [لینک](https://www.uuidgenerator.net/) وارد شوید و ایدی جدید بسازید و اون رو داخل فایل جیسون قرار بدید.

![Ekran görüntüsü 2024-01-27 215100](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/3f519de4-93c8-4167-8545-786729ba784c)

برای تصویر ولیدیتور یک تصویر 400*400 بسازید و اون رو در این لینک اپلود کنید. [لینک](https://resimlink.com/)

![Ekran görüntüsü 2024-01-27 215606](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/b336b64a-e32c-44b3-b8b3-e7b5d320fe18)

* صرفا لینک direct link رو بردارید.

* فایل جیسون را با عنوان uid که ساختید ذخیره کنید.

![Ekran görüntüsü 2024-01-27 220406](https://github.com/CoinHuntersTR/Avail-Full-Node/assets/111747226/67f0ebd0-44eb-4309-bae2-39fd9286dc37)


## لینک ها.

[لینک ریپازتوری اصلی پروژه](https://github.com/karnotxyz/avail-campaign-listing).


[برای مشاهده لیدر برد کلیک کنید](https://leaderboard.availproject.org/).

[داکیومنتیشن برای نصب نود ورژن 14 به بالا ](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04).


### برای فیکس کردن مشکل pull request ( توضیحات در ویدیو یوتیوب )

```
npx prettier --check yourfileontheserver.json

npx prettier --write yourfileontheserver.json


```

ادامه کار را در ویدیو یوتیوب ببینید 

کلمه پیش فرض 
✨ Adding nodename .





