# Expo & React Navigation & Typescript covered by Jest & Testing Library

This repo is a time capsule on how to create and setup an expo application with jest integrations tests.
This repo might be linked inside articles about expo usage.

## Setup

To start this demo repository you need to have [Expo](https://docs.expo.dev/get-started/installation/).

### Install deps

Install dependencies and enter the expo CLI running.

```
expo start
```

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command        | Action                      |
| :------------- | :-------------------------- |
| `npm run test` | Runs the integrations tests |

## How I created this repo

To create and setup the same repository you need to have [Expo](https://docs.expo.dev/get-started/installation/) and [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) installed on your computer.

### Create the app

```bash
npx create-expo-app YOUR-APP-NAME
```

### Setup typescript

To setup typescript create an empty `tsconfig.json` file.

```bash
touch tsconfig.json
```

Then run `expo start`, it will find the `tsconfig.json` and detect that typescript dependencies are not installed and will ask for them to be installed.

```bash
expo start
```

### Testing with jest

#### Install jest

From the official expo documentation [testing with jest](https://docs.expo.dev/guides/testing-with-jest/)
Install `jest` and `expo-jest`

```bash
expo install expo-jest jest
```

As we're using typescript we also need to install related types

```bash
npm install --save-dev @types/jest
```

#### Install react-test-renderer

You should sync your react and react-test-renderer versions.
In our case we're using react 17

```bash
npm i --save-dev react-test-renderer@17 @types/react @types/react-test-renderer@17
```

#### Install react-native testing library

```bash
npm install --save-dev @testing-library/react-native
```

### React Navigation

Following the official doc for react-navigation 6.x [React Navigation installation](https://reactnavigation.org/docs/getting-started#installation) for an expo application installation.

```bash
npm install @react-navigation/native
```

Install dependencies

```bash
npm install react-native-screens react-native-safe-area-context @react-navigation/native-stack
```

### Testing React Navigation

Note that previously in [react-navigation 5.x](https://reactnavigation.org/docs/5.x/getting-started/#installing-dependencies-into-an-expo-managed-project), required the installation of the following dependencies:

- react-native-gesture-handler
- react-native-reanimated
- @react-native-community/masked-view

It looks like it's not required anymore.
But the [Testing with jest](https://reactnavigation.org/docs/testing) guide still asks mocking the dependencies.
In our case we're not, for the moment, using any of these dependencies then we don't have anything to mock.
