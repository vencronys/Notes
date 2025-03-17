# Cordova

## Requirements

### Installing Cordova using npm

```bash
 sudo npm install -g cordova
```

This installs Cordova globally.

### Install Android's SDK

I just installed Android Studio, I like my installations to be done locally.

## Pre-requisites

To check if you satisfy requirements for building the platform:

```bash
cordova requirements
```

> [!IMPORTANT]
> If you installed Android studio to manage your SDKs, Just read the docs like I had to man.

I installed sdkman, a tool to manage th SDKs.

## Creating a Cordova App

### Initializing a Cordova project

```bash
cordova create $DIR_NAME $WHATEVER_THAT_IS $APP_NAME 
```

### Adding a platform

```bash
cordova platform add $PLATFORM
```

To check your current set of platforms:

```bash
cordova platform ls
```

To build the app:

```bash
cordova build $PLATFORM
```

To emulate the app:

```bash
cordova emulate $PLATFORM
```

## Adding plugins

Agian, read docs, I just installed the geolocation one using:
```bash
cordova plugin add cordova-plugin-geolocation
```