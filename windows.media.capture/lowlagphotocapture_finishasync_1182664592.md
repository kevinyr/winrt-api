---
-api-id: M:Windows.Media.Capture.LowLagPhotoCapture.FinishAsync
-api-type: winrt method
---

<!-- Method syntax
public Windows.Foundation.IAsyncAction FinishAsync()
-->

# Windows.Media.Capture.LowLagPhotoCapture.FinishAsync

## -description
Asynchronously releases the [LowLagPhotoCapture](lowlagphotocapture.md) object and resources used by the capture photo operation.

## -returns
Object that is used to control the asynchronous operation.

## -remarks

## -examples
Here is an example that shows how to setup and take low lag photos. It displays the captured photo and thumbnail in [Image](XREF:TODO:wwa.Image_object) objects. The XAML creates a simple UI with a two [Image](XREF:TODO:wwa.Image_object) objects and some [Button](../windows.ui.xaml.controls/button.md) objects to interact with the [MediaCapture](mediacapture.md) element. In code, there is a method to initialize the [MediaCapture](mediacapture.md) object, a method to initialize the [LowLagPhotoCapture](lowlagphotocapture.md) object, a method to take the photo and display it, and a method to shutdown the [LowLagPhotoCapture](lowlagphotocapture.md).



[!code-xml[MediaCaptureLowLagXAML](../windows.media.capture/code/MediaCapture/csharp/MainPage.xaml#SnippetMediaCaptureLowLagXAML)]

[!code-csharp[MediaCaptureLowLagPhotoCaptureCode](../windows.media.capture/code/MediaCapture/csharp/MainPage.xaml.cs#SnippetMediaCaptureLowLagPhotoCaptureCode)]

## -see-also
