This maven module contains an Android project with integration tests for cucumber-android.
It uses the [maven-android-plugin](https://code.google.com/p/maven-android-plugin).

To execute the tests you need the [Android SDK](https://developer.android.com/sdk/index.html) and a running
[emulator](http://developer.android.com/tools/devices/emulator.html) or an attached physcial device. Please
consider `AndroidManifest.xml` for min- and target-sdk versions.

Using maven (recommended only for cucumber developers):

`mvn install -pl examples/android-test -am -P android,android-examples`

Using ant (recommended for users of cucumber):

`TODO: provide standard ant buildfile`

Using [adb](https://developer.android.com/tools/testing/testing_otheride.html#AMSyntax) on the commandline:

`mvn package -pl examples/android-test -am -P android,android-examples`

`adb install -r examples/android-test/target/cucumber-android-test-*.apk`

`adb shell am instrument -w -r cucumber.android.test/cucumber.api.android.CucumberInstrumentation`

Using an IDE:

[Set up your IDE](https://developer.android.com/sdk/installing/index.html) and import this directory as a
new Android test-project. You will also need to create a new run-configuration with `CucumberInstrumentation`.