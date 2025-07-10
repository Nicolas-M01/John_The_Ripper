
# 🔐 John the Ripper – Guide Pratique (eJPT Ready)

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
