
Error

```
Could not initialize class org.codehaus.groovy.runtime.InvokerHelper
```

Solution

 - This is because of the gradle version.
 - Go to: gradle/wrapper/gradle-wrapper.properties.
 - Change a version of the course by this:
 
```
distributionUrl=https\://services.gradle.org/distributions/gradle-7.3.3-all.zip
```

Please note for you this may a different gradle version. Check from any of your working projects.
