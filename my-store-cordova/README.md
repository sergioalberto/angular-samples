# Add Device Platform

Run `cordova platform add android [any of your choice]` 

# AngularApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 7.2.1.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Cordova with Docker
- `sudo docker build -t cordova .`
- `sudo docker run -ti --name=cordova -v $(pwd):/workspace --privileged --net host -v /dev/bus/usb:/dev/bus/usb cordova`

## Run Cordova in the Docker container
- `npm run build`
- `cordova platform add android@6.4.0`

```bash
android update sdk --no-ui --filter build-tools-26.0.0,android-26,extra-android-m2repository
android update sdk --no-ui --all --filter platform-tools,android-26,extra-android-m2repository
sdkmanager --update
```
- `cordova build android` 
- `cordova run android`

Example:
![Alt text](src/assets/my-store.jpeg?raw=true "My App")

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
# AngularToMobileProject
A demo project to convert Angular Project to Mobile App using Cordova
