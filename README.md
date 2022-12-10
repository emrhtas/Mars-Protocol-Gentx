# Mars-Protocol-Gentx

## https://discord.gg/marsprotocol

## Sunucu güncellemesi 
```
sudo apt update && sudo apt upgrade -y
```
## Kütüphane kurulumu
```
sudo apt-get install make build-essential gcc git jq chrony -y
```
## Go kurulumu
```
cd $HOME
wget -O go1.18.2.linux-amd64.tar.gz https://go.dev/dl/go1.18.2.linux-amd64.tar.gz
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.2.linux-amd64.tar.gz && rm go1.18.2.linux-amd64.tar.gz
echo 'export GOROOT=/usr/local/go' >> $HOME/.bashrc
echo 'export GOPATH=$HOME/go' >> $HOME/.bashrc
echo 'export GO111MODULE=on' >> $HOME/.bashrc
echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bashrc && . $HOME/.bashrc
go version
```
## Binary Kurulumu
```
cd $HOME
git clone https://github.com/mars-protocol/hub.git
cd hub
git checkout v1.0.0
make install
```
## Yapılandırma
```
marsd config chain-id mars-1
marsd config keyring-backend test
```
## Initialize ( Validator adı yazan yere validator adınızı yazmayı unutmayın)
```
marsd init VALİDATORADI --chain-id mars-1
```
## Cüzdan Oluşturma ( Cüzdan adı yazan yere cüzdan adınızı yazın)
```
marsd keys add CÜZDANADI
```
## Genesis Hesabı ekle
```
marsd genesis add-account CÜZDANADRESİ 1000000umars
```
## Gentx işlemi ( CUZDANADI ve VALIDATORADI kısımlarını kendinize göre düzenlemeyi unutmayın. Website kısmında sizde bu şekilde istediğiniz bir sitenin veya kendi web sitenizin linkini yazabilirsiniz. Details kısmında da istediğiniz açıklamayı ekleyebilirsiniz)
```
marsd genesis gentx CUZDANADI 1000000umars \
--chain-id mars-1 \
--moniker=VALİDATORADI \
--commission-max-change-rate=0.01 \
--commission-max-rate=1.0 \
--commission-rate=0.05 \
--website="https://github.com/emrhtas" \
--details="bircisimyaklaşıyorefendim" \
--min-self-delegation=1
```
### Bundan sonraki işlemlere github ve winscp ile devam edeceğiz. 
## Winscp ye bağlanıyoruz config klasörü içinde yer alan gentx dosyamızı cihazımızda istediğimiz yere indiriyoruz. Winscp ile işimiz bitti kapatabilirsiniz. 
* https://github.com/mars-protocol/networks  linke tıklıyoruz ve forkluyoruz. 
* Profilimize geliyoruz ve forkladığımız networks reposuna tıklıyoruz. 
*  ![gentx](https://user-images.githubusercontent.com/101218992/206649133-0871ead4-f425-4218-b81f-a1523d468eb1.png)
  Karşınıza görseldeki sayfa çıktı. mars-1 'e tıklıyoruz, ardından gentx e tıklıyoruz. 
*  ![gentx1](https://user-images.githubusercontent.com/101218992/206649734-ae3bd781-5349-40d4-acdf-5b68b445cfaf.png)
Sağ tarafta Add file tıklıyoruz ve create new file diyoruz. 
** ![gentx2](https://user-images.githubusercontent.com/101218992/206650493-851efdbf-9d2e-451f-b27c-2648c0c9674b.png)
  Name your file kısmında şu şekilde dosyamızın adını yazıyoruz.      gentx-VALIDATORADI.json 
  Edit new file kısmına da indirdiğimiz gentx dosyamızın içeriğini ekliyoruz  ve sayfanın alt kısmından commit new file diyerek kaydediyoruz. 
 * Sol üst tarafta Pull Request yazan yere tıklıyoruz, New pull request e tıklıyoruz ve create pull request diyerek açılan sayfada gentx dosyamızın içeriğini ekliyoruz. Onaylıyoruz ve işlemimiz bitiyor. 
  
  https://github.com/mars-protocol/networks/pulls   Buradan kontrol edebilirsiniz. 
