---
-api-id: T:Windows.Storage.Streams.InputStreamOverStream
-api-type: winrt class
---

<!-- Class syntax.
public class InputStreamOverStream : Windows.Foundation.IClosable, Windows.Storage.Streams.IInputStream
-->

# Windows.Storage.Streams.InputStreamOverStream

## -description
Provides a Windows Runtime input stream for an [IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034.aspx) base implementation.

## -remarks
The [InputStreamOverStream](inputstreamoverstream.md), [OutputStreamOverStream](outputstreamoverstream.md), and [RandomAccessStreamOverStream](randomaccessstreamoverstream.md) classes are interop helpers to convert between the Windows Runtime stream types, which are natively asynchronous, and the Component Object Model (COM) [IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034.aspx) types, which are natively synchronous.

These helper classes make it easier for to reuse legacy code when you transition to the Windows Runtime stream types.

## -examples

## -see-also
[OutputStreamOverStream](outputstreamoverstream.md), [RandomAccessStreamOverStream](randomaccessstreamoverstream.md), [IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034.aspx)