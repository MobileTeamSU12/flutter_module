# flutter_module
mobimap flutter module build

## Attach Flutter vào Android Native
### B1: build `aar` từ flutter module `flutter build aar`
### B2: push libs đã build ở đường dẫn '{project_flutter_module}/build/host/outputs/repo' lên git repo 'https://github.com/MobileTeamSU12/flutter_module.git'
### B3: Config gradle 
```
allprojects {
  ...
  String storageUrl = System.env.FLUTTER_STORAGE_BASE_URL ?: "https://storage.googleapis.com"
  repositories {
    ...
    maven {
      url "https://github.com/MobileTeamSU12/flutter_module/tree/main/android/repo"
    }
    maven {
      url "$storageUrl/download.flutter.io"
    }
    ...
  }
}
```

## Attach Flutter vào IOS Native

