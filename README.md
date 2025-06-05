# PlanToSim - Complete Flight Plan Transfer Solution

Transfer flight plans from popular Electronic Flight Bag (EFB) apps directly into X-Plane flight simulator GPS/FMS units. This complete solution includes both the **PlanToSim iOS app** and the **PlanToSim X-Plane plugin** to seamlessly move your flight plans from planning to simulation for Reality-XP GTN/GNS navigators, TDS GTN Xi navigators, and X-Plane FMS systems.

## System Overview

**PlanToSim** consists of two components that work together:

1. **PlanToSim (iOS App)** - Create, convert, and export flight plans from your iPhone/iPad
2. **PlanToSim (X-Plane Plugin)** - Receive flight plans and install them in your simulator

## Components

### PlanToSim (iOS App)

A comprehensive flight planning app that supports worldwide navigation data and multiple export formats.

#### Features:
- **Global Navigation Data** - Uses pre-processed FAA CIFP, NASR and OurAirports data
- **EFB Integration** - Import from ForeFlight, Garmin Pilot, and FlyQ
- **Basic Route Processing** - Handles airports, fixes, and airways (no SIDs/STARs/runways)
- **Multiple Export Formats** - Supports GTN (.gfp), GNS (.fpl XML), X-Plane FMS (.fms), and TDS (.gfp)
- **Configurable Destinations** - Toggle between GTN, GNS, X-Plane FMS, and TDS output formats
- **Network Transfer** - Send flight plans directly to X-Plane plugin via TCP
- **Airway Expansion** - Full airway support with automatic route expansion

#### Supported Export Formats:
- **GTN (.gfp)** - For Reality-XP GTN navigators  
- **GNS (.fpl XML)** - For Reality-XP GNS navigators
- **TDS (.gfp)** - For TDS GTN Xi navigators
- **X-Plane FMS (.fms)** - For X-Plane flight management systems

### PlanToSim (X-Plane Plugin)

A plugin for X-Plane 11/12 that receives flight plans from the PlanToSim iOS app and automatically saves them to the correct simulator directories.

#### Features:
- **TCP Server** - Listens on port 5000 for incoming flight plans from iOS app
- **Four Format Support** - Saves to GTN, GNS, TDS, and X-Plane FMS folders  
- **Configurable Paths** - Set custom folder paths for each GPS/FMS type
- **Automatic Directory Creation** - Creates necessary directories if they don't exist
- **Persistent Settings** - Configuration saved across X-Plane sessions

## Installation Guide

### Step 1: Install PlanToSim Plugin (X-Plane)

1. **Download the plugin**:
   - Download the latest PlanToSim plugin from the [Releases](../../releases) page
   - Extract the ZIP file

2. **Install the plugin**:
   - Close X-Plane if it's running
   - Copy the `PlanToSim` folder to your X-Plane plugins directory:
     ```
     X-Plane/Resources/plugins/PlanToSim/
     ```

3. **Configure the plugin**:
   - Start X-Plane
   - Go to **Plugins > PlanToSim**
   - The plugin comes with default folder paths for each GPS/FMS type:
     - **GTN Folder**: `C:\ProgramData\Garmin\Trainers\Databases\FPLN`
     - **GNS Folder**: `C:\ProgramData\Garmin\GNS Trainer Data\GNS\FPL`  
     - **TDS Folder**: `C:\ProgramData\TDS\GTNXi\FPL`
     - **X-Plane FMS Folder**: `[X-Plane Directory]\Output\FMS Plans`
   - **Only change these paths if you've installed your GPS/FMS software in a different location**
   - Use the plugin dropdown menu and file selector to set custom folder paths if needed

### Step 2: Install PlanToSim (iOS)

1. **Download from App Store**: [Link coming soon]
2. **Configure network settings**:
   - Open the app settings
   - Enter your X-Plane computer's IP address
   - The default port (5000) should work in most cases

## Usage Instructions

### Step 1: Import Flight Plan from EFB

Choose your Electronic Flight Bag (EFB) and follow the specific instructions:

