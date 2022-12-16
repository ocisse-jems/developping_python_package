# 1_Du_code_au_package

> Pourquoi un package ?

- Pour rendre le code plus facile à réutiliser
- Pour éviter de faire beaucoup de copier-coller
- Pour garder les fonctions à jour
- Pour partager son code aux autres

<br>

## Scripts, modules, and packages

- **Scripts**  
    Un fichier Python (.py) qui se lance avec la commande : `python3 my_script.py`  

- **Package**  
    Un répertoire (dossier) contenant du code Python povant être importé  
    ex:  numpy  

- **Subpackage**  
    Un 'petit' pachake dans un package  
    ex: numpy.random  

- **Module**  
    Un fichier Python à l'intérieur d'un package qui contient le code du package  

- **Library (bibliothèque)**    
    Soit un packahe ou une collection de packages  
    ex: la biliotheque standard Python (math, os, datetime ...)  

<br>

## Structure d'un Package simple  
(_voir le dossier mysimplepackage_)

mysimplepackage/     
|-- simplemodule.py  
|-- __ init __.py  

> mysimplepackage/  
    nom du répertoire (package python)  

> simplemodule.py  
    contient tout le code du package  

> __ init __.py (fichier vide)    
    permet de définir (indiquer) que le répertoire est un packahe Python  

<br>

## Subpackages  

Ex. de structure d'un package avec des subpackages (sklearn)  

mysklearn/  
|-- __ init __.py  
|-- preprocessing  
____|-- __ init __.py  
____|-- normalize.py  
____|-- standardize.py  
|-- regression  
____|-- __ init __.py  
____|-- regression.py  
|-- utils.py  


<br>

## Documentation 

> Pourquoi ?
- permet à d'autres développeurs d'utiliser le code
- documenter chaque :
    - fonction
    - classe
    - methode de classe

ex:

```py
import numpy as np
help(np.sum)
```

sum(a, axis=None, dtype=None, out=None)  
Sum of array elements over a given axis.  

Parameters  

--  
    a : array_like  
        Elements to sum.  
    axis : None or int or tuple of ints, optional  
        Axis or axes along which a sum is performed.  
        The default, axis=None, will sum all of the elements of the input array.  
    ...  

> documenter une fonction

```py
def count_words(filepath, words_list):  
    """Count the total number of times these words appear.
    The count is performed on a text file at the given location.
    [explain what filepath and words_list are]
    [what is returned]
    """
```

> style de documentation  

- Google documentation style

```
Extended description of function. Extended description of function.  

Args: Parameters
    arg1 (int): Description of arg1  
    arg2 (str): Description of arg2
```

- NumPy style

```
Extended description of function.

Parameters
----------
arg1 : int
Description of arg1 ...
```

- reStructured text style

```
Extended description of function.

:param arg1: Description of arg1
:type arg1: int
:param arg2: Description of arg2
:type arg2: str
```

- Epytext style

```
Extended description of function.

@type arg1: int
@param arg1: Description of arg1
@type arg2: str
@param arg2: Description of arg2
```

> Templates de documentation et changement (switch) de style

- `pyment` peut ête utilisé pour générer des docstrings
- depuis le Terminal
- qq soit le style souhaité
- et permet de switcher d'un style à un autre

ex: 

```
pyment -w -o numpydoc textanalysis.py
```

* -w: overwrite file
* -o: output in NumPy style

```
ppyment -w -o google textanalysis.py
```

> Package, subpackage et module (documentation)

```
mysklearn/__init__.py
```

"""   
Linear regression for Python  
 
mysklearn is a complete package for implmenting
linear regression in python.  
"""


```
mysklearn/preprocessing/__init__.py
```

"""  
A subpackage for standard preprocessing operations.  
"""  

```
mysklearn/preprocessing/normalize.py
```

"""  
A module for normalizing data.  
"""