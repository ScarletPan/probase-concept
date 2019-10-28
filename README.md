# Probase-Concept


## Install
```bash
python setup.py install
```



## Download the Probase Data

Please visit Probase [website](https://concept.research.microsoft.com/Home/Download) to download



## Basic Usage

### 1.  Load the data

```python
from pbconcept import ProbaseConcept

pb_concept = ProbaseConcept("data/data-concept-instance-relations.txt")
```

### 2. Conceptualization

```python
pb_concept.conceptualize("dog", score_method="likelihood")
```

which will produce

```
[('animal', 0.23049271472392638),
 ('pet', 0.10381518404907976),
 ('domestic animal', 0.049798696319018405),
 ('mammal', 0.043855444785276074),
 ('specie', 0.034700920245398774),
 ('domesticated animal', 0.026313266871165645),
 ('companion animal', 0.02142446319018405),
 ('household pet', 0.014666411042944786),
 ('predator', 0.013468174846625767),
 ('domestic pet', 0.012893021472392638),
 ...,
]
```

### 3. Instantiation

```python
pb_concept.instantiate("dog")
```

Which will produce

```
[('german shepherd', 126),
 ('poodle', 106),
 ('rottweilers', 79),
 ('poodles', 78),
 ('rottweiler', 72),
 ('german shepherds', 72),
 ('chihuahua', 65),
 ('golden retriever', 63),
 ('labradors', 60),
 ('boxer', 60),
 ...,
]
```

### 4. Concept chain

```python
pb_concept.get_concept_chain("dog")
```

which will produce 

```
['dog', 'animal', 'organism', 'complex system', 'social complexity concept']
```

PS: Top 1 likelihood concept will be chosen when finding a chain