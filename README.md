# Estructures de Dades en Python 

[![Versió](https://img.shields.io/badge/versió-1.0.0-blue.svg)](https://github.com/dmorenoar/python-codex-smx)
[![Estat](https://img.shields.io/badge/estat-ONLINE-brightgreen.svg)](https://dmorenoar.github.io/python-codex-smx/)

Arxiu de referència i exemples pràctics sobre les principals estructures de dades en Python.

**Plataforma interactiva d'aprenentatge de teòria d'estructures de dades en Python** 

🌐 **[Fer el test](https://dmorenoar.github.io/est-dades/)**


---

## Contingut teòric

### 1. Llistes (`list`)

Una llista és una estructura de dades **ordenada, indexada i mutable** que permet guardar múltiples valors dins d'una sola variable i pot contenir elements de tipus diferents.

**Operacions cobertes:**
- Creació de llistes (tipus únics i mixtos)
- Accés per índex positiu i negatiu
- Modificació d'elements
- Afegir elements: `append()`, `insert()`
- Eliminar elements: `remove()`, `pop()`
- Comprovació d'existència abans d'eliminar (`in`)
- Longitud: `len()`
- Recorregut per valor i per índex

---

### 2. Tuples (`tuple`)

Una tupla és una estructura similar a la llista però **immutable**: un cop creada, no es pot modificar.

**Operacions cobertes:**
- Creació de tuples (inclòs el cas especial d'un sol element: `(5,)`)
- Accés per índex
- Recorregut per valor i per índex
- Error típic: `(5)` no és una tupla, és un `int`

---

### 3. Diccionaris (`dict`)

Un diccionari guarda informació en format **clau-valor**. És mutable però no té posicions numèriques; l'accés és sempre per clau.

**Operacions cobertes:**
- Creació de diccionaris
- Accés per clau
- Afegir i modificar valors
- Eliminar elements: `del`, `pop()`
- Accés segur: `get()` amb valor per defecte
- Comprovació d'existència (`in`)
- Recorregut per claus, per valors i per parells clau-valor

---

### 4. Conjunts (`set`)

Un conjunt és una estructura que **no permet duplicats** i **no té ordre**. És ideal per a operacions matemàtiques de conjunts.

**Operacions cobertes:**
- Creació de conjunts amb valors i conjunts buits (`set()`)
- Comportament davant duplicats
- Afegir elements: `add()`
- Eliminar elements de manera segura: `discard()`
- Eliminació amb error si no existeix: `remove()`
- Recorregut (l'ordre pot variar a cada execució)
- Operacions matemàtiques:
  - Unió: `|`
  - Intersecció: `&`
  - Diferència: `-`
  - Diferència simètrica: `^`

---

# Material de suport per a codificar

Aquest document explica les principals estructures de dades en Python amb exemples pràctics. Llegeix-lo abans de fer les activitats!

---

## 1. Llistes (`list`)

Una llista és com una **caixa amb compartiments numerats** on pots guardar diversos valors. Els compartiments es numeren des del 0.

> 💡 **Característica clau:** Ordenada, indexada i **mutable** (es pot modificar).

### Crear una llista

```python
numbers = [10, 20, 30]
names   = ['Dani', 'Pikachu', 'Alba']
mix     = [1, 'Tanjiro', True, 10.5]   # pot barrejar tipus!
```

### Accedir als elements

L'índex comença a **0**. L'índex **-1** és sempre l'últim element.

```python
names = ['Dani', 'Pikachu', 'Alba']

print(names[0])   # → Dani     (primer)
print(names[-1])  # → Alba     (últim)
print(names)      # → ['Dani', 'Pikachu', 'Alba']
```

### Modificar elements

```python
names[0] = "Charmander"
print(names)    # → ['Charmander', 'Pikachu', 'Alba']
```

### Afegir elements

```python
names.append('Macarena')      # afegeix al FINAL
names.insert(1, 'Julio')      # afegeix a la posició 1 (desplaça els altres)

# Resultat: ['Charmander', 'Julio', 'Pikachu', 'Alba', 'Macarena']
```

### Eliminar elements

> ⚠️ **Important:** Si l'element no existeix, el programa **peta**. Comprova sempre abans d'eliminar!

```python
# Eliminar per VALOR
names.remove('Charmander')

# ✅ Manera segura (comprova primer)
if "Charmander" in names:
    names.remove("Charmander")
else:
    print("Charmander no existeix a la llista")

# Eliminar per POSICIÓ
names.pop(0)    # elimina el primer element
```

### Longitud i recorregut

```python
print(len(names))   # → nombre d'elements

# Forma bàsica (per valor)
for nom_usuari in names:
    print(nom_usuari)

# Forma amb índex (quan necessites saber la posició)
for i in range(len(names)):
    print(i, names[i])
    # → 0 Julio
    # → 1 Pikachu
    # → 2 Alba
    # → 3 Macarena
```

---

## 2. Tuples (`tuple`)

Una tupla és com una llista, però **bloquejada**: un cop creada, **no es pot modificar**. Útil quan vols assegurar-te que les dades no canvien.

> 💡 **Característica clau:** Ordenada, indexada i **immutable** (NO es pot modificar).

### Crear una tupla

```python
numbers     = (10, 20, 30)
names_users = ("Ana", "Felipe", "Marta")
mix_var     = (1, "Ana", True, 3.1)

# ⚠️ ERROR TÍPIC amb un sol element:
t = (5,)    # ✅ AIXÒ SÍ és una tupla (vés la coma!)
t = (5)     # ❌ AIXÒ és un int, NO una tupla
```

### Accedir als elements

Funciona exactament igual que amb les llistes:

```python
print(names_users[0])    # → Ana
print(names_users[-1])   # → Marta
```

### No es poden modificar

```python
numbers[0] = 4
# ❌ TypeError: 'tuple' object does not support item assignment
```

### Recorregut

```python
# Per valor
for name in names_users:
    print(name)
    # → Ana
    # → Felipe
    # → Marta

# Per índex
for i in range(len(names_users)):
    print(i, names_users[i])
    # → 0 Ana
    # → 1 Felipe
    # → 2 Marta
```

---

## 3. Diccionaris (`dict`)

Un diccionari és com una **fitxa de dades**: en comptes d'accedir per número de posició, accedes per **nom de camp** (clau). Perfecte per representar objectes amb propietats.

> 💡 **Característica clau:** Mutable, accés per clau (no per índex numèric).

### Crear un diccionari

```python
alumne = {
    "nom"    : "Gabimaru",
    "edat"   : 18,
    "estil"  : "ninja",
    "isMale" : True
}
```

Cada línia és un parell `clau : valor`. La clau és sempre un text (string).

### Accedir als valors

```python
print(alumne["nom"])    # → Gabimaru
print(alumne["edat"])   # → 18

# ❌ Si la clau no existeix, dona error:
# print(alumne["attack"])  → KeyError!
```

### Afegir i modificar valors

```python
alumne["edat"]     = 20          # modifica un valor existent
alumne["nickname"] = 'El vacío'  # afegeix una clau nova

print(alumne["nickname"])   # → El vacío
```

### Eliminar elements

```python
del alumne["isMale"]    # opció 1
alumne.pop("edat")      # opció 2

# ✅ Manera segura (comprova primer)
if "edat" in alumne:
    print(alumne["edat"])
else:
    print("L'alumne no té l'atribut edat")

# ✅ Accés segur amb .get() → retorna None si no existeix (no peta!)
print(alumne.get("edat"))               # → None
print(alumne.get("edat", "No definit")) # → No definit
print(alumne.get("edat", 0))            # → 0
```

### Recorregut

```python
# Per clau
for clau in alumne:
    print(clau)
    # → nom
    # → estil
    # → nickname

# Per valor
for valor in alumne.values():
    print(valor)
    # → Gabimaru
    # → ninja
    # → El vacío

# Per clau i valor alhora (el més útil!)
for clau, valor in alumne.items():
    print(f"{clau} : {valor}")
    # → nom : Gabimaru
    # → estil : ninja
    # → nickname : El vacío
```

---

## 4. Conjunts (`set`)

Un conjunt és com una **bossa** on pots ficar elements, però amb dues regles: **no admet duplicats** i **no té ordre**. Molt útil per comparar grups de dades.

> 💡 **Característica clau:** Mutable, sense ordre, sense duplicats.

### Crear un conjunt

```python
enemics = {"orc", "drac", "zombi"}   # amb valors inicials
players = set()                        # conjunt buit ✅
users   = ()                           # ⚠️ AIXÒ és una tupla buida, NO un set!
```

### Els duplicats s'ignoren automàticament

```python
numbers = {1, 2, 3, 3, 3, 4}
print(numbers)   # → {1, 2, 3, 4}  (els repetits desapareixen)
```

### Afegir i eliminar elements

```python
enemics.add("esquelet")   # afegeix un element
enemics.add("orc")        # ja existeix → no fa res
enemics.add("ORC")        # ⚠️ "ORC" i "orc" SÓN DIFERENTS (case sensitive)

enemics.remove("orc")     # ❌ peta si no existeix

# ✅ Manera segura
enemics.discard("pepe")   # NO peta si no existeix
enemics.discard("drac")   # elimina si existeix, sinó res
```

### No es pot accedir per índex

```python
# ❌ Els conjunts no tenen posicions!
enemics[0]   # → TypeError
```

### Recorregut

```python
for enemic in enemics:
    print(enemic)
# ⚠️ L'ordre pot ser diferent a cada execució!
```

### Operacions matemàtiques de conjunts

Aquí és on els sets brillen de veritat:

```python
habilitats_jugador = {"espasa", "magia", "furtivitat"}
habilitats_enemic  = {"magia", "volar"}

# Unió → tots els elements de tots dos
print(habilitats_jugador | habilitats_enemic)
# → {'espasa', 'magia', 'furtivitat', 'volar'}

# Intersecció → elements que tenen en comú
print(habilitats_jugador & habilitats_enemic)
# → {'magia'}

# Diferència → elements del jugador que l'enemic NO té
print(habilitats_jugador - habilitats_enemic)
# → {'espasa', 'furtivitat'}

# Diferència simètrica → elements que NO són comuns
print(habilitats_jugador ^ habilitats_enemic)
# → {'espasa', 'furtivitat', 'volar'}
```

---

## Resum comparatiu

| Estructura | Exemple           | Ordenada | Indexada     | Mutable | Duplicats |
|------------|-------------------|----------|--------------|---------|-----------|
| `list`     | `[1, 2, 3]`       | ✅       | ✅ (0, 1, 2…) | ✅     | ✅        |
| `tuple`    | `(1, 2, 3)`       | ✅       | ✅ (0, 1, 2…) | ❌     | ✅        |
| `dict`     | `{"nom": "Ana"}`  | ✅*      | ✅ (per clau) | ✅     | ❌ (claus)|
| `set`      | `{1, 2, 3}`       | ❌       | ❌            | ✅     | ❌        |

> *Els diccionaris mantenen l'ordre d'inserció des de Python 3.7+

---

## Errors més habituals

| Error | Causa | Solució |
|-------|-------|---------|
| `IndexError` | Accedir a una posició que no existeix | Comprova `len()` abans |
| `KeyError` | Accedir a una clau que no existeix al dict | Usa `.get()` o comprova amb `in` |
| `ValueError` | Fer `remove()` d'un element que no hi és | Comprova amb `in` abans |
| `TypeError` | Intentar modificar una tupla | Les tuples no es poden canviar |

---