#### ForeFlight
1. Open your flight plan in ForeFlight
2. At the bottom of the flight plan window, tap the **share icon** <img src="./share-ios.svg" width="16" height="16" style="display: inline; background-color: white; padding: 2px; border-radius: 3px; border: 1px solid #ccc;">
3. Select **"SHARE FPL FILE"**
4. Choose **"PlanToSim"** from the app list
5. After the plan is sent, you may return to ForeFlight

#### Garmin Pilot
1. Open your flight plan in Garmin Pilot
2. In the flight planning screen, tap the **share icon** <img src="./share-ios.svg" width="16" height="16" style="display: inline; background-color: white; padding: 2px; border-radius: 3px; border: 1px solid #ccc;"> at the bottom left
3. Select **"Print Navlog"**
4. Tap the **share icon** <img src="./share-ios.svg" width="16" height="16" style="display: inline; background-color: white; padding: 2px; border-radius: 3px; border: 1px solid #ccc;"> at the top right
5. Choose **"PlanToSim"** from the app list
6. After the plan is sent, you may return to Garmin Pilot

#### FlyQ+ EFB
1. Open your flight plan in FlyQ+ EFB
2. In the Plans section, tap the **share icon** <img src="./share-ios.svg" width="16" height="16" style="display: inline; background-color: white; padding: 2px; border-radius: 3px; border: 1px solid #ccc;"> at the top right
3. Select **"PRINT"**
4. Tap the **share icon** <img src="./share-ios.svg" width="16" height="16" style="display: inline; background-color: white; padding: 2px; border-radius: 3px; border: 1px solid #ccc;"> at the top
5. Choose **"PlanToSim"** from the app list
6. After the plan is sent, you may return to FlyQ+ EFB

### Step 2: Configure Export Destinations

In the PlanToSim app settings, toggle which flight plan formats you want to export:
- **GTN** - Reality-XP GTN navigators (.gfp files)
- **GNS** - Reality-XP GNS navigators (.fpl XML files)  
- **TDS** - TDS GTN Xi navigators (.gfp files)
- **X-Plane FMS** - X-Plane flight management systems (.fms files)

### Step 3: Export to X-Plane

- The app automatically processes and sends the flight plan
- Flight plans are sent to your X-Plane computer via TCP (port 5000)
- You'll see progress indicators for importing, converting, and exporting

### Step 4: Import Flight Plan in GPS Navigator

**After flight plans are sent to the appropriate folders, you must use your navigator's instructions to import the flight plans:**

#### For GNS Navigators (Reality-XP GNS 430/530)
1. Press **FPL** button
2. Use the **small knob** to scroll right to the import page
3. The import page will display available flight plans
4. The first plan should be highlighted; if not, press the **center button** to select and highlight
5. Use the **small knob** to scroll through available flight plans
6. Press **ENTER** to select your desired flight plan
7. Choose the flight plan slot number (use **small knob** to change if desired)
8. Press **ENTER** to import
9. Select **"DONE"** when complete and press **ENTER**
10. Use the **big knob** to scroll back to import more plans, or:
    - Press **center button** to unhighlight/deselect
    - Press **FPL** again to exit
    - Press **CLR** or **press and hold CLR** depending on your preference

#### For GTN Navigators (Reality-XP GTN 650/750)
1. Select **HOME**
2. Select **FLIGHT PLAN**
3. Press **MENU**
4. Select **CATALOG**
5. Press **MENU**
6. Select **IMPORT**
7. Choose your flight plan (flight plan names will show destination and departure)
8. You then have the option to **STORE** or **ACTIVATE** the flight plan

#### For TDS GTN Xi Navigators
1. Follow similar steps as GTN navigators above
2. Navigate to the flight plan catalog
3. Import your flight plan from the available list
4. Choose to store or activate as needed

#### For X-Plane FMS
1. Open your aircraft's flight management system
2. Navigate to the flight plan section
3. Load the flight plan from the FMS plans directory
4. Follow your specific aircraft's FMS procedures for activation

### Supported Aircraft and GPS Units

#### Reality-XP GTN Series
- GTN 650/750 touchscreen units
- Flight plans saved as `.gfp` files
- Supports full route with airways and procedures

#### TDS GTN Series
- TDS GTN 650Xi/750Xi navigators
- Flight plans saved as `.gfp` files
- Compatible with TDS GPS systems

