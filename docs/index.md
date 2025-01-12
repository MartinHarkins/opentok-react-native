### OpenTok React Native docs

## Basic sample

This simplest use of these opentok-react-native componenents:

```
<OTSession apiKey="your-api-key" sessionId="your-session-id" token="your-session-token">
  <OTPublisher style={{ width: 100, height: 100 }}/>
  <OTSubscriber style={{ width: 100, height: 100 }} />
</OTSession>
```

Replace `your-api-key`, `your-session-id`, and `your-session-token` with your
[OpenTok project API key](https://tokbox.com/account/),
an [OpenTok session ID](https://tokbox.com/developer/guides/create-session/),
and a [token for the session](https://tokbox.com/developer/guides/create-token/).

Note that you add the OTPublisher and OTSubscriber components and children of
the OTSession component. Use the `style` and `className` properties to use CSS
to adjust publisher and subscriber layout.

## Reference docs 

The OpenTok React Native library includes the following components:

* [OTPublisher](./OTPublisher.md) -- Represents an OpenTok publisher.
* [OTSession](./OTSession.md) -- Represents an OpenTok session.
* [OTSubscriber](./OTSubscriber.md) -- Represents an OpenTok subscriber.

It also includes an [OT](./OT.md) object that includes methods for logging.

For details on events dispatched by the OTPublisher, OTSession, and OTSubscriber
components, see [Event data](./EventData.md).

## Unsupported features

The OpenTok React Native library provides a React interface for using the
OpenTok Android and iOS client SDKs. The following advanced features of the OpenTok Android and
iOS client SDKs are *unsupported* in the OpenTok React Native library:

* **Custom audio drivers** -- An application using OpenTok React Native use the device microphone
to capture audio to transmit to a published stream. And it uses the device speakers (or headphones)
to play back audio from subscribed streams. However, you can set the `enableStereoOutput` property
of the OTSession object to enable stereo output.

* **Custom video capturers** -- (BaseVideoCapturer) -- The OpenTok React Native OTPublisher uses
the standard video capturer that uses video directly from the device's camera. However, you can set
the `videoSource` property of an OTPublisher component to "screen" to publish a screen-sharing stream.

* **Custom video renderers** -- The OTSubscriber and OTPublisher components implement a standard
video renderer that renders streams and provides user interface controls for displaying
the stream name and muting the microphone or camera. Publishers and subscribers use
  `mPublisher.setStyle(BaseVideoRenderer.STYLE_VIDEO_SCALE, BaseVideoRenderer.STYLE_VIDEO_FILL)`
  
* **iOS delegate callback queue** -- For iOS, you cannot assign the delegate callback queue (the
GCD queue). See the docs for the
[OTSession.apiQueue property](https://tokbox.com/developer/sdks/ios/reference/Classes/OTSession.html#//api/name/apiQueue)
in the OpenTok iOS SDK.

To build Android and iOS apps that use these features, use the
[OpenTok Android SDK](https://tokbox.com/developer/sdks/android/)
and the [OpenTok iOS SDK](https://tokbox.com/developer/sdks/ios/).

## More information

For full documentation on using OpenTok, see the [OpenTok developer center](https://tokbox.com/developer).

See the [opentok-react-native-samples](https://github.com/opentok/opentok-react-native-samples) repo.
