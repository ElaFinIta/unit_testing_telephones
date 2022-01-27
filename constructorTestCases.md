# Test cases

## **constructor(data)**

Phone json array is passed as a parameter `data`.


### Test 1: object created with given data
```js
new PhoneRegister(jsonData);
```

test if the inner field of the created object has the same value as given as parameter. Parameter `jsondata` is the json array from the default file `phones.json`

### Test 2: missing parameter

```js
new PhoneRegister()
```
- if missing parameter >>> throw exception `'phone data missing'`