# 42-born2beroot-yardimci-notlar
## ***Sanal makine nasıl çalışır?***

Virtual box vb. programlar ile işletim sistemi içinde sanal makine oluşturarak birden çok işletim sistemi kullanmaya imkan sağlanır.

sanal makine gerçek bir bilgisayar gibi işlev gören ama fiziksel olmayan bir bilgisayar dosyasıdır. Birinci bilgisayara müdahale edemez.

## ***Sanal makinenın amacı nedir?***

Aynı makineda, birden çok işletim sistemini aynı anda kullanma imkanı sağlar. virüslü olduğunu düşündüğümüz dosyayı burada test edebiliriz. Hazırladığımız web sitesinin farklı işletim sistemlerinde nasıl çalışacağını test edebiliriz.

En önemli avantajı büyük bir güvenlik sağlıyor olması. çünkü sanal makinen sağladığı kaynağı kullanan yazılım, içinde bulunduğu sanal ortamın dışına çıkamaz. host üzerinde bir değişikliği sebep olamaz.

## **CentOS ve Debian arasındaki temel farklar?**

CentOS yeni sürümleri genellikle uzun bir aradan sonra yayınlanır ve bu nedenle bu sistemler çok kararlıdır. Debian CentOSa göre daha fazla güncelleme alıyor. CentOSun arayüzü karışıktır. Debianın daha kolay.

## **Aptitude ve Apt arasındaki temel farklar?**

İkisi de Debianın paket yöneticisidir. paket kurma,kaldırma,arama vs. her türlü etkinliği gerçekleştirebilir.aptitude arayüze sahipken apt değildir. Aptitude sisteme yüklediğimiz paketleri otomatik izler. apt-get bu konuda yetersiz. Aptitude yaptığımız işlemlerin kaydını tutar.

## **APPArmor nedir?**

ubuntuya varsayılan olarak dahil edilen önemli bir güvenlik özelliğidir. arka planda sessizce çalışır. sisteme zarar verebilecek ayarları, servisleri ve diğer ayarları kontrol edip sınırlandırır. sistem açılışında varsayılan olarak aktiftir.

## **LVM nasıl çalışır ve neyle ilgilidir?**

LVM birden fazla diski tek bir disk bölümü olarak kullanabilir. Disk alanının yetersiz kaldığı durumlarda LVM ile oluşturulan disk veri kümesine kolaylıkla yeni disk ve disk bölümleri ilave edebilir, ihtiyaca göre disk alanı şekillendirilebilir.

VM de ilk olarak tüm disk alanı sanal makinaya tahsis edilmez. ihtiyaç olduğunda ise lvm sayesinde sanal makineye ihtiyacı kadar alan yeniden tahsis edilir, boyutlandırılır.

## **SUDO nedir?**

sudo, sıradan kullanıcılan sisteme yönetici olarak bağlanmaları gerekmeden yönetici yetkisi gerektiren işlemleri yapabilmesini sağlayan bir programdır.

## **UFW nedir?**

Port ve güvenlik duvarı işlemlerini gerçekleştirmemize olanak veren bir güvenlik duvarı aracıdır. genel olarak SSH işlemleri içerisinde port açma/kapatma/değiştirme aşamalarında faydalanırız.

## **SSH nedir?**

uzaktaki bir sunucuya bağlanmak, ona komutlar ve dosyalar göndermek üzere kullanılan şifrelenmiş bir uzaktan sağlayıcı protokolüdür. sadece belirlediğimiz adreslerden SSH erişimi sağlamak istiyorsak UFW burada çok işe yarar.

Rocky ve debian arasındaki farklar

- Debian paket yöneticisi apt rocky yum
- rocky nin sürümleri uzun süre sonra güncelleme çok kararlıdır
- debian rocky e göre daha çok güncelleme alır
- rocky kurumsal alanda daha fazla tercih edilir debian ise bireysel
- rocky redhat toplulugu tarafından desteklenir
- rocky kendine ait bir siber güvenlik sistemiyle gelir Selinux
- rocky arayüzü daha karışıktır debian daha basit

