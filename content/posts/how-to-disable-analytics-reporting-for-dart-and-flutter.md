---
date: "2024-03-03T15:42:37+00:00"
title: "How to Disable Analytics Reporting for Dart and Flutter"
---

The official documentation states:

> The _Flutter_ tool uses _Google Analytics_ to report feature usage statistics and send crash reports. This data is used to help improve _Flutter_ tools over time.  
> _Flutter_ tool analytics are not sent on the very first run.  
> _Dart_ tools might also send usage metrics and crash reports to _Google_.

## Disabling Analytics for the _Flutter_ SDK

Run one of the following commands:

```sh
flutter config --no-analytics
```

or:

```sh
flutter --disable-analytics
```

## Disabling Analytics for the _Dart_ Language

Run the following command:

```sh
dart --disable-analytics
```

These commands worked immediately after installing _Flutter_ from the _AUR_ on _Arch Linux_.

---

## Documentation

- <https://docs.flutter.dev/get-started/install/linux>
