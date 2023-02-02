# AirSnap Android SDK

**Session Replay for Mobile Apps**

Build the perfect digital experience by seeing exactly how your customers are using your app.

https://www.airsnap.io/

## Installation

Include JitPack repository to your root `build.gradle`

```
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

Then add the dependency

```
dependencies {
    implementation("com.github.airsnapio:airsnap-android:0.0.4@aar") { transitive = true }
}
```

## Usage

#### Start Session

```
import io.airsnap.sdk.AirSnap;
import io.airsnap.sdk.AirSnapConfig;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate() {
        ...

        AirsnapConfig config = new AirsnapConfig("<api-key");
        AirSnap.start(this, config)
    }
}
```

#### Intercept Network Requests

```
import io.airsnap.sdk.network.AirsnapInterceptor;

OkHttpClient okHttpClient = new OkHttpClient.Builder()
    .addInterceptor(new AirsnapInterceptor())
    .build();
```