### Aptitude ve apt arasındaki farklar

- apt “Advanced Packaging Tool”
- aptitude işlevsellik açısındak apt den daha geniştir apt nin işlevlerini bünyesinde barındırır
- aptitude arayüze sahiptir
- aptitude sisteme yüklenen paketleri otomatik olarak izler
- aptitude paket kurulumunda o paket tarafından tavsiye edilen paketleri de beraber kurar
- aptituded paketlerin ismi tanımları bağımlılıkları gibi bir çok bilgiye kolayca ulaşabilmemizi sağlar
- aptitude eski paketin dağıtımı durdurulmuş olabilir bu yüzden bunları takip eder siler apt sistemde bulunddurmaya devam eder
- aptitude yaptıgınız işlemlerin logunu tutar aptitude ile kurulan kaldırılan güncellenenn paketlerin kaydını /var/log/aptitude dosyasında tutar.
- son kullanıcı memnuniyeti düşünülerek yapılmış bir komut

### APPARMOR nedir

- Apparmor bir güvenlik özelligi arka planda sessize çalışır sisteme zarar verebilcek ayarları servisleri ve diğer ayarları kontrol edip sınırlandırır sistem açılışında default olarak aktiftir.
- ubuntu için geliştirilmiş olan security framework yapısdır red hat ve fedora sistemlerindeki selinux benzer bir yapısı bulunmaktadır.
- apparor sisteme verebilcek zararı sınırlandırır veya yapılan bu işlemi tamamen durduran bir uygulamadır.
- selinux ve apparmor ikisi de MAC(Mandatory Access Control)zorunlu erişim kontrolü güvenligini sağlamaktadır
- apparmorun sistemizdeki durrumunu öğrenmek için apparmor-status komutunu vermemiz gerekir.

### “chage -l username” komutu ile şifre yenileme politikalarının her bir kullanıcıda nasıl oldugunu ögrenebiliriz.

### İşletim sistemini nasil görüntüleriz ?

“uname -a” (all sistem info) 

### oturum açma bilgilerine hangi kod ile ulaşırız ?

cat /etc/passwdd | grep home 

id username

### Yeni bir kullanıcı oluşturmak için:

aduser username    —>    yüksek seviyeli

useradd     —>     düşük seviyeli

sudo vim /etc/login.defs >> burada max 30 gün min 2 gün warn 7 gün olarak ayarlanır

enforcing eğer sıfırdan farklı bir değer aldıysa yazılan şifre katı şifre politikalarına uymuyorsa girilen şifreyi reddeder enforcing = 0 yazıldıgında ise girilen şifre katı şifre politşkalarına uymasa da yalnızca warning hayasi verir ve girilen düşük seviyeli şifreyi kabul eder

### evaluating    adında bir grup oluşturma

addgruop evo 

`$ sudo deluser tecmint postgres` kullanıcıya verilen grubu silme

cat /etc/group | grep evo >> kurulan grubu gör

usermode -aG evo user42 >> evo grubuna kullanıcı ekledik

id faruk42 YADA

groups faruk42 >> ile grupları gösteririz

---

lsblk sanal maine bölümleri ile ilgili ayrıntılı bilgiler verir 

SDA ilk diski temsil edr sonrakli blok cihaz bölümleri sda’nin yanında ondalık sayı alarak gösterilir

RO: READ-ONLY

sr0: çıkarılabilir cihazi temsil eder cd-rom listelenen cihazlar içinde çıkarılabilir olup olmayanlari gösteren bölüm “RM” dur (RM: REMOVABLE)

RM= 0 İSE ÇIKARILAMAZ

RM = 1 ÇIKARILIR 

sda birincil cihazdır 

sda(1-4) arasi öncelikli cihazları temsil ederken sda4 sonrası logical birimler olduklarını gösterir.

mountpoint = bu cihazın monte edildigi bağlamak noktasını görüntüler

---

## yeni bir kullanıcı oluştururken

