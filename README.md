# AR Datacenter

This program recognizes racks and devices within a rack which are marked with ficudical markers. By usign the link encoded in a QR Code it will get additional data from a netbox database. The program will load images which will be laid over the stream. These images are an overley into which information about the individual interfaces can be written and graphs can be shown.

For this to happen we need multiple functionalities:
 - QR Code Recognition
 - Pose Estimation with Ficudical Markers
 - Image Overlay
    - Graphs
    - Text
- Netbox API
    - Get Device Information
    - Get Interface Information
    - Get Graphs
- Stream from Camera

Steps: 
1. Calibrate Camera
1. Read Camera Stream and Display it
2. Read Fiducial Markers and Display them
3. Estimate the Pose of Device on which the Fiducial Markers are
5. Recognize and Read QR Code, estimate which device it belongs to
6. Get Information about Device from Netbox
7. Display Information on Overlay

