# **使用android support库时firebase最新版本依赖库**

Update - May 31, 2019

Cloud Firestore version 19.0.2

- Updated gRPC to 1.21.0. A bug in the prior version would occasionally cause a crash if a network state change occurred concurrently with an RPC. Refer to [GitHub issue #428](https://github.com/firebase/firebase-android-sdk/issues/428) for more details.

Cloud Firestore Kotlin extensions version 19.0.2

Visit the [open source documentation](https://firebaseopensource.com/projects/firebase/firebase-android-sdk/docs/ktx/firestore.md) to learn more about getting started with and using Kotlin extensions.

The Kotlin extensions library transitively includes the updated `firebase-firestore` library. The Kotlin extensions library has no additional updates.

Firebase Bill of Materials (Firebase BoM) version 19.0.0



Firebase Android SDKs mapped to this BoM version:

- `com.google.firebase:firebase-core:16.0.9`
- `com.google.firebase:firebase-ads:17.2.1`
- `com.google.firebase:firebase-analytics:16.5.0`
- `com.google.firebase:firebase-appindexing:18.0.0`
- `com.google.firebase:firebase-auth:17.0.0`
- `com.google.firebase:firebase-firestore:19.0.2`
- `com.google.firebase:firebase-functions:17.0.0`
- `com.google.firebase:firebase-messaging:18.0.0`
- `com.google.firebase:firebase-storage:17.0.0`
- `com.google.firebase:firebase-crash:16.2.1`
- `com.google.firebase:firebase-dynamic-links:17.0.0`
- `com.google.firebase:firebase-invites:17.0.0`
- `com.google.firebase:firebase-inappmessaging:17.2.0`
- `com.google.firebase:firebase-inappmessaging-display:17.2.0`
- `com.google.firebase:firebase-ml-vision:20.0.0`
- `com.google.firebase:firebase-ml-vision-image-label-model:17.0.2`
- `com.google.firebase:firebase-ml-vision-face-model:17.0.2`
- `com.google.firebase:firebase-ml-natural-language:19.0.1`
- `com.google.firebase:firebase-ml-natural-language-language-id-model:19.0.1`
- `com.google.firebase:firebase-ml-natural-language-smart-reply-model:19.0.1`
- `com.google.firebase:firebase-ml-model-interpreter:19.0.0`
- `com.google.firebase:firebase-perf:17.0.2`
- `com.google.firebase:firebase-database:17.0.0`
- `com.google.firebase:firebase-config:17.0.0`
- `com.crashlytics.sdk.android:crashlytics:2.10.1`

# 使用androidx库时再以下链接查找最新依赖库

https://firebase.google.com/support/release-notes/android#bom_v20-0-0