#### Reality-XP GNS Series  
- GNS 430/530 units
- Flight plans saved as `.fpl` XML files
- Compatible with Reality-XP GNS trainers

#### X-Plane Flight Management Systems
- Native X-Plane FMS
- Saved as `.fms` files in X-Plane format
- Works with default X-Plane aircraft and most third-party aircraft

## Navigation Data Sources

PlanToSim uses pre-processed navigation data from public sources and OurAirports.

**Important:** This data is for simulation purposes only - do not use for navigation and may not be complete.

## Supported Import Sources

PlanToSim can import flight plans from:

- **ForeFlight**
- **Garmin Pilot** 
- **FlyQ**

**Current Processing Limitations:**
- Processes airports, fixes, and airways only
- Does not process runways, SIDs, or STARs
- Routes are converted to basic point-to-point with airway expansion

## Troubleshooting

### Connection Issues

**Flight plans not transferring**:
- Verify your X-Plane computer's IP address in the iOS app
- Check that port 5000 isn't blocked by your firewall
- Ensure both devices are on the same network

**Plugin not appearing in X-Plane**:
- Verify the plugin is in the correct directory
- Check X-Plane's Log.txt file for error messages

### Flight Plan Issues

**Flight plan not appearing in GPS**:
- Verify the folder paths are correctly configured in the X-Plane plugin
- Check X-Plane's Log.txt file for any error messages from the plugin
- Ensure your GPS/FMS software is looking in the correct folder for flight plans
- Some aircraft may use custom paths - check aircraft documentation

**Missing waypoints**:
- The app uses the most current navigation data available
- Some very recent changes may not be reflected immediately
- Custom or local waypoints may not be available

## Advanced Configuration

### Flight Plan Destination Toggles

Both the iOS app and X-Plane plugin allow you to control which flight plan formats are generated and received:

**In the iOS App:**
- Go to Settings within the app
- Toggle on/off the formats you want to export:
  - **GTN** - Reality-XP GTN navigators
  - **GNS** - Reality-XP GNS navigators  
  - **TDS** - TDS GTN Xi navigators
  - **X-Plane FMS** - X-Plane flight management systems

**In the X-Plane Plugin:**
- No toggles needed - the plugin receives and saves all formats sent by the app
- Simply configure the correct folder paths for each GPS/FMS type
- The app controls which formats are sent based on your iOS app settings

**Note:** The plugin will save any formats sent by the app to the configured folders.

### Custom Installation Paths

If you're using non-standard installations:

1. **GTN Custom Path**: Set via plugin menu "Select GTN Flight Plan Folder"
2. **GNS Custom Path**: Set via plugin menu "Select GNS Flight Plan Folder"  
3. **TDS Custom Path**: Set via plugin menu "Select TDS Flight Plan Folder"
4. **X-Plane FMS Custom Path**: Set via plugin menu "Select X-Plane FMS Flight Plan Folder"

### Network Configuration

- **Default Port**: 5000
- **Protocol**: TCP
- **Firewall**: Ensure port 5000 is open for incoming connections

## Downloads

### PlanToSim Plugin (X-Plane)
Download the latest version from the [Releases](../../releases) page.

### PlanToSim (iOS App)
[App Store link will be added here]

## Requirements

### X-Plane Plugin (PlanToSim)
- **X-Plane**: Version 11 or 12 (Windows only)
- **Operating System**: Windows (64-bit) - **Windows only**
- **Supported GPS**: Reality-XP GTN/GNS, TDS GTN Xi, X-Plane FMS

### iOS App (PlanToSim)  
- **iOS**: Version 13.0 or later
- **Device**: iPhone or iPad
- **Network**: WiFi connection to same network as X-Plane computer

## Support and Documentation

- **Updates**: Check releases page for latest versions
- **Documentation**: Complete setup and usage instructions provided below
- **Downloads**: Plugin and app downloads available in the releases section

## About This Repository

This repository serves as the official distribution point for PlanToSim components and provides comprehensive setup and usage instructions. 

**Repository Purpose:**
- Download location for the PlanToSim X-Plane plugin
- Complete installation and configuration instructions
- Usage guides and troubleshooting information
- Version release information

## License

This software is provided as-is. Use at your own risk.

---

*Transform your flight planning workflow with seamless EFB-to-simulator integration.*
