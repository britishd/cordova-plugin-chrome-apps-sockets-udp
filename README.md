# chrome.sockets.tcp Plugin

This plugin provides UDP sockets for Android and iOS.

## Status

Beta on Android and iOS.

## Reference

The API reference is [here](https://developer.chrome.com/apps/sockets_udp).

## Configuration

You can set next parameters for Sockets:

persistent { boolean	(optional) } - Flag indicating if the socket is left open when the event page of the application is unloaded (see Manage App Lifecycle). The default value is "false." When the application is loaded, any sockets previously opened with persistent=true can be fetched with getSockets.

name { string (optional) } - An application-defined string associated with the socket.

bufferSize { integer	(optional) } - The size of the buffer used to receive data. If the buffer is too small to receive the UDP packet, data is lost. The default value is 4096.

### Work only for IOS devices!

disableIPv4 { boolean (optional) } - Flag indicating if the socket should disable IPv4 protocol

disableIPv6 { boolean (optional) } - Flag indicating if the socket should disable IPv6 protocol

preferIPv { number (optional) } - Can be **4** or **6** depend on protocol that you prefer.

By default, both IPv4 and IPv6 are enabled.
This means GCDAsyncUdpSocket automatically supports both protocols, and can send to IPv4 or IPv6 addresses, as well as receive over IPv4 and IPv6.
 For operations that require DNS resolution, GCDAsyncUdpSocket supports both IPv4 and IPv6.
 * If a DNS lookup returns only IPv4 results, GCDAsyncUdpSocket will automatically use IPv4.
 * If a DNS lookup returns only IPv6 results, GCDAsyncUdpSocket will automatically use IPv6.
 * If a DNS lookup returns both IPv4 and IPv6 results, then the protocol used depends on the configured preference.
 * If IPv4 is preferred, then IPv4 is used.
 * If IPv6 is preferred, then IPv6 is used.
 * If neutral, then the first IP version in the resolved array will be used.
 
 Starting with Mac OS X 10.7 Lion and iOS 5, the default IP preference is neutral.
 On prior systems the default IP preference is IPv4.