- sudo adduser <username>
- sudo chage -l <username> —> şifre politikalarına uyup uymadıgını gösterir
- sudo adduser <username> sudo —> sudo grubuna ekler
- sudo adduser <username> user42 —> user42 grubuna ekler

---

lsblk partitions kontrolü

sudo aa-status —> AppArmor status

getent group sudo —> sudo kullanıcılarını gösterir

sudo systemctl status ssh

sudo ufw status

/etc/sudoers.d/filename —> sudo config file

---

### Nasıl hostname degiştirilir?

sudo hostnamectl set-hostname faruk42 —> hostname’yi faruk42 olarak degiştirir.

aynı zamanda /etc/hosts içerisinden de hostname yi degiştirmemiz gerekir.

sudo reboot

### Sudo loglarının tutuldugu dosya nerededir ?

/var/log/sudo

### Ufw’ye nasıl 8080 portu eklenir ve silinir ?

sudo ufw allow 8080

sudo ufw status numbered (listeyi 1,2,3 sıralar)

sudo ufw delete 2 

### Ssh nedir ?

SSH, Secure Shell protokolünün kısaltmasıdır. Türkçe anlamı, Güvenli Kabuk olarak geçmektedir. Bir bilgisayar ile uzak bir bilgisayar arasında güvenli bir bağlantı kurulum yapılmasını sağlayan bir ağ protokolüdür. SSH protokolü ile birlikte bir kişi, bağlanacağı uzak sunucuya erişim sağlaması durumunda sunucu için de istediği şekilde yönetimi sağlayabilir. SSH bağlantısı yapılması durumunda bağlanan kişi aşağıdaki işlemleri gerçekleştirebilir. Sunucu dosya ve klasör yönetimini gerçekleştirebilir. klasör ve dosyalar da erişim izinlerini değiştirebilir. Sunucuda bulunan dosyaların içeriklerini değiştirebilir. Bunların yanı sıra sunucu üzerinde her türlü işlemi gerçekleştirebilir.

Kimi zaman kullanıcılar, SSH ile FTP bağlantısını aynı olduğunu düşünebilir ancak, SSH ile FTP protokolleri farklıdır. FTP protokolü ile birlikte sadece dosya yönetimini gerçekleştirebilirken, SSH protokolü ile sunucuya bağlanmanız durumunda sunucu içerisindeki tüm dosya, uygulama gibi sunucunun tamamında bir yönetime sahip olursunuz.

### Sudo nedir ?

Normal kullanıcılar olarak işletim sistemlerinde zaman zaman yönetici yetkisi gerektiren işlemler yapmamız gerekir. `sudo` sıradan kullanıcıların, sisteme yönetici olarak bağlanmaları gerekmeden yönetici yetkisi gerektiren işlemleri yapabilmesini sağlayan bir programdır.

Aşağıda görülen örnekte `joe`
 kullanıcısı için ilk `ALL`
 ile bütün terminal ve makinelerden, ikinci `ALL`
 ile `root`
 dahil bütün kullanıcıların yerine, üçüncü `ALL`
 ile ise bütün komutları koşturma hakkı tanınmıştır.

## **MONİTORİNG dosyası içeriği**

```
#!/bin/bash
 arc=$(uname -a)
 pcpu=$(grep "physical id" /proc/cpuinfo | sort | uniq | wc -l)
 vcpu=$(grep "^processor" /proc/cpuinfo | wc -l)
 fram=$(free -m | grep Mem: | awk '{print $2}')
 uram=$(free -m | grep Mem: | awk '{print $3}')
 pram=$(free | grep Mem: | awk '{printf("%.2f"), $3/$2*100}')
 fdisk=$(df -Bg | grep '^/dev/' | grep -v '/boot$' | awk '{ft += $2} END {print ft}')
 udisk=$(df -Bm | grep '^/dev/' | grep -v '/boot$' | awk '{ut += $3} END {print ut}')
 pdisk=$(df -Bm | grep '^/dev/' | grep -v '/boot$' | awk '{ut += $3} {ft+= $2} END {printf("%d"), ut/ft*100}')
 cpul=$(top -bn1 | grep '^%Cpu' | cut -c 9- | xargs | awk '{printf("%.1f%%"), $1 + $3}') lb=$(who -b | awk '$1 == "system" {print $3 " " $4}')
 lvmt=$(lsblk -o TYPE | grep "lvm" | wc -l)
 lvmu=$(if [ $lvmt -eq 0 ]; then echo no; else echo yes; fi)
 # net-tools araclari gerekli:
 ctcp=$(cat /proc/net/tcp | wc -l | awk '{print $1-1}' | tr '' ' ')
 ulog=$(users | wc -w)
 ip=$(hostname -I)
 mac=$(ip link show | awk '$1 == "link/ether" {print $2}')
 # Journalctl calistirilabilir cunku komut dosyasi sudo cron'dan yurutulur.
 cmds=$(journalctl _COMM=sudo | grep COMMAND | wc -l)
 wall " #Architecture: $arc#CPU physical: $pcpu
 #vCPU: $vcpu
 #Memory Usage: $uram/${fram}MB ($pram%) #Disk Usage: $udisk/${fdisk}Gb ($pdisk%) #CPU load: $cpul
 #Last boot: $lb
 #LVM use: $lvmu
 #Connexions TCP : $ctcp ESTABLISHED
 #User log: $ulog
 #Network: IP $ip ($mac)
 #Sudo: $cmds cmd"
```

sort → alfabetik sıralar

uniq → tekrar eden satırları ayırır.

$1,$2 → sutünları tutar

xargs → öncesinde kullanılan çıktıyı bir sonraki komuta iletir.

arc -> mevcut işletim sisteminin mimarisini ve kernel versiyonunu gösterir

pcpu-> fiziksel işlemci sayısı

vcpu-> sanal işlemci sayısı

fram -> sunucunun erişilebilir ram miktarı

uram -> kullanılan ram miktarı

pram -> yüzde olarak kullanılan miktarı verir

fdisk -> sunucunun erişilebilir depolama alanı

udisk -> sunucunun kullanılan depolama alanı

pdisk-> udisk/fdisk *100 bize yüzde olarak kullanımını verir

cpul-> yüzde olarak işlemci kullanım oranını verir.

lb -> son yeniden başlatma tarihi ve saati

lvmt -> LVM ile yapılandırılmış diskin bilgisini verir.

lvmu-> LVMnin aktif olma bilgisini verir

ctcp-> mevcut aktif bağlantı sayısı

ulog-> sunucuyu kullanan kullanıcı sayısı

ip -> sunucu ip adresi verir

mac-> sunucu mac adresi verir

cmds-> sudo ile çalıştırılmış komut sayısı

Cpu physical -> işlemci

vCpu → sanal işlemci sayısı

CPU load → Anlık işlemci yükü/kullanımı

Last boot → sanal makinenin en son açıldığı an

Connexions TCP → ssh ile sunucuyla bağlantı kuranların sayısı

Free bellek hakkında bilgi, kullanılan alan, kapasite, boş alan vs…. Free -m : mebi byte

Awk komutu -> grepe benzer şekilde örüntü temelli tarama işlemi

Top -> sunucu hakkındaki anlık istatistikleri verir.

**Parola gücü Politikasını Ayarlamak İçin:**

```
sudo vim /etc/pam.d/common-password
```

**TTY Nedir ?**

Günümüzde işletim sisteminde terminal olarak işlev görebilen tüm device’lara erişim için kullanılan alt sisteme **TTY** denilmektedir. Yani **TTY** artık fiziksel bir cihaz yerine gerçek veya sanal terminal olarak düşünülmeli.

**PTS ve TTY arasındaki fark nedir?**

- **TTY** normal bir terminal cihazıdır (örneğin sunucunuzdaki konsol).
- **PTS**, sanal/taklit (uzak) terminal bağımlısıdır (bir xterm veya **ssh** bağlantısı).

Yine güvenlik sebebiyle, **sudo** tarafından kullanılan dizinler sınırlandırılmalıdır.

