# LoRaCrowdsensing
IIITD IP Winter 2024

<h1> <u>Bharat Pi Programming : </u> </h1>
<ol><h2>Steps to follow to run the code and upload on Bharat Pi: </h2>

1. First, Install the Arduino IDE from Audrino's official site (Arduino IDE 2.3.2 used in this project).
2. After installing Arduino IDE, go to Boards Manager, which appears on the left sidebar; search for esp32 Espressif and install it.
3. Then, go to Library Manager, appear on the left sidebar, search for Lora Sandeep Mistry, and install it. (make sure you install the latest version available)
4. Now, Go to Tools, select Board -> esp32 -> ESP32-WROOM-DA-Module, and select which USB port you want to program. If no port is showing when Bharat Pi is connected to the USB port, then you need to install a 
   USB driver using the links given below.
  <ul><p> https://wch-ic.com/downloads/CH341SER_ZIP.html (For Windows)</p></ul>
   <ul><p>https://wch-ic.com/downloads/CH341SER_MAC_ZIP.html (For Mac)</p></ul> 
v. Finally, write the code in C language in IDE and upload the code to Bharat pi using the -> symbol on top.
</ol>
Note: To see the output that you are printing  using the command " Serial.print("") ". Go under tools -> Serial Monitor and then set the correct baud rate of the serial monitor that you set in your code. (In this project,  115200 baud rate is used)


<ul><h2>Libraries Used in this Project :</h2>

<h3>1. SPI.h:   (esp32) </h3>

SPI.h library is a synchronous serial communication interface for short-distance communication primarily between microcontrollers (esp32 in our project) and peripheral devices (Our PC from which we are uploading code) like sensors, displays, and memory chips.

<h3>2. LoRa.h:  (Lora Sandeep Mistry) </h3>

The LoRa.h library provides functions that work with LoRa modules or chips. It allows you to configure LoRa parameters, send and receive LoRa packets, and manage LoRa networks using Bharat Pi board.

<h3>3. BluetoothSerial.h:  (Inbuilt library in Arduino IDE) </h3>

The BluetoothSerial.h library provides functions to communicate via Bluetooth serial protocol. It allows a Bharat Pi board to establish a Bluetooth connection and send/receive data wirelessly to/from other Bluetooth-enabled devices.
</ul>
<ul><h2>Software Used in this Project:</h2>

<h4>1. Arduino IDE (Version 2.3.2)</h4>
</ul>
<ul><h2>Hardware Used in this Project:</h2>

<h4>1. Bharat Pi LoRa Module with ESP32, LoRa RFM95W 868MHZ lora Long range transreceiver module chip with ESP32 WROOM </h4>
</ul>

