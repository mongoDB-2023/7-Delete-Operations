# 7-Delete-Operations


1. [Understanding deleteOne() & deleteMany()](#schema1)
2. [Deleting All Entries in a Collection](#schema2)


<hr>

<a name="schema1"></a>

## 1. Understanding deleteOne() & deleteMany()

### deleteOne()
```
users> db.persons.deleteOne({name:'Chris'})
{ acknowledged: true, deletedCount: 1 }
users> db.persons.find()
[
  {
    _id: ObjectId('6567259ef5d66fd59e935426'),
    name: 'Max',
    hobbies: [
      {
        title: 'Sports',
        frequency: 5,
        highFrequency: true,
        goodFrequency: true
      },
      { title: 'Cooking', frequency: 3, goodFrequency: true },
      { title: 'Hiking', frequency: 1 }
    ],
    isSporty: true
  },
  {
    _id: ObjectId('6567259ef5d66fd59e935427'),
    name: 'Manuel',
    hobbies: [
      { title: 'Cooking', frequency: 4, goodFrequency: true },
      { title: 'Cars', frequency: 1 }
    ],
    phone: '012177972',
    isSporty: false,
    TotalAge: 33
  },
  {
    _id: ObjectId('6567259ef5d66fd59e935428'),
    name: 'Anna',
    hobbies: [
      { title: 'Sports', frequency: 2 },
      { title: 'Yoga', frequency: 3, goodFrequency: true }
    ],
    isSporty: true,
    TotalAge: null
  },
  {
    _id: ObjectId('656755d39afc3679dfa0514b'),
    name: 'Maria',
    age: 29,
    hobbies: [
      { title: 'Good food', frequency: 3, goodFrequency: true },
      { title: 'Sports', frequency: 2 },
      { title: 'Hiking', frequency: 2 },
      { title: 'Good Wine', frequency: 1 }
    ],
    isSporty: true
  }
]
users> 

```


### deleteMany()

```
users> db.persons.deleteMany({age:{$gt:25},isSporty:true})
{ acknowledged: true, deletedCount: 3 }

```

<hr>

<a name="schema2"></a>

## 2. Deleting All Entries in a Collection

Elimina todos los elementos de una colección
```
db.persons.deleteMany({})
```
Otra opción

```
db.persons.drop()
```