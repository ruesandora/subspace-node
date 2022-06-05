# subspace-node-TR
Subspace Network scriptli node kurulum Türkçe rehberi. ''Güncel script''
![image](https://user-images.githubusercontent.com/101149671/171963119-c5ad523b-b97e-4d1e-ab00-97590e4d7aa1.png)

# Öncelikle bir Subspace cüzdanına ihtiyacınız var, cüzdanız varsa bu adımı geçin.

Cüzdan kurulumu için [buraya](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Feu.gemini-1b.subspace.network%2Fws#/accounts) giriyoruz.

# Add account diyoruz görselde ki gibi:

![image](https://user-images.githubusercontent.com/101149671/171963996-876e12a7-a78c-45b0-bdab-4fb056cdceaf.png)

# Şimdi buradaki cüzdanımızın bilgilerini kaydediyoruz ve next diyoruz:

![image](https://user-images.githubusercontent.com/101149671/171964249-2382a72d-b7a1-4bb8-b3cf-74e9637ecb4b.png)

Daha sonra şifre belirleyip next + save diyoruz.

# Alttan hesabımızı seçip adresimizi kopyalıyoruz ve not ediyoruz:

![image](https://user-images.githubusercontent.com/101149671/171964513-2d99cadc-b900-4a5e-b9e2-634b04b37685.png)

# Kurulum: 

< node-ismi > yazan kısımlara kendi node isminizi girip yazıyoruz.

```
apt install screen
screen -S subNode
echo 'export SUBSPACE_NODENAME='<node-ismi> >> $HOME/.bash_profile
echo 'export SUBSPACE_WALLET='<cüzdan-adresi> >> $HOME/.bash_profile
wget -O subspace-last.sh http://api.rues.info/subspace-last.sh && chmod +x subspace-last.sh && ./subspace-last.sh
journalctl -u subspaced -f -o cat
CTRL + A + D
```

# Yararlı komutlar:

Node logları: 
```
journalctl -u subspaced -f -o cat
```
Farmer ekranı:
```
screen -S subFarmer
journalctl -u subspaced-farmer -f -o cat
```
Node resetleme:
```
sudo systemctl restart subspaced
```
Reset farmer:
```
sudo systemctl restart subspaced-farmer
```

Node kaldırma:
```
sudo systemctl stop subspaced subspaced-farmer
sudo systemctl disable subspaced subspaced-farmer
rm -rf ~/.local/share/subspace*
rm -rf /etc/systemd/system/subspaced*
rm -rf /usr/local/bin/subspace*
```

Teşekkürler <3


# Hesaplar:

[Twitter](https://twitter.com/Ruesandora0)

[Forum](https://forum.rues.info/index.php)

[Telegram Announcement](https://t.me/RuesAnnouncement)

[Telegram Chat](https://t.me/RuesChat)

[Telegram Node](https://t.me/RuesNode)

[Telegram Node Chat](https://t.me/RuesNodeChat)