![image](https://github.com/shamikdesarkar/LoRaCrowdsensing/assets/108173950/25710f7e-491b-40f3-b753-8fe6c18f6c70)

# CrowdSense

## Introduction
**App Name:** CrowdSense

**Purpose:** CrowdSense provides the current latitude and longitude of the user and displays a list of paired Bluetooth devices, allowing users to connect with these devices easily and send data to the app, which is then sent to the server.

## Getting Started

### System Requirements
- **Operating System:** Android 10.0 or later
- **Hardware:** GPS-enabled device, Bluetooth 4.0 or later
- **Permissions:** Location access, Bluetooth access

### Installation
1. **Android:** Open Google Play Store, search for "CrowdSense", and tap "Install".

### Setup
1. Open CrowdSense after installation.
2. Tap on the Transmitter or Receiver button depending on if you have a transmitter or receiver device with the phone.
3. Tap on start location tracking and grant location access when prompted.
4. Then tap on the activate button and enable the Bluetooth activation prompt if it’s not already on.
5. Tap on the devices to get the list of paired devices in the spinner beside the devices button.
6. Connect to your device from the list of devices and press the connect button to receive data from that device.

## Features

### 3.1 Location Services
- **Accessing Location:** CrowdSense uses the device’s GPS to provide accurate latitude and longitude coordinates. Ensure that your device’s location services are enabled.
- **Displaying Coordinates:** Your coordinates are displayed in the middle of the activity screen. Users also get a notification of the current coordinates every second.

### 3.2 Connecting to Devices

#### Troubleshooting Connection Issues
- **If the connection fails:**
  - Ensure the device is powered on and within range.
  - Restart your device’s Bluetooth.
  - Try restarting the paired device.
  - Check for any device-specific troubleshooting steps in the device manual.

## FAQs

### What to do if the app can't find my location?
- Ensure GPS is enabled.
- Check if the app has location permissions.
- Restart the app and your device.

### How can I add a new device to the paired list?
- Pair the device through your phone’s Bluetooth settings first, then it will appear in the app.

### Why does the app need Bluetooth and location permissions?
- Bluetooth is needed to detect and connect to devices, and location services are required for accessing accurate GPS coordinates.

## Troubleshooting

### Problem: Can't connect to a paired device.
- Make sure the device is within range and turned on.
- Restart Bluetooth on your device.
- Try reconnecting through your phone’s Bluetooth settings first.

### Contact Support
- If you encounter issues not covered here, contact us at support@crowdsense.com.

## Technical Details (for developers)

### Bluetooth APIs
- **BluetoothAdapter:** Represents the local Bluetooth adapter (Bluetooth radio).
- **BluetoothDevice:** Represents a remote Bluetooth device.
- **BluetoothManager:** Manages all aspects of Bluetooth connectivity.
- **BluetoothSocket:** Represents the interface for a Bluetooth socket (connection).

### Notification APIs
- **Notification:** Represents a notification that can be shown to the user.
- **NotificationChannel:** Required for creating notification channels on Android 8.0 (API level 26) and above.

### Service API
- **Service:** A component that can perform long-running operations in the background.

### Location APIs
- **Location:** Represents a geographical location.
- **FusedLocationProviderClient:** The main entry point for interacting with the fused location provider.
- **LocationAvailability:** Represents the availability of location data.
- **LocationCallback:** Used for receiving notifications from the FusedLocationProviderClient.
- **LocationRequest:** Used to request location updates.
- **LocationResult:** Represents a location result from the fused location provider.
- **LocationServices:** Entry point for location services integration.

### Third-Party Libraries
- **EventBus (from GreenRobot):** A publish/subscribe event bus optimized for Android. It simplifies communication between components such as activities, fragments, and background threads.

### Coroutines
- **CoroutineScope:** Defines a scope for new coroutines.
- **Dispatchers:** Provides various dispatchers to run coroutines on different threads.
- **launch:** Launches a new coroutine without blocking the current thread.

### Data Handling
- CrowdSense sends data of GPS and received from other devices via Bluetooth to the server.

  
# Backend part to connect the android devices and Server

## Local Setup for Android and Django Integration

### Prerequisites

1. **Django Server**: Ensure your Django server is set up and running.
2. **Android Device and Emulator**: Ensure your Android devices/emulators are connected to the same local network.

### Network Configuration

To ensure that your Android device can communicate with your Django server, follow these steps:

1. **Switch Off the Firewall**:
    - Temporarily switch off the firewall on your system to allow connections. This can usually be done through your system's security settings.

2. **Find the IP Address**:
    - Find the IP address of your PC on the local network. This is typically the IP address assigned by your WiFi network. On Windows, you can find this by running `ipconfig` in the Command Prompt and looking for the "IPv4 Address" under your active network connection.

### Step-by-Step Guide

#### Django Setup

1. **Install Django**:
    - Ensure Django is installed in your environment. If not, install it using pip:
      ```sh
      pip install django djangorestframework
      ```

2. **Create a Django Project and App**:
    - Create a new Django project and app:
      ```sh
      django-admin startproject myproject
      cd myproject
      python manage.py startapp locationapp
      ```

3. **Define the Model**:
    - Define your model in `locationapp/models.py`:
      ```python
      from django.db import models

      class Location(models.Model):
          longitude = models.CharField(max_length=100)
          latitude = models.CharField(max_length=100)
          rssi = models.CharField(max_length=100, default="00")
          mode = models.CharField(max_length=100, default="0")
          timed = models.CharField(max_length=100, default="0")
          identity = models.CharField(max_length=100, default="0")
          message = models.CharField(max_length=100, default="0")

          def __str__(self):
              return f"{self.latitude}, {self.longitude} - {self.identity}"
      ```

4. **Create a Serializer**:
    - Create a serializer for your model in `locationapp/serializers.py`:
      ```python
      from rest_framework import serializers
      from .models import Location

      class LocationSerializer(serializers.ModelSerializer):
          class Meta:
              model = Location
              fields = '__all__'
      ```

5. **Create a View**:
    - Create a view to handle incoming data in `locationapp/views.py`:
      ```python
      from rest_framework import status
      from rest_framework.decorators import api_view
      from rest_framework.response import Response
      from .models import Location
      from .serializers import LocationSerializer

      @api_view(['POST'])
      def add_location(request):
          if request.method == 'POST':
              serializer = LocationSerializer(data=request.data)
              if serializer.is_valid():
                  serializer.save()
                  return Response(serializer.data, status=status.HTTP_201_CREATED)
              return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)
      ```

6. **Configure URLs**:
    - Add the view to your URLs in `locationapp/urls.py`:
      ```python
      from django.urls import path
      from . import views

      urlpatterns = [
          path('add_location/', views.add_location, name='add_location'),
      ]
      ```

    - Include the app URLs in your project `urls.py`:
      ```python
      from django.contrib import admin
      from django.urls import path, include

      urlpatterns = [
          path('admin/', admin.site.urls),
          path('api/', include('locationapp.urls')),
      ]
      ```

7. **Run the Server**:
    - Start your Django server to listen on all IP addresses using the following command:
      ```sh
      python manage.py runserver 0.0.0.0:8000
      ```

#### Android Setup

1. **Android Studio Setup**:
    - Make sure your Android project is set up to use Retrofit for network operations.

2. **Initialize Retrofit in Android**:
    - In your Android project, initialize Retrofit with the base URL pointing to your local Django server. Replace `192.168.1.20` with your PC's IP address. For example:
      ```kotlin
      private val serverURL = "http://192.168.1.20:8000/"
      
      private lateinit var locationApi: LocationApi
      
      // Initialize Retrofit
      val retrofit = Retrofit.Builder()
          .baseUrl(serverURL)
          .addConverterFactory(GsonConverterFactory.create())
          .build()
      
      locationApi = retrofit.create(LocationApi::class.java)
      ```

3. **Convert and Parse the Incoming Message**:
    - Convert the `lastMessage` into individual components such as `message`, `rssi`, `mode`, and `identity`. Here is the code snippet:
      ```kotlin
      val messageList = lastMessage?.split(",")?.map { it.trim() }
      var message: String? = null
      var rssi: String? = null
      var mode: String? = null
      var identity: String? = null
      
      if (messageList?.size == 4) {
          message = messageList[0]
          rssi = messageList[1].substringAfter(": ").trim()
          mode = messageList[2].substringAfter(": ").trim()
          identity = messageList[3].substringAfter(": ").trim()
      }
      ```

4. **Add Time and Location Information**:
    - Add the current time and location data of the phone:
      ```kotlin
      val currentDateTime = LocalDateTime.now()
      val formattedDateTime = currentDateTime.format(DateTimeFormatter.ISO_DATE_TIME)

      val latitudeString = "Your Latitude"
      val longitudeString = "Your Longitude"
      ```

5. **Create and Send the Data Object**:
    - Create an object of the data class `LocationEvent1` and send it to the server using Retrofit:
      ```kotlin
      if (latitudeString != null && longitudeString != null && rssi != null && mode != null && identity != null && message != null) {
          val locationEvent1 = LocationEvent1(
              longitude = longitudeString,
              latitude = latitudeString,
              rssi = rssi,
              mode = mode,
              time = formattedDateTime,
              identity = identity,
              message = message
          )

          // Log the data
          Log.d("LocationEvent1", locationEvent1.toString())

          // Post the data to the server
          locationApi.addCred(locationEvent1).enqueue(object : Callback<ResponseBody> {
              override fun onResponse(call: Call<ResponseBody>, response: Response<ResponseBody>) {
                  if (response.isSuccessful) {
                      if (response.code() == 200) {
                          showToast("Data posted successfully")
                          Log.d("Server", "Data posted successfully")
                      } else if (response.code() == 201) {
                          showToast("Data already exists")
                          Log.d("Server", "Data already exists")
                      }
                  } else {
                      showToast("Request failed: ${response.code()}")
                      Log.e("Server", "Request failed: ${response.code()}")
                  }
              }

              override fun onFailure(call: Call<ResponseBody>, t: Throwable) {
                  Log.e("Server", "Failed to connect to the server", t)
                  showToast("Failed to connect to the server")
              }
          })
      }
      ```

### How It Works
![Lora Transmitter](https://github.com/shamikdesarkar/LoRaCrowdsensing/assets/108173950/6119fb7d-415d-428e-8a55-69b3ab371621)

1. **Initialization**: Retrofit is initialized with the base URL of the Django server.
2. **Message Parsing**: The incoming message is split and parsed into its components.
3. **Add Metadata**: Current time and location data are added to the message.
4. **Create Data Object**: An object of `LocationEvent1` is created with all necessary data.
5. **Send Data**: This data object is sent to the Django server using Retrofit's API call.
6. **Django Server**: The Django server, using Django REST Framework serialization, processes the incoming data and stores it in the database.
7. **Admin Panel**: You can view the stored data in the Django admin panel.

This process ensures seamless data transfer from your Android application to the Django backend, facilitating real-time data synchronization and monitoring.


