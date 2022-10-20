---
title: "How to run react native app on an physical device using same network"
date: "2022-10-10"
---

Laptop OS: Windows
Server: Django
Device OS: Android
React Native: CLI

I was developing an app for the final year project using react native and needed it to run on my Android device and also connect to a local python server (Django). I could create an APK file and install it on my device but for that I would need to create keystore file as well (if you want to see how to do that check this link). But I simply wanted the development version of the app to run on my device to show it to my team members and professor. This is what I did -

1. Connect phone and laptop to same network, disable browsable API in settings.py (django server code)
2. Find IPv4 of the network using ipconfig command in cmd. Add this IP to ALLOWED_HOSTS in settings.py of Django.
3. Use that IP to call the Django API from the react native app - replace 10.0.2.2:8000/api with 192.168.1.11:8000/api (use your IP address)
4. Run the python server as `python manage.py runserver 0.0.0.0:8000`
5. Connect phone to laptop using USB and enable USB debugging from developer settings in the phone
6. Make sure phone is visible when you run `adb devices` in cmd
7. Run `npx react-native run-android`. This will install the app on the phone, react native dev server will be started & app will start working.
8. Stop the previous command and disconnect USB connection between the phone & laptop
9. Run `npm start` to run the react native dev server (python server is still running)
10. Open the newly installed app and change the debug settings of host:port in the settings as 192.168.1.11:8081
11. Now the app should work without USB and connect to Django server.

Reference: https://reactnative.dev/docs/running-on-device
