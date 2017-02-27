[中文](localization/zh/README.md) - [Português](localization/pt/README.md)

# Ampiri SDK Integration

Boost your app's revenue streams and save time: sign up for an account at [Ampiri.com](https://ampiri.com)

## Contents

* [Ampiri Support](#ampiri-support)
* [Supported Ad Networks and Ad Types](#supported-ad-networks-and-ad-types)
* [Requirements](#requirements-and-dependencies)
* [Add the Ampiri SDK and 3rd-party Networks to your Project](#add-the-ampiri-sdk-and-to-your-project)
* [Update your Android Manifest](#update-your-android-manifest)
* [Banner Layout and Activity](#banner-layout-and-activty)
* [Interstitial Layout and Activity](#interstitial-layout-and-activty)
* [Video Layout and Activity](#video-layout-and-activty)
* [Native and In-Feed Templates and UI](#native-and-in-feed-templates-and-ui)
* [Ad Events Handling (Callbacks)](#ad-events-handling-callbacks)
* [Demo App/ Testing](#demo-sample-app-testing)

## Ampiri Support

Additional documentation for integrating the Ampiri SDK with your Android app can be found by clicking the links.

- [Ampiri.com Tutorials](http://www.ampiri.com/tutorials/) - Tutorials and Sign Up to Ampiri
- [Publisher's Self-Serve UI User Guide](https://ampiri.zendesk.com/hc/en-us/articles/213857245-Publisher-s-Self-Serve-UI-User-Guide) - Publisher's Interface Guide
- [Ampiri SDK Android Quickstart](https://ampiri.zendesk.com/hc/en-us/articles/213431769-Ampiri-SDK-Android-Quickstart) - Basic Integration
- [Ampiri SDK Android Integration Manual](https://ampiri.zendesk.com/hc/en-us/articles/115000510445-Ampiri-SDK-Android-Integration-Manual) - Ampiri SDK Reference Manual
- [Zendesk Support](https://ampiri.zendesk.com/hc/en-us) - Support and FAQ

## Supported Ad Networks and Ad Types ##

Ampiri supports the following ad networks on the client-side:

To show *standard banner* ads:

| Specification | Network | Version |
|----------|----------|----------|
|`ampiri-sdk-mediation-admob`|[Google Mobile Ads](https://developers.google.com/admob/android/quick-start)|v10.0.1, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-mopub`|[MoPub](https://github.com/mopub/mopub-android-sdk)|v4.11.0, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-facebook`| [Facebook Audience](https://developers.facebook.com/docs/audience-network)|v4.18.0, API 11: Android 3.0 (Honeycomb)|
|`ampiri-sdk-mediation-inlocomedia`| [InLocoMedia](http://docs.inlocomedia.com)| v2.5.0, API 14: Android 4.0 (ICE_CREAM_SANDWICH)|

To show *interstitial* ads:

| Specification | Network | Version |
|----------|----------|----------|
|`ampiri-sdk-mediation-admob`|[Google Mobile Ads](https://developers.google.com/admob/android/quick-start)|v10.0.1, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-mopub`|[MoPub](https://github.com/mopub/mopub-android-sdk)|v4.11.0, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-chartboost`|[Chartboost](https://answers.chartboost.com/hc/en-us/articles/201219545-Download-Integrate-the-Chartboost-SDK-for-Android)|v6.6.1, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-facebook`|[Facebook Audience](https://developers.facebook.com/docs/audience-network)|v4.18.0, API 11: Android 3.0 (Honeycomb)|
|`ampiri-sdk-mediation-nativex`|[NativeX](https://github.com/nativex/NativeX-Android-SDK)|v5.5.9, API 11: Android 3.0 (Honeycomb)|
|`ampiri-sdk-mediation-applovin`|[AppLovin](https://github.com/AppLovin/Android-Demo-App)|v6.4.2, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-inlocomedia`| [InLocoMedia](http://docs.inlocomedia.com)| v2.5.0, API 14: Android 4.0 (ICE_CREAM_SANDWICH)|

To show *video* ads:

| Specification | Network | Version |
|----------|----------|----------|
|`ampiri-sdk-mediation-adcolony`|[AdColony](https://github.com/AdColony/AdColony-Android-SDK)|v2.3.6, API 14: Android 4.0 (Ice Cream Sandwich)|
|`ampiri-sdk-mediation-unityads`|[Unity Ads](https://github.com/Applifier/unity-ads-sdk)|v2.0.8, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-chartboost`|[Chartboost](https://answers.chartboost.com/hc/en-us/articles/201219545-Download-Integrate-the-Chartboost-SDK-for-Android)|v6.6.1, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-nativex`|[NativeX](https://github.com/nativex/NativeX-Android-SDK)|v5.5.9, API 11: Android 3.0 (Honeycomb)|
|`ampiri-sdk-mediation-vungle`|[Vungle](https://v.vungle.com/sdk)|v4.0.3, API 11: Android 3.0 (Honeycomb)|

To show *native* ads:

| Specification | Network | Version |
|----------|----------|----------|
|`ampiri-sdk-mediation-admob`|[Google Mobile Ads](https://developers.google.com/admob/android/quick-start)|v10.0.1, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-mopub`|[MoPub](https://github.com/mopub/mopub-android-sdk)|v4.11.0, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-facebook`|[Facebook Audience](https://developers.facebook.com/docs/audience-network)|v4.18.0, API 11: Android 3.0 (Honeycomb)|
|`ampiri-sdk-mediation-applovin`|[AppLovin](https://github.com/AppLovin/Android-Demo-App)|v6.4.2, API 9: Android 2.3 (Gingerbread)|
|`ampiri-sdk-mediation-baidu`|[Baidu](http://mssp.baidu.com/app/static/main.html#/sdk)|v5.6, API 8: Android 2.2 (Froyo)|
|`ampiri-sdk-mediation-inlocomedia`| [InLocoMedia](http://docs.inlocomedia.com)| v2.5.0, API 14: Android 4.0 (ICE_CREAM_SANDWICH)|

> We can't guarantee stable functionality of the SDK if you use other versions of these network libraries.

You must set up each 3rd-party network on the Ampiri website, otherwise they will not be used for showing ads.

## Requirements and Dependencies ##

* Android 2.3 (API Version 9) and up
* support-annotations, v25.2.0
* support-v4, v25.2.0
* **Recommended** Google Play Services 10.0.1

We strongly recommend compiling your app using **Google Play services**, in order to use the `Android Advertising ID`
instead of the`Device ID`, as required by Google. Failing to correctly use the `Android Advertising ID` may result in your submission to the Play Store being rejected.

>NOTE: You must have a different **adUnitId** for every ad space placement in your app. If you use the same ID for multiple placements or the IDs from the testing/demo examples, reporting errors will occur and there will be no payout. Please ask your account manager for further details.

## Add the Ampiri SDK and 3rd-party Networks to your Project ##
The Ampiri SDK is available via:

1. jCenter AAR (**Recommended**)
2. Zipped AAR

Add the following rows in your _app_ module `build.gradle` file:

```
repositories {
  maven { url "http://ampiri.bintray.com/maven" }
}

dependencies {
  compile 'com.ampiri.sdk:ampiri-sdk:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-adcolony:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-admob:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-unityads:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-applovin:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-chartboost:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-facebook:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-inlocomedia:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-mopub:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-nativex:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-vungle:3.6.0'
  compile 'com.ampiri.sdk:ampiri-sdk-mediation-baidu:3.6.0'

  compile 'com.google.android.gms:play-services-ads:10.0.1'
}
```

### Include the Local .aar Libraries ###

Save the `aar` files under _app_ module's `libs` folder (eg: `<project>/<app>/libs`)

Then add the following rows in your _app_ module `build.gradle` file:

```
repositories {
  flatDir {
    dirs 'libs'
  }
}

dependencies {
  compile(name: 'ampiri-sdk', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-adcolony', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-admob', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-applovin', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-unityads', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-chartboost', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-facebook', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-inlocomedia', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-mopub', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-nativex', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-vungle', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mediation-baidu', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-mraid', version:'3.6.0', ext: 'aar')
  compile(name: 'ampiri-sdk-vast', version:'3.6.0', ext: 'aar')

  compile 'com.google.android.gms:play-services-ads:10.0.1'
  compile 'com.facebook.android:audience-network-sdk:4.18.0'
  compile ('com.mopub:mopub-sdk:4.11.0@aar') {
    transitive = true
  }
  compile 'com.inlocomedia.android:android-sdk:2.5.0'
  compile 'com.google.code.gson:gson:2.8.0'
}
```

Then add follow rows in your _app_ module `proguard-rules.pro` file:

```
-keep class com.ampiri.** { *; }
-dontwarn com.ampiri.**
```

## Modify your Android Manifest ##

Under the main `<manifest>` element, add the following permissions.

```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.READ_PHONE_STATE"/>
```
* ACCESS_COARSE_LOCATION (recommended) - Grants the SDK permission to access approximate location based on cell tower.
* ACCESS_FINE_LOCATION (recommended) - Grants the SDK permission to access a more accurate location based on GPS.

Although not technically required, the LOCATION permissions make it possible for the SDK to send location-based data to advertisers. Sending better
location data generally leads to better monetization.

* WRITE_EXTERNAL_STORAGE (optional) - Allows the SDK to cache all ad assets (creatives, custom frames, etc.) in external memory. This can maximize
performance by ensuring immediate delivery of ads and minimize network traffic used by the SDK by keeping cached
ad assets available even after the user closes the app.

* READ_PHONE_STATE (recommended) - Allows the SDK to handle calls interrupting video playback during videos.

> When using SDK as a library project, you shouldn't need to worry about merging AndroidManifest.xml changes or Proguard settings. If you run into problems, make sure `manifestmerger.enabled` is set to `true` in `project.properties`

Please see the Android documentation [here](https://developer.android.com/studio/build/shrink-code.html).

## Banner Initialization ##
Add a banner to layout file, e.g.:
```xml
<FrameLayout
    android:id="@+id/ad_view"
    android:layout_width="320dp"
    android:layout_height="50dp"
    android:background="@android:color/white"/>
```

It is advisable to make the banner size in the layout the same as teh required one (see below). Otherwise, the banner might be displayed incorrectly.

Add the following code to your activity:
```java
FrameLayout adView = (FrameLayout) view.findViewById(R.id.ad_view);
StandardAd standardAd = new StandardAd(this, adView, "YOUR_STANDARD_AD_UNIT_ID", BannerSize.BANNER_SIZE_320x50, adListener);
standardAd.loadAd();
```

Banners `320*50` are served by default. Available sizes:

* 320x50
* 728x90

### Standard Banner Auto-update

You can switch the banner auto-update function on or off; to do this, call `setAutorefreshEnabled()` method, e.g.:
```java
standardAd.setAutorefreshEnabled(false);
```

By default, auto-update is switched on. The auto-update period is set up via the admin panel.

From version 3.4 onwards, the SDK’s interface includes the `showAd()` method. It is strongly recommended to call this method after the standard banner’s view became visible, as it will then trigger an impression event.

## Interstitial Initialization and Activity ##

> Note: All SDK method calls should be done from the main thread (Main thread, UI thread).

### Interstitial Ad Initialization

Add the following code to your activity:
```java
InterstitialAd interstitialAd = new InterstitialAd(this, "YOUR_INTERSTITIAL_AD_UNIT_ID", adListener);
interstitialAd.loadAd();
```
After calling the `loadAd()` method, the interstitial download starts. If you call `loadAd()` again before the banner is fully served, the previous request processing is cancelled. In this case, only the last request will be processed.

When the banner download is completed, you can display the banner by calling `showAd()` method.
```java
interstitialAd.showAd();
```

To learn about download completion, subscribe to banner events (see [Step 8 - Ad Events Handling](#step-8-ad-events-handling)) or call method `isReady()`.
```java
interstitialAd.isReady();
```

If your application workflow allows showing full screen banners at any time and in any place, there are 2 additional ways to show it right after the loading has finished or with a custom delay after method invocation.

To load and show full screen banner right after it was loaded use:
```java
interstitialAd.loadAndShow()
```

To load and show full screen banner with a custom delay after method invocation use:
```java
interstitialAd.loadAndShowWithDelay()
```
The delay interval is specified via Admin UI interface.

If you want full control over when and where to show full screen banners, use the following steps:

1. Call `interstitialAd.loadAd()` in advance
2. Set `AdEventCallback` to handle banner events
3. When you want to show the banner, check that it is ready and show: `if (interstitialAd.isReady()) interstitialAd.showAd()`
4. Start loading next banner in `onAdClosed()` event handler of `AdEventCallback`

## Video Initialization and Activity ##


> Note: All SDK method calls should be done from the main thread (Main thread, UI thread).

### Video Ad Initialization

Add the following code to your activity:
```java
VideoAd videoAd = new VideoAd(this, "YOUR_VIDEO_AD_UNIT_ID", adListener);
videoAd.loadAd();
```

The *Close* button for video ads is supported for some networks. If you want to enable this button you should add a boolean parameter in the video ad constructor:
```java
VideoAd videoAd = new VideoAd(this, "YOUR_VIDEO_AD_UNIT_ID", closeButtonEnabled);
or
VideoAd videoAd = new VideoAd(this, "YOUR_VIDEO_AD_UNIT_ID", closeButtonEnabled, adListener);
```

After calling the `loadAd()` method, the video download starts. If you call `loadAd()` again before the video has started to show, new request processing is cancelled. Only one request will be processed.

When the video download is completed, you can display it by calling the `showAd()` method.
```java
videoAd.showAd();
```

To learn about download completion, subscribe to video banner events (see [Ad events handling](#ad-events-handling) section) or call method `isReady()`.
```java
videoAd.isReady();
```

## Native and In-Feed, Templates and UI ##

>Note: All SDK method calls should be done from the main thread (Main thread, UI thread).

Native ads are loaded via the `NativeAd` class, which has its own `Builder` class to customize it during creation:

```java
NativeAd nativeAd = new NativeAd.Builder()
  .setAdUnitId(YOUR_NATIVE_AD_UNIT_ID)
  .setCallback(adListener)
  .build(this);
```

To show native ads you can use two methods:

* Create an ad view programmatically from template and add it to the screen.
* Add `NativeAdView` view in the layout and bind loaded data to this view.

### Templates

Ampiri SDK provides 3 types of templates for native ads

* FeedCardNativeAdView - Icon, title, description, star rating, and CTA button
* StoryCardNativeAdView - Icon, image, title, description, star rating, and CTA button
* VideoCardNativeAdView - Icon, image/video/carousel, title, description, star rating, and CTA button

> Every template has a label that clearly indicates that it is an ad. For example "Ad" or "Sponsored".

If you want to use one of these templates, you can add the selected template in the creation of the `NativeAd`:

```java
.setAdViewBuilder(FeedCardNativeAdView.BUILDER);
```


Add a banner place to layout, e.g.:
``` xml
  <FrameLayout
    android:id="@+id/ad_container"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:visibility="gone"/>
```

After calling the `loadAd()` method, the ad download starts. If you call `loadAd()` again before the banner is fully served, new request processing is
ignored. In this case, only the first request will be processed.

When the banner download is completed, you can display the banner by calling `renderAdView()` method.

```java
adContainerView = (FrameLayout) view.findViewById(R.id.ad_container);

@Override
public void onAdLoaded() {
  adContainerView.setVisibility(View.VISIBLE);
  adContainerView.removeAllViews();
  adContainerView.addView(nativeAd.renderAdView());
}
```

### Create Native UI

In order to create custom native ads ui, you will need to go through following steps:

* Create all needed views (icon view, main image view, text views, rating bar etc...)
* Pass the views to our SDK

You can either create your custom views in a layout `.xml`, or you can add elements in the code.

> All views should be placed in one child; this child itself should be placed in `NativeAdView`.

Custom layout `.xml`. For example:

``` xml
<com.ampiri.sdk.banner.NativeAdView android:id="@+id/native_ad"
 ...>
    <RelativeLayout ...>
        <ImageView android:id="@+id/native_ad_icon"
          ... />
        <ImageView android:id="@+id/native_ad_cover_image"
          ... />
        <FrameLayout android:id="@+id/native_ad_media_container"
          ... />
        <TextView android:id="@+id/native_ad_title"
          ... />
        <TextView android:id="@+id/native_ad_text"
          ... />
        <RatingBar android:id="@+id/native_ad_star_rating"
          ... />
        <Button android:id="@+id/native_ad_call_to_action"
          ... />
        <TextView android:id="@+id/native_ad_attribution"
          ... />
        <ImageView android:id="@+id/native_ad_choices_icon"
          android:layout_width="40dp"
          android:layout_height="40dp"
          android:padding="10dp"
          ... />
        <FrameLayout
          android:id="@+id/native_ad_choices_container"
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:minHeight="20dp"
          android:minWidth="20dp"
          ... />
    </RelativeLayout>
</com.ampiri.sdk.banner.NativeAdView>
```

After you created all the views, please proceed by passing the views to our SDK. For example:

```java
  adView = (NativeAdView) view.findViewById(R.id.native_ad);

  adView.setIconView(R.id.native_ad_icon);
  adView.setCoverImageView(R.id.native_ad_cover_image);
  adView.setMediaContainerView(R.id.native_ad_media_container);
  adView.setTextView(R.id.native_ad_text);
  adView.setTitleView(R.id.native_ad_title);
  adView.setCallToActionView(R.id.native_ad_call_to_action);
  adView.setStarRatingView(R.id.native_ad_star_rating);
  adView.setAdAttributionView(R.id.native_ad_attribution);
  adView.setAdChoiceIconView(R.id.native_ad_choices_icon);
  adView.setAdChoiceContainerView(R.id.native_ad_choices_container);
```

Registering the native ad view in the creation of the `NativeAd`:

```java
.setAdView(adView);
```

After calling the `loadAd()` method, the ad download starts. If you call `loadAd()` again before the banner is fully served, new request processing is
ignored. In this case, only the last request will be processed.

When banner download is completed, you can display the banner by calling `showAd()` method.

To learn about download completion, subscribe to ad events (see [Ad events handling](#ad-events-handling) section) or call method `isReady()`.
```java
nativeAd.isReady();
```

### Customize Native UI

With a native template, you can customize the following elements:

* Title
    * Text font (DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF)
    * Text size
    * Text color
    * Max Ems (25 by default)
* Icon
    * Dimensions(width, height)
    * Margins (left, right)
* Star rating
    * Star size (SMALL, MEDIUM, LARGE)
* Attribution label
    * Default text
    * Text font (DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF)
    * Text size
    * Text color
* Cover image
    * Background color
    * Background resource
    * Margins (left, right, bottom, top)
    * Alignment (undefine, top, bottom, left, right, center, center_vertical, center_horizontal)
* Description
    * Text font (DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF)
    * Text size
    * Text color
    * Margins (left, right)
    * Max Ems (100 by default)
* Call To Action button
    * Default text
    * Text font (DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF)
    * Text size
    * Text color
    * Max Ems (25 by default)
    * Background color
    * Background resource
    * Margins (left, right)

In order to customize these elements, you will need to build an attributes object and provide the following in the creation of the `NativeAd`:
```java
.setAdUnitId(AD_UNIT_ID)
.setAdViewBuilder(StoryCardNativeAdView.BUILDER)
.setAdViewAttributes(new NativeAdView.Attributes(this)
    .setTitle(new NativeAdView.Attributes.Setter<NativeAdView.Attributes.Title>() {
        @Override
        public NativeAdView.Attributes.Title set(@NonNull NativeAdView.Attributes.Title builder) {
            return builder
                    .setTextFont(Typeface.MONOSPACE)
                    .setTextColor(Color.RED)
                    .setMaxEms(20);
        }
    })
    .setStarRating(new NativeAdView.Attributes.Setter<NativeAdView.Attributes.StarRating>() {
        @Override
        public NativeAdView.Attributes.StarRating set(@NonNull NativeAdView.Attributes.StarRating builder) {
            return builder.setStarSize(Size.MEDIUM);
            }
        })
    .setAdAttribution(new NativeAdView.Attributes.Setter<NativeAdView.Attributes.AdAttribution>() {
        @Override
        public NativeAdView.Attributes.AdAttribution set(@NonNull final NativeAdView.Attributes.AdAttribution adAttribution) {
            return adAttribution.setDefaultText(R.string.sponsored);
        }
}))
```

Also, you can set the style of your `NativeAdView` layout by using following attributes:

|Attribute Name | Format | Description |
|---|---|---|
| `Title` |
| ampiriTitleTextFont | DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF | Font of the Title text |
| ampiriTitleTextSize | reference,dimension | Size of the Title text|
| ampiriTitleTextColor | reference,color | Color of the Title text|
| ampiriTitleTextMaxLengthEms | integer | Maximum Ems of the Title text|
| `Icon` |
| ampiriIconWidth | reference,dimension | Icon view width |
| ampiriIconHeight | reference,dimension |Icon view height|
| ampiriIconMarginLeft | reference,dimension | Icon view left margin|
| ampiriIconMarginRight | reference,dimension | Icon view right margin|
| `Star Rating` |
| ampiriStarRatingSize | SMALL, MEDIUM, LARGE | Size of the rating bar stars. SMALL - 10dp for height and width, MEDIUM - 16dp, LARGE - 22dp|
| `Ad Attribution` |
| ampiriAdAttributionTextFont | DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF | Font of the Attribution label text |
| ampiriAdAttributionTextSize | reference,dimension | Size of the Ad Attribution text|
| ampiriAdAttributionTextColor | reference,color | Color of the Ad Attribution text|
| ampiriAdAttributionDefaultText | reference,string | Default Ad Attribution text|
| `Cover Image` |
| ampiriCoverImageBackgroundColor | reference,color | Cover Image background color|
| ampiriCoverImageBackgroundResource | reference | Cover Image background resource|
| ampiriCoverImageMarginLeft | reference,dimension | Cover Image left margin|
| ampiriCoverImageMarginRight | reference,dimension | Cover Image right margin|
| ampiriCoverImageMarginTop | reference,dimension | Cover Image top margin|
| ampiriCoverImageMarginBottom | reference,dimension | Cover Image bottom margin|
| ampiriCoverImageAlignment | undefine, top, bottom, left, right, center, center_vertical, center_horizontal | Cover Image alignment within the NativeAd view|
| `Description` |
| ampiriDescriptionTextFont | DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF | Font of the Description text |
| ampiriDescriptionTextSize | reference,dimension | Size of the Description text|
| ampiriDescriptionTextColor | reference,color | Color of the Description text|
| ampiriTitleTextMaxLengthEms | integer | Maximum Ems of the Description text|
| ampiriDescriptionMarginLeft | reference,dimension | Description view left margin|
| ampiriDescriptionMarginRight | reference,dimension | Description view right margin|
| `Call To Action` |
| ampiriCallToActionBackgroundColor |  reference,color | Color of the Call To Action button |
| ampiriCallToActionTextFont | DEFAULT, DEFAULT_BOLD, MONOSPACE, SANS_SERIF, SERIF | Font of the Description text |
| ampiriCallToActionTextSize | reference,dimension | Size of the Call To Action button text|
| ampiriCallToActionTextColor | reference,color | Color of the Call To Action button text|
| ampiriCallToActionMarginLeft | reference,dimension | Call To Action button view left margin|
| ampiriCallToActionMarginRight | reference,dimension | Call To Action button view right margin|
| ampiriCallToActionMarginTop | reference,dimension | Call To Action button view top margin|
| ampiriCallToActionMarginBottom | reference,dimension | Call To Action button view bottom margin|
| ampiriCallToActionDefaultText | reference,string | Default Call To Action text|

You can set this attributes in your custom `NativeAdView` layout
``` xml
<com.ampiri.sdk.banner.NativeAdView android:id="@+id/native_ad"
    app:ampiriTitleTextFont="MONOSPACE"
    app:ampiriIconWidth="42dp"
    app:ampiriIconHeight="42dp"
    app:ampiriCallToActionTextColor="@android:color/lighter_gray"
 ...>
```

### In-Feed Viewer ###

> Note: All SDK method calls should be done from the main thread (Main thread, UI thread).

Add the following code to your activity:

```java
StreamAdAdapter adAdapter = new StreamAdAdapter.Builder()
  .setAdapter(new MainAdapter(this))
  .setAdUnitId("YOUR_NATIVE_AD_UNIT_ID")
  .setViewBuilder(FeedCardNativeAdView.BUILDER)
  .setEventCallback(this)
  .build(this);
listView.setAdapter(adAdapter);
adAdapter.loadAd();
```

After calling the `loadAd()` method, the in-feed ad download starts. If you call `loadAd()` again before the native ad is fully served, new request processing is cancelled. Only one request will be processed.

When in-feed ad download is completed, it will show automatically.

To learn about download completion, subscribe to ad events (see [Ad events handling](#ad-events-handling) section).


## Ad Events Handling (Callbacks)

To receive events from ad, you should implement an event listener interface `AdEventCallback`.

Listener example:
```java
AdEventCallback adListener = new AdEventCallback() {
    @Override
    public void onAdLoaded() {
    }

    @Override
    public void onAdFailed(@NonNull final ResponseStatus responseStatus) {
    }

    @Override
    public void onAdOpened() {
    }

    @Override
    public void onAdClicked() {
    }

    @Override
    public void onAdClosed() {
    }

    @Override
    public void onAdCompleted() {
    }
};
```

## Demo (Sample) App/ Testing

### Steps

1. Download the Ampiri Demo (Sample) from GitHub.
2. Import the Ampiri Demo (Sample App) into Android Studio under *File > New > Import Project*.
3. In the Ampiri UI, set the status of **the Ad Unit you want to use** to *Test*.
4. In the Ampiri UI, click the "Click to Copy Ad Unit ID" button to copy the placement ID to the clipboard.
5. In Android Studio, in the Java activity of the Ad Type of **the Ad Unit you want to use**, paste the Ad Unit ID from Step 4.
6. In the Android Studio main menu, select **Run** and click *Run* to compile and run the App.
7. In the Android emulator (or your device) where the app is running with Ampiri, select the Ad Type from Step 4 and you will see the event register in the Ampiri Publishers's Self Serve UI under *Reporting*.

[For advanced SDK topics, click here.](CONFIGURATION.md)
