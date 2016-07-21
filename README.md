# Launch Todos Example

[![Build Status](https://travis-ci.org/NewSpring/launch-todos-example.svg?branch=master)](https://travis-ci.org/NewSpring/launch-todos-example)

1. [Build on Travis](https://travis-ci.org/NewSpring/launch-todos-example)
2. [Site on Heroku](https://launch-todos-example.herokuapp.com/)
3. [iOS app download on Hockey](https://rink.hockeyapp.net/apps/dc6361da5fdd4c42ba3aed76ef894f22)
4. [Android app download on Hockey](https://rink.hockeyapp.net/apps/a6221f3834f149599f8da90bd23fd147)

The Google Play and TestFlight uploads you will have to take my word for, but you can see that they are uploading in the Travis builds.

This is a fork of https://github.com/meteor/simple-todos to demonstrate how to use the [launch tool](https://github.com/newspring/meteor-launch) for building/deploying mobile apps.

## launch.json

```json
{
  "XCODE_SCHEME_NAME": "LaunchTodosExample",
  "APP_IDENTIFIER": "cc.newspring.LaunchTodosExample",
  "APPLE_ID": "email@email.com",
  "FASTLANE_PASSWORD": "password",
  "KEYCHAIN_PASSWORD": "password",
  "CERT_KEY_PATH": "distribution.p12",
  "CERT_PASSWORD": "password",
  "SLACK_URL": "https://hooks.slack.com/services/things",
  "SLACK_ROOM": "#room",
  "ANDROID_STORE_PASS": "password",
  "ANDROID_KEY": "launch-todos-example",
  "ANDROID_ZIPALIGN": "path/to/zipalign",
  "IOS_HOCKEY_TOKEN": "token",
  "ANDROID_HOCKEY_TOKEN": "token",
  "ANDROID_HOCKEY_ID": "id",
  "PLAY_AUTH_FILE": "google-auth.json",
  "GALAXY_DEPLOY_HOSTNAME": "galaxy.meteor.com",
  "GALAXY_SESSION_FILE": "deployment_token.json"
}
```

## launch commands

```shell
$ launch galaxy launch-todos-example.meteorapp.com settings.json
$ launch build launch-todos-example.meteorapp.com settings.json
$ launch hockey
$ launch testflight
$ launch playstore
```

## Secrets

```
tar cvf secrets.tar launch.json distribution.p12 .keystore google-auth.json deployment_token.json settings.json
travis encrypt-file secrets.tar .travis/secrets.tar.enc
```
