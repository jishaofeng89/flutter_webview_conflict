# flutter_webview_conflict

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## 处理flutter_webview_plugin, install_plugin, image_picker冲突

- image_picker-0.6.1+4\android\src\main\AndroidManifest.xml
```
  <manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="io.flutter.plugins.imagepicker">
     <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
     <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>

      <application>
          <provider
              android:name="io.flutter.plugins.imagepicker.ImagePickerFileProvider"
              android:authorities="${applicationId}.flutter.image_provider"
              android:exported="false"
              android:grantUriPermissions="true">
              <meta-data
                  android:name="android.support.FILE_PROVIDER_PATHS"
                  android:resource="@xml/filepaths"/>
          </provider>
      </application>
  </manifest>
```

- install_plugin-2.0.1\android\src\main\AndroidManifest.xml
```
  <manifest xmlns:android="http://schemas.android.com/apk/res/android"
      xmlns:tools="http://schemas.android.com/tools"
      package="com.example.installplugin">
      <uses-permission android:name="android.permission.REQUEST_INSTALL_PACKAGES" />
      <application>
          <provider
              android:name="androidx.core.content.FileProvider"
              android:authorities="${applicationId}.fileProvider.install"
              android:exported="false"
              android:grantUriPermissions="true"
              tools:replace="android:authorities">
              <meta-data
                  android:name="android.support.FILE_PROVIDER_PATHS"
                  android:resource="@xml/filepaths"/>
          </provider>
      </application>
  </manifest>
```
