# No Signature of Method error while generating APK

```
A problem occurred evaluating project ':app'.
> No signature of method: build_a8vvdgesylwq237gh9izqh8m2.android() is applicable for argument types: (build_a8vvdgesylwq237gh9izqh8m2$_run_closure1) values: [build_a8vvdgesylwq237gh9izqh8m2$_run_closure1@18da53c9]
```

React Native : 0.69.0
React : 18.0.0

## Solution that worked for me

```
Make changes to app level build.gradle
from signingConfigs object delete debug. Keep only release.
``

```
    signingConfigs {
        release {
            if (project.hasProperty('MYAPP_UPLOAD_STORE_FILE')) {
                storeFile file(MYAPP_UPLOAD_STORE_FILE)
                storePassword MYAPP_UPLOAD_STORE_PASSWORD
                keyAlias MYAPP_UPLOAD_KEY_ALIAS
                keyPassword MYAPP_UPLOAD_KEY_PASSWORD
            }
        }        
    }
```

```
make changes to project level build.gradle
Changed from 7.1.1 to 7.2.1

classpath("com.android.tools.build:gradle:7.2.1")
```
