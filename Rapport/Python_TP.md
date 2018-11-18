## Python TP

PENG Hanyuan & YAN Wenli

---

> Les codes du TP sont fournis dans le fichier `Code_TP.zip`.


### TP1 - Fichiers

Ce sujet nous permet d'utiliser:
- Les fichiers: Lecture et l'écriture d'un fichier,
- Classe: Surcharge des méthodes, getter, setter.


#### Fichier

Quand nous voulons lire un fichier text (ou json, xml etc..), c'est mieux d'indiquer le codage de fichier pour que les textes affiche correctement.

``` python
def func():
    print(' Bonjour le monde !')
    print('\t1. Choisir un nom de fichier','\t2. Ajouter un texte','\t3. Afficher le fichier complet', '\t4. Vider le fichier', '\t5. Quitter',sep='\n')

    filename = ''
    while True:
        inp = input('Votre choix: ')
        if inp == '1':
            filename = input('Nom de fichier: ')
            print('Nom du fichier:', filename)
        elif inp == '2':
            if not filename:
                print('Choisir un nom de fichier!')
            else:
                print('Nom du fichier: ', filename)
                with open(filename, "a", encoding="utf-8") as fic:
                    text = input("Votre Texte: ")
                    fic.write(text)
        elif inp == '3':
            if not filename:
                print('Choisir un nom de fichier!')
            else:
                print('Nom du fichier: ', filename)
                with open(filename, "r", encoding="utf-8") as fic:
                    print(fic.read(),end='\n')
        elif inp == '4':
            with open(filename, "w+") as fic:
                fic.truncate()
        elif inp == '5':
            break
        else:
            raise Exception("Error input, programme va quitter")


if __name__ == "__main__":
    try:
        func()
    except Exception as e:
        print(e)
```

###### Résultat:

![](tp1.png)

#### Classe

##### Surcharge des méthodes

``` python
class Date:
    def __init__(self,date):
        self.date = date
    def __eq__(self, other):
        if other.date == self.date:
            return True
        else:
            return False
    def __lt__(self,other):
        if self.date < other.date:
            return True
        else:
            return False

date = Date(1.2)
date2 = Date(1.3)

print(date > date2)

```

###### Résultat:

![](tp1_date.png)


###### Des point importants

Il faut utiliser le nom particulier pour surcharger les opérateur (+, =, <, etc)


##### Attributs et Getter, Setter

> Des codes de cette partie sont dans le `Code_TP.zip`. Fichier `tp1_etudiant.py`

Résultat:

![](tp1_etu.png)

###### Des point importants

(莉莉这里你看一下有没有需要注意的点。。。)


### TP2 - Tkinter

### TP3 - Exceptions et chiffrement

### TP4 - Matplotlib

### TP5 - Base de données

### TP6 - Numpy et Scipy

### TP7 - Serveur et page web (Django)

### TP8 - Prog. asynchrone et fourmis
