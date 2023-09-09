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

فقط قبل از اینکه دستور آخر رو بزنید باید پورت هایی که استفاده می کنید رو در فایروالتون اضافه کنید وگرنه از دسترس خارج می شه مجبور می شید همه کار ها رو از اول انجام بدید
برای مثال :

Port 22 , 443 , 80 , ...

```
ufw allow 22/tcp
```
```
ufw allow 80/tcp
```
```
ufw allow 443/tcp
```
یا
```
ufw allow ssh
```
```
ufw allow http
```
```
ufw allow https
```
و در نهایت فایروال رو فعال می کنید

```
ufw enable
```
