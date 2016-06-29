# Launch Todos Example

[![Build Status](https://travis-ci.org/NewSpring/launch-todos-example.svg?branch=master)](https://travis-ci.org/NewSpring/launch-todos-example)

This is a fork of https://github.com/meteor/simple-todos to demonstrate how to use the [launch tool](https://github.com/newspring/meteor-launch) for building/deploying mobile apps.

![screenshot](screenshot.png)

## Secrets

```
tar cvf secrets.tar launch.json distribution.p12 .keystore google-auth.json deployment_token.json settings.json
travis encrypt-file secrets.tar .travis/secrets.tar.enc
```
