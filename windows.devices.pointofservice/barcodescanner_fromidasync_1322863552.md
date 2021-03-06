---
-api-id: M:Windows.Devices.PointOfService.BarcodeScanner.FromIdAsync(System.String)
-api-type: winrt method
---

<!-- Method syntax
public Windows.Foundation.IAsyncOperation<Windows.Devices.PointOfService.BarcodeScanner> FromIdAsync(System.String deviceId)
-->

# Windows.Devices.PointOfService.BarcodeScanner.FromIdAsync

## -description
Creates [BarcodeScanner](barcodescanner.md) object from the [DeviceInformation.Id](../windows.devices.enumeration/deviceinformation_id.md).

## -parameters
### -param deviceId
The [DeviceInformation.Id](../windows.devices.enumeration/deviceinformation_id.md) that identifies a specific barcode scanner, which can be retrieved from the [DeviceId](barcodescanner_deviceid.md) property.

## -returns
The barcode scanner specified by the unique device identifier. Returns a null object in the following cases:
+ The specific device is not found.
+ Access denied to the existing device. The user can deny access to a device, which is not treated as an exception.


## -remarks

## -examples

## -see-also
[DeviceInformation.Id](../windows.devices.enumeration/deviceinformation_id.md)