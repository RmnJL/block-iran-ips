# block iran ips
# RaminJL

با این روش شما به صورت دستی با استفاده از فایروال آی پی ها رو می بندید
```
sudo apt update -y && sudo apt upgrade -y
```
```
sudo ufw disable
```
```
sudo apt install ufw libapache2-mod-geoip geoip-database -y && a2enmod geoip && apt install geoip-bin -y
```
```
sudo apt install curl -y
```
```
curl -sSL https://www.ipdeny.com/ipblocks/data/countries/ir.zone | awk '{print "sudo ufw deny out from any to " $1}' | bash
```

فقط قبل از اینکه دستور آخر رو بزنید باید پورت هایی که استفاده می کنید رو در فایروالتون اضافه کنید وگرنه از دسترس خارج می شه مجبور می شید سرورتون رو ریبیلد کنید و همه کار ها رو از اول انجام بدید

برای مثال : (من از پورت 8081 در اپاچی استفاده میکنم و از پورت 1188 در nginx و پورت ترمینال یا ssh بنده 22 هستش و یک پورت udp دارم 7100)

Port 22 , 1188 , 8081 , ...

```
ufw allow 22/tcp
```
```
ufw allow 1188/tcp
```
```
ufw allow 8081/tcp
```
```
ufw allow 7100/udp
```
و در نهایت فایروال رو فعال می کنید

```
ufw enable
```
