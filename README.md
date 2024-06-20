# rn-codegen-javapackagename

![Build](https://github.com/mfazekas/rn-codegen-javapackagename/workflows/Pre%20Merge%20Checks/badge.svg)


# Steps to reproduce the issue:

1.) Remove the following from package.json, so we can run 
```json
    ,
    "includesGeneratedCode": true,
    "outputDir": {
      "android": "android/codegen"
    }
```

2.)
```sh
cd ReproducerApp
yarn install
cd android 
./gradlew generateCodegenArtifactsFromSchema
```

observe
```sh
RTNCalculator/android/build/generated/source/codegen/java/com/rtncalculator/NativeRTNCalculatorSpec.java
```

restore codegeConfig on package.json

```sh
cd ReproducerApp
npx react-native codegen --path ../RTNCalculator --platform android
```

observe:
```
ReproducerApp/android/codegen/java/com/facebook/fbreact/specs/NativeRTNCalculatorSpec.java
```


## Reproducer todo list

- [x] Create a new reproducer project.
- [x] Git clone your repository locally.
- [x] Edit the project to reproduce the failure you're seeing.
- [x] Push your changes, so that Github Actions can run the CI.
- [x] Make sure the repository is public and share the link with the issue you reported.
