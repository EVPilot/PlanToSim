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
   - Set folder paths for each GPS/FMS type:
     - **GTN Folder**: Usually `C:\ProgramData\Garmin\Trainers\Databases\FPLN`
     - **GNS Folder**: Usually `C:\ProgramData\Garmin\GNS Trainer Data\GNS\FPL`  
     - **TDS Folder**: Usually `C:\ProgramData\TDS\GTNXi\FPL`
     - **X-Plane FMS Folder**: Usually `[X-Plane Directory]\Output\FMS Plans`

### Step 2: Install PlanToSim (iOS)

1. **Download from App Store**: [Link coming soon]
2. **Configure network settings**:
   - Open the app settings
   - Enter your X-Plane computer's IP address
   - The default port (5000) should work in most cases

## Usage Instructions

### Creating and Sending Flight Plans

1. **Import flight plan** in the PlanToSim iOS app:
   - Import from **ForeFlight**, **Garmin Pilot**, or **FlyQ**
   - The app will automatically process and display the extracted route

2. **Configure output destinations**:
   - In the app settings, toggle which flight plan formats you want to export:
     - **GTN** - Reality-XP GTN navigators (.gfp files)
     - **GNS** - Reality-XP GNS navigators (.fpl XML files)  
     - **TDS** - TDS GTN Xi navigators (.gfp files)
     - **X-Plane FMS** - X-Plane flight management systems (.fms files)

3. **Export to X-Plane**:
   - The app automatically processes and sends the flight plan
   - Flight plans are sent to your X-Plane computer via TCP (port 5000)
   - You'll see progress indicators for importing, converting, and exporting

4. **Confirm in X-Plane**:
   - Check X-Plane's Log.txt file for confirmation messages
   - Open your aircraft's GPS unit
   - Load the newly received flight plan from the appropriate folder

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
