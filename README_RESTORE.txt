OnCallNotifier scaffold

Put your Kotlin sources into:
  app/src/main/java/com/example/oncallnotifier/
    MainActivity.kt
    calendar/GoogleCalendarService.kt
    config/DefaultMonthConfig.kt
    config/MonthConfig.kt
    data/Prefs.kt (optional)
    network/AuthInterceptor.kt
    network/GoogleApis.kt
    network/GoogleCalendarApi.kt
    network/GoogleCalendarModels.kt
    network/GoogleSheetsAPI.kt
    network/RetrofitClient.kt
    network/TokenApi.kt
    network/TokenRepository.kt
    sheets/SheetsHelper.kt
    sync/SyncEngine.kt
    work/DailyCheckWorker.kt
    work/DailySyncWorker.kt
    work/WeeklySyncWorker.kt
    work/StartOnBootReceiver.kt
    work/Scheduler.kt
    work/VolumeAtNineWorker.kt

App-level Gradle (build.gradle.kts) dependencies to add:

dependencies {
    implementation("org.jetbrains.kotlinx:kotlinx-coroutines-android:1.8.1")
    implementation("androidx.core:core-ktx:1.13.1")
    implementation("androidx.appcompat:appcompat:1.7.0")
    implementation("com.google.android.material:material:1.12.0")

    // WorkManager
    implementation("androidx.work:work-runtime-ktx:2.9.0")

    // Retrofit/OkHttp/Gson
    implementation("com.squareup.retrofit2:retrofit:2.11.0")
    implementation("com.squareup.retrofit2:converter-gson:2.11.0")
    implementation("com.squareup.okhttp3:okhttp:4.12.0")
    implementation("com.squareup.okhttp3:logging-interceptor:4.12.0")
    implementation("com.google.code.gson:gson:2.11.0")

    // Google Sign-In
    implementation("com.google.android.gms:play-services-auth:21.2.0")
}

Also ensure in AndroidManifest.xml:
  - INTERNET and RECEIVE_BOOT_COMPLETED permissions present (already in scaffold)
  - StartOnBootReceiver declared (already in scaffold)

Update res/values/strings.xml with your Web application OAuth client id.
