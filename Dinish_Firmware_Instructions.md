This board uses **Rust programming language** (not Arduino), which might be unfamiliar.

# Step-by-Step Firmware Setup

### **Step 1: Install Rust**
1. Go to https://rustup.rs
2. Follow the instructions for your operating system

### **Step 2: Install ESP Flash Tool**
In Terminal, run:
```bash
cargo install --locked espflash
```
This installs the tool to upload programs to your ESP32-C3 board.

### **Step 3: Get the Firmware Code**
1. Go to https://github.com/hakkaatachi (mentioned in your instructions)
2. Find and download/clone the "hakkaa-firmware" repository
3. Open Terminal and navigate to that folder:

## **Fix: Add your user to the dialout group**
On Linux, regular users can't access serial ports by default. You need permission:

### **Step 1: Add yourself to the dialout group**
```bash
sudo usermod -a -G dialout $USER
```

### **Step 2: Apply the changes**
```bash
newgrp dialout
```

### **Step 3: Verify it worked**
```bash
groups
```
You should see `dialout` in the list.

### **Step 4: Test Your Soldering!**
Connect your board via USB-C and run the test program.
This tests if all your LEDs, shake sensor, and button work!
```bash
cargo run --example eol-test
```

**If it doesn't connect:**
BUTTONS:
if you press the two buttons next in the esp32 under the usb
one of them wil make the green light stop to blink.
That one is RST. The other is BOOT.

1. Press and HOLD the **BOOT button** on your board
2. Press and release the **RST (reset) button**
3. Release the **BOOT button**
4. Try the command again
```bash
cargo run --example eol-test
```

## **Step 5: Run the POV Demo**
Once the test passes:
```bash
cargo run --bin pov
```
This should run the persistence-of-vision demo!

---

