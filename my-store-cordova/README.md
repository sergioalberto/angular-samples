# MyStore

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.1.1.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

Example:
![Alt text](src/assets/my-store.png?raw=true "My Store")

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Deploy on Firebase
Run
- `npm install -g firebase-tools`
- `firebase login` 
- `firebase init` (after to build the project (`ng build --prod`), select `Hosting: Configure and deploy Firebase Hosting sites` option and use `dist/my-store` path)
- `firebase deploy`

Go to [My Store](https://food-delivery-mmxqxb.web.app/)

## Cordova with Docker
- `sudo docker build -t cordova .`
- `sudo docker run -ti --name=cordova -v $(pwd):/workspace --privileged --net host -v /dev/bus/usb:/dev/bus/usb cordova`

## Run Cordova in the Docker container
- `cordova create mobile sergiogq.myStore MyStore`
- `cd mobile`
- `rm -rf www`
- `ln -s ../dist/my-store-cordova/ www`
- `cordova platform add android`
- `cordova build android` 
- `cordova run android`

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
