
# 🔐 John the Ripper – Guide Pratique (eJPT Ready)  

---  

> Un guide simple et rapide pour apprendre à utiliser **John the Ripper**, l’outil de craquage de mots de passe, essentiel pour les CTF et la certification **eJPT**.

---

## 📦 Installation

### ✅ Sur Kali Linux :  
```bash
sudo apt update
sudo apt install john
```

### 📁 Créer un fichier de hash à craquer  
Exemple avec un hash MD5 :
```bash
echo -n "password" | md5sum > hash.txt  
```
💡 Explication :  
* ``echo -n "password"`` :  
✅ Le -n empêche le saut de ligne à la fin (par défaut, echo ajoute un \n).  
👉 Sans -n, on aurait le hash de ``"password\n"`` (ce qui donnerait un résultat complètement différent).  

* ``| md5sum :``  
✅ Passe la sortie de echo dans le programme md5sum, qui calcule le hash MD5.  

* ``> hash.txt`` :  
✅ Redirige le résultat (le hash suivi de -) dans un fichier nommé ``hash.txt``.  

Contenu de hash.txt :  
``5f4dcc3b5aa765d61d8327deb882cf99``  

## 🧠 Craquer un hash avec une wordlist  
```
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```
💡 Explication :  
| Élément                                       | Description                                                                               |
| --------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `john`                                        | Lance l’outil **John the Ripper**                                                         |
| `--format=raw-md5`                            | Spécifie le **type de hash** à cracker. Ici : `raw-md5` = hash MD5 simple (32 caractères) |
| `--wordlist=/usr/share/wordlists/rockyou.txt` | Indique le **chemin de la wordlist** à utiliser (ici, la célèbre `rockyou.txt`)           |
| `hash.txt`                                    | Fichier contenant le ou les **hashs à cracker**                                           |



### 📌 Afficher le mot de passe trouvé :  
```
john --show hash.txt  
```


## 🧰 Outils d’extraction de hash  
### 🔐 ZIP :  
```
zip2john secret.zip > zip.hash
john zip.hash
```
### 📄 PDF :  
```
pdf2john.pl fichier.pdf > pdf.hash
john pdf.hash
```

### 🧑‍💻 /etc/passwd + /etc/shadow :  
```
unshadow /etc/passwd /etc/shadow > fullshadow.txt
john fullshadow.txt
```


## 🔍 Identifier le type de hash  
Avec John :
```
john --list=formats
```

Avec hashid (outil tiers) :
```
hashid hash.txt
```

## 📚 Wordlists recommandées
rockyou.txt (disponible par défaut sous Kali) :
```
/usr/share/wordlists/rockyou.txt
```





