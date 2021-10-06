Unit Testing Info For Team


# Unit Testing

> 🍓 _"The only way we can make sure our apps work correctly is by testing them - so it is vital that we learn to test apps thoroughly."_ -- Edd Yerburgh

.

Primary Source Referenced, Paraphrased, and Quoted: ["Testing Vue.js Applications"](https://www.manning.com/books/testing-vue-js-applications) by Edd Yerburgh,  Vue.js core team member and author of the official Vue testing utility

---


## **Unit Tests**

- **Definition**
	- The process of running tests against the smallest parts of an application (units) in isolation and asserting that they behave correctly. 
    Normally the units you test are functions, but in Vue apps, components are also units to test.

.
> 🍓 _"A good testing approach speeds up development, improves code quality, and limits the bugs in your app"_ -- Edd Yerburgh

.

- **Why Unit Test?** 
	- Confidence to Change Code +  Higher Quality Code + Well-Documented Code = Developer Happiness
- **What to Unit Test?**
	-  Component Contract - Defines the expected behavior of your component and what assumptions are reasonable to have about its usage
	-  Inputs: Props, User Interaction, Lifecycle methods
	-  Outputs: Events, Rendered Output
	-  Connection with Children


-- Matt O'Connell - [Vue NYC - Component Tests with Vue.js](https://www.youtube.com/watch?v=OIpfWTThrK8)

----

.

> 🍓  _"Tests should give you confidence that you aren't shipping broken software"_
-- Sarah Dayan - [Test-Driven Development with Vue.js - Vue.js Amsterdam 2020](https://www.youtube.com/watch?v=LXR1DRm-Gzo)

.

## Helpful Resources:
- ["Testing Vue.js Applications"](https://www.manning.com/books/testing-vue-js-applications) by Edd Yerburgh
    - Live-Book by Vue.js core team member and author of the official Vue testing utility (Vue Test Utils)
- [Vue Test Utils docs](https://vue-test-utils.vuejs.org/guides/)
- [Jest docs](https://jestjs.io/docs/api)
- [Install Jest and Vue Test Utils](https://vue-test-utils.vuejs.org/installation/#semantic-versioning)
- [Vuetify Unit Testing](https://vuetifyjs.com/en/getting-started/unit-testing/)

.

> 🍓 _"In testing, less is more. Every extra unit test you write couples your test code to your source code. When you write unit tests, you need to be more miserly than Scrooge McDuck."_
-- Edd Yerburgh


## Setup Unit Tests in a Vue + Vuetify Project

1. **Install Dependencies**
```sh
vue add unit-jest
npm install --save-dev @vue/test-utils
```

2. **Add a Test Setup File**
```js
// testSetup.js
import Vue from 'vue';
import Vuetify from 'vuetify';
Vue.use(Vuetify);
```

3. **Configure Jest** 
- to look for any `.test` or `.spec` file, rather than only those in a `test` or `__test__` directory
- to utilize our test setup file
```js
// jest.config.js
module.exports = {
	// keep whatever preset was generated
   	// preset: '...'
	testMatch: ['**/?(*.)+(spec|test).[jt]s?(x)'],
 	setupFilesAfterEnv: ['./testSetup.js'],
};
```


## Examples of Unit Testing Integration:

- DevOnBoardingFrontend, `jrhTesting` branch
```sh
# Clone
git clone https://github.com/Swift-Logistics/DevOnboardingFrontend.git

# Navigate to the right place
cd DevOnboardingFrontend && git checkout jrhTesting && code . && npm i

# Run Tests
npm run test:unit
```
- Loop, `jrh-unitTests` branch
```sh
# Clone
git clone https://github.com/Swift-Logistics/Loop.git

# Navigate to the right place
cd Loop && git checkout jrh-unitTests && code . && npm i

# Run Test(s)
npm run test:unit
```


## Common Testing Scripts and Flags
```sh
# run all tests
npm run test:unit

# run all tests in watch mode
npm run test:unit --watch

# run a specific test file
npm run test:unit -- item.spec.js

# run a specific test file in watch mode
npm run test:unit -- item.spec.js --watch

```
