# ESP32-BluetoothClassicSerial
Establishes serial profile between ESP32 and Android app

# Preface
To clone the repo properly make sure to do the following:
```
git clone
git submodule update
git submodule init
```

# Running ESP32 code
1. Install the esp-idf, guide can be found here:https://docs.espressif.com/projects/esp-idf/en/latest/get-started/
make sure to install the prerequisites for your respective operating system
2. Run `idf.py` and ensure you get a list of commands, not errors

3. If on linux you will likely need to add your user to the dialout group so you can serially to ESP32
```
sudo usermod -a -G dialout $(whoami)
```
4. Enter the bt_echo directory and run idf.py flash to upload the code to ESP32
```
cd bt_echo
idf.py flash monitor
```

# Running BluetoohChat
1. From the android folder, move the apk file to your android phone and open it in your file browser
2. Install the app, android will try to warn you not to, but the app is safe
3. Within the app, tap on the bluetooth logo in the top right corner
4. Connect to the ESP32 server by default this is called "MerakiTheNextGeneration"
5. You should be able to send text to your esp and it will echo what you send back


# Notes:
Text you send to the esp is stored in a fixed size byte array, you will notice that some characters aren't cleared when echoed back, but this is not that big of an issue as long as you know the size of the response you expect, or the size of the response is included in the text in some way.
