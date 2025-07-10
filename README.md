
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
👉 Sans -n, on aurait le hash de "password\n" (ce qui donnerait un résultat complètement différent).
