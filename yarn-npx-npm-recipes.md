# Recipes

**PREREQUISITE:** Install nvm

## uninstall/install/select npm using nvm

```console
nvm uninstall 14.16.0
nvm install 14.16.0
nvm use 14.16.0
```

## install & upgrade yarn

```console
npm install -g yarn
yarn set version latest
```

## create applications from templates

### react native with typescript

```console
npx react-native init my-app --template react-native-template-typescript
npx create-react-native-app my-app --template-with-typescript <-->
```

add windows target & run

```console
npx react-native-windows-init --overwrite
npx react-native run-windows
```

### react with typescript

```console
npx create-react-app my-app --template typescript

yarn create react-app my-app --template typescript
```