- Aşağıdaki komutu ekliyoruz ( eğer böyle bir komut varsa ilgili komutu düzenliyoruz.)

**Şifre Yaşı**

Parola yaşı ilkesini **sudo vim /etc/login.defs** aracılığıyla yapılandıralım**. login.defs** dosyasını açalım.

```
sudo vim /etc/login.defs
```

---

---

### kullanici ogenc kullanicisinin sudo ogenc42 gruplarına ait oldugunun kontrol

groups ogenc

### yeni bir kullanici olusturun şifre kurallarının yerini göster

sudo adduser evo42    —> yeni bir kullanici oluşturur

sudo cat /etc/passwd  —> kullanicilari burada görebilriiz

 sudo cat /etc/pam.d/common-password şifre kurallarini gördügümüz yer

sudo cat /etc/login.defs —> şifre değiştirme tarihlerini ayarladıgımız kısım

### yeni kullaniciya yeni grup kurup gruba eklemek

sudo addgroup degerlendirme —> grup eklenir

sudo addgroup evodeneme42 degerlendirme —> evodeneme42 kullanicisina degerlendirme grubunu ekler.

sudo cat /etc/group —> grupları görürüz

### FTP (File Transfer Protocol)

dosya aktarım protokolüdür. İnternet üzerinde dosyaların güvenli ve hızlı bir şekilde transfer edilmesini sağlar. FTP, dosyaların bilgisayardan bilgisayara, sunucudan sunucuya veya sunucudan istemciye veya istemciden sunucuya aktarılmasını mümkün kılar. FTP, dosyaların yüklenmesi, indirilmesi, adının değiştirilmesi veya silinmesi gibi işlemlerin yapılmasına olanak tanır.

FTP sunucusu, dosyaların FTP protokolü kullanılarak aktarımının yapılabileceği bir sistemdir. FTP sunucusu, dosyaların depolanması, yönetilmesi ve erişimi için gerekli olan donanım ve yazılımı içerir. FTP sunucusu, kullanıcıların dosyalarını güvenli bir şekilde yüklemesi, indirmesi, adının değiştirilmesi veya silinmesi gibi işlemler yapmasına olanak tanır. FTP sunucuları, ev kullanıcılarından büyük işletmelere kadar birçok farklı tip kullanıcıya hizmet verir. FTP sunucuları, internet üzerinden dosyaların aktarımı için en yaygın kullanılan araçlardan biridir.

### Debian Lighttpd (Web sunucusu)

lighttpd, doğrudan Debian üzerindeki resmi paket kaynaklarından kurulabilir, bu nedenle Apache gibi
herhangi bir üçüncü taraf deposuna ihtiyacımız yok.

### MariaDB nedir ?

MariaDB, MySQL veritabanı yönetim sistemi benzeri bir açık kaynak veritabanı yönetim sistemidir. MariaDB, MySQL veritabanı yönetim sistemi kodunun bir fork'udur ve MySQL veritabanı yönetim sistemine benzer bir API ve veritabanı sorgulama dilini (SQL) kullanır. MariaDB, MySQL veritabanı yönetim sistemi gibi popüler web uygulamaları, bloglar, forumlar ve e-ticaret siteleri gibi uygulamalar için kullanılabilir.

MariaDB, MySQL veritabanı yönetim sisteminde yapılan değişikliklere ve güncelleştirmelerine ek olarak, birçok özellik ve iyileştirme de içermektedir. Bu özellikler arasında en hızlı veritabanı motorlarından biri olan XtraDB motoru, gelişmiş veritabanı optimizasyonu ve daha iyi güvenlik özellikleri bulunur.

MariaDB, kurulum ve kullanımı kolay bir veritabanı yönetim sistemi olarak bilinir ve birçok dağıtımda varsayılan olarak kurulur. Ayrıca, MariaDB, MySQL veritabanı yönetim sistemi gibi geniş bir kullanıcı topluluğu ve aktif bir geliştirme ekibi tarafından desteklenir.

---
