# Phone API

## Data
Data will be in a json file

### phones.json
```json
[
    {
        "firstname": "Leila",
        "lastname": "Hökki",
        "phones": [
            {"type": "home", "number": "12345678"},
            {"type": "work", "number": "876654321"},
            {"type": "work", "number": "050543212"}
        ]
    },
    {
        "firstname": "Matti",
        "lastname": "River",
        "phones": [
            {"type": "home", "number": "999999999"},
            {"type": "work", "number": "878787877"},
            {"type": "work", "number": "045067607"}
        ]
    }
]
```

## Class PhoneRegister

A person is uniquely identified by first name and last name. There cannot be two persons with the same name.

### **constructor(data)**

Phones json arrays is passed as a paramenter `data`. If the parameter is missing, throws an exception `'phone data missing'`.

### **getTypes()** 
 return all phone types in an array. The type is added to the result array only once. If there are no phone or no persons, an empty arrays is returned.

For example:
```json
["home", "work", "mobile"]
```

### **getPersonsNumbersByType(firstname, lastname, type)**

Return an array of phone numbers of the given `type` belonging to the given person with `firstname` and `lastname`.

- if no person with given name >>> empty array is returned
- if no number with given type >>> empty array is returned
- if at least one parameter is missing >>> an exception `'missing parameter'`is thrown

For example Leila Hökki and work:
```js
["876654321", "050543212" ]
```

### **getAllNumbersByType(type)**

Returns an array of objects consisting of names and numbers of given type. If no number of given type is found, return an empty array.

- if a person have multiple numbers of the same type >>> each of them will be in its own onject
- if the paramenter type is missing >>> an exception `'missing parameter'`is thrown


The format of the rturned array of object is:
```json
[
    {"firstname": "Leila", "lastname": "Hökki", "number": {"type":"", "tel":""}},
    {"firstname": "Leila", "lastname": "Hökki", "number": {"type":"", "tel":""}}
]
```

#### Example type work:
```json
[
    {"firstname": "Leila", "lastname": "Hökki", "number": {"type":"work", "tel":"876654321"}},
    {"firstname": "Leila", "lastname": "Hökki", "number": {"type":"work", "tel":"050543212"}},
    {"firstname": "Matti", "lastname": "River", "number": {"type":"work", "tel":"045067607"}}
]
```

### **getAllNumbers()**

Return all phone numbers in an array, each as an object of form:

```json
{"firstname": "", "lastname": "", "phone": []}
```

The phone object in phones array is of form:
```json
{"type": , "number": ""}
```

- if a person does not have a phone (phone field empty or no phone field) >>> the person is not added into the result array
- if all phones are missing >>> an empty array is returned
- if all persons are missing (empty json) >>> an empty arrays is returned

### **getName(number)**

The method searches the given phone number from the telephone registry.

- if the number is found >>> return a json object of form:

```json
{"fistname": "", "lastname": ""}
```

- if no phone with given number is found >>> return `null`
- if the parameter is missing >>> return `null`

#### Example who has number "12345678"

```json
{"firstname": "Leila", "lastname": "Hökki"}
```



