# Unit testing for phone register API

An application to test a phone number register at its lowest level with unit testing.


## Concepts practised:
- unit testing
- classes

## Built with:
- JXS
- Jest

## Usage:

1. In your project folder, create a `package.json` file (set up a npm package)
```sh
npm init -y
```
2. Install jest
```sh
npm install jest --save-dev
```
3. Add jest in the test script in `package.json``
```json
  "scripts": {
    "test": "jest"
  }
```
4. In the project folder, create a folder `__tests__`for the tests
5. Write an API description
6. Create your tests and run them BEFORE implementing the methods (or comment out methods)
```sh
npm test
```

Make sure tests fail. If they don't, there's something wrong and they're useless.

7. Implement the methods and then test them
```sh
npm test
```

## Screenshot:

Version 1:
![screenshot](screenshot.png?raw=true "Screenshot of the first version of Pokédex app")


## Acknowledgement:  
- Teacher HI at Business College Helsinki
