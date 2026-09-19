# Smart India Hackathon Workshop

# Date: 19-09-2026

## Register Number: 212224220081

## Name: RITHIKA M

## Problem Title

**SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations**

## Problem Description

Railway stations are often large and complex environments containing multiple platforms, ticket counters, waiting halls, food courts, restrooms, lifts, escalators, foot overbridges, entrances, exits, parking areas and other passenger facilities.

Passengers who are unfamiliar with a station may find it difficult to identify the location of a required facility or reach the correct platform efficiently. The problem becomes more challenging when certain corridors become crowded, facilities are temporarily unavailable, or passengers need an alternative route.

A navigation system for railway stations should therefore provide clear indoor directions while also considering the current condition of different station zones.

## Problem Creator's Organization

Ministry of Railway

## Idea

### StationFlow – Smart Crowd-Aware Railway Station Navigation

StationFlow is a smart indoor navigation system designed to help passengers locate railway station facilities and reach their destinations efficiently.

Instead of providing only a fixed shortest route, StationFlow represents the railway station as a collection of connected zones and continuously considers the condition of those zones.

The system combines:

- Interactive railway station maps
- Facility search
- Zone-based navigation
- Crowd-aware routing
- Accessibility-aware paths
- Indoor location anchors
- Dynamic route updates
- Voice and visual navigation
- Railway staff monitoring
- Digital kiosk support

The main objective is to improve passenger movement inside railway stations while reducing unnecessary movement through crowded or temporarily restricted areas.

---

# Proposed Solution / Architecture Diagram

### Proposed Solution Architecture Diagram

> **[Insert Proposed Solution Architecture Diagram Here]**

StationFlow consists of five major layers:

### 1. Passenger Interface

Passengers can access StationFlow through a mobile or web application.

The passenger can:

- Search for a facility
- Select a platform
- View the station map
- Check nearby facilities
- Start navigation
- Receive route instructions
- View crowd conditions
- Receive alternative routes

### 2. Station Mapping Layer

The railway station is represented as a digital indoor map.

Important locations are represented as nodes such as:

- Entrances
- Exits
- Platforms
- Ticket counters
- Waiting halls
- Restrooms
- Food courts
- Lifts
- Escalators
- Stairs
- Foot overbridges
- Information counters
- Medical facilities
- Parking areas

Navigation paths between these locations form the station navigation graph.

```text
G = (V, E)

V = Station locations / navigation nodes
E = Walkable connections between nodes
```

### 3. Station Zone Monitoring

The station is divided into logical zones.

Each zone can maintain information such as:

- Crowd level
- Path availability
- Facility availability
- Accessibility
- Temporary restrictions
- Estimated walking time

Example:

```text
Zone A → Entrance → Low Crowd
Zone B → Ticketing → Medium Crowd
Zone C → Foot Overbridge → High Crowd
Zone D → Platform Area → Normal
```

### 4. Navigation Engine

The navigation engine calculates a suitable route between the passenger's current location and destination.

The route considers:

- Distance
- Walking time
- Crowd level
- Accessibility
- Path availability
- Facility status

The route cost can be represented as:

```text
Route Cost =
α × Distance
+ β × Walking Time
+ γ × Crowd Level
+ δ × Accessibility Penalty
+ ε × Restriction Penalty
```

The system can therefore choose an alternative route when the normal path becomes crowded or unavailable.

### 5. Railway Administration Dashboard

Railway staff can monitor and update:

- Station zones
- Facility status
- Lift and escalator availability
- Temporary closures
- Crowd conditions
- Navigation anchors
- Station information

These updates can be reflected in passenger navigation.

---

# Navigation Workflow Diagram

### Passenger Navigation Workflow

> **[Insert Navigation Workflow Diagram Here]**

```text
Passenger Opens StationFlow
            ↓
Select Station
            ↓
Identify Current Location
            ↓
Search Destination / Facility
            ↓
Check Station Zone Conditions
            ↓
Navigation Engine Calculates Route
            ↓
Display Route on Station Map
            ↓
Passenger Starts Navigation
            ↓
Monitor Route Conditions
            ↓
Condition Changed?
       ↙            ↘
     YES             NO
      ↓               ↓
Recalculate        Continue
Route              Navigation
      ↓
Alternative Route
      ↓
Destination Reached
```

---

# Dynamic Rerouting Diagram

### Crowd-Aware Dynamic Rerouting

> **[Insert Dynamic Rerouting Diagram Here]**

StationFlow continuously considers the status of the route.

For example:

```text
Passenger
    ↓
Entrance
    ↓
Corridor A
    ↓
Foot Overbridge
    ↓
Platform 3
```

If Corridor A becomes highly crowded:

```text
Passenger
    ↓
Entrance
    ↓
Corridor A
    ↓
[HIGH CROWD DETECTED]
          ↓
Navigation Engine
          ↓
Alternative Route
          ↓
Corridor B
          ↓
Foot Overbridge
          ↓
Platform 3
```

This allows the system to provide an alternate route rather than forcing the passenger to continue through a congested area.

---

# Facility Discovery

StationFlow allows passengers to search for facilities available inside the station.

Examples include:

- Restrooms
- Food courts
- Drinking water
- Ticket counters
- Reservation counters
- Waiting halls
- Medical facilities
- Lifts
- Escalators
- ATMs
- Parking areas
- Information counters

Example:

```text
Passenger Search
       ↓
"Restroom"
       ↓
Find Nearby Facilities
       ↓
Check Availability
       ↓
Display Locations
       ↓
Select Facility
       ↓
Generate Route
```

The system can also display nearby facilities on the interactive station map.

---

# Indoor Positioning

GPS-based positioning can become unreliable inside large railway stations.

StationFlow therefore uses station-specific navigation anchors.

Possible anchor locations include:

- Station entrances
- Platform entrances
- Major junctions
- Foot overbridges
- Staircases
- Lift areas
- Waiting halls
- Information counters

A QR or visual anchor can be used to establish the passenger's approximate starting point.

Future versions can incorporate:

- BLE beacons
- UWB
- Computer vision
- Sensor-based positioning

---

# Accessibility Support

StationFlow can provide accessible navigation for passengers who require routes with fewer physical obstacles.

The system can identify:

- Accessible entrances
- Ramps
- Lifts
- Accessible footbridges
- Step-free corridors

For example:

```text
Normal Route:

Entrance
   ↓
Stairs
   ↓
Foot Overbridge
   ↓
Platform


Accessible Route:

Entrance
   ↓
Lift
   ↓
Accessible Corridor
   ↓
Foot Overbridge
   ↓
Platform
```

Accessibility constraints can be incorporated into route calculation.

---

# Voice and Visual Guidance

StationFlow can provide simple navigation instructions using both visual and voice-based guidance.

Example:

```text
"Continue straight for 40 metres."

"Turn left at the information counter."

"Take the lift to reach the foot overbridge."

"Platform 4 is ahead."
```

Landmarks are used in instructions wherever possible so passengers can understand their surroundings more easily.

---

# Digital Kiosk Support

StationFlow can also be deployed through interactive kiosks installed inside railway stations.

A passenger can:

1. Select the destination.
2. View the station map.
3. Select a preferred route.
4. Scan a QR code.
5. Continue navigation using a mobile device.

### Kiosk-to-Mobile Flow

```text
Passenger
    ↓
Station Kiosk
    ↓
Select Destination
    ↓
Generate Route
    ↓
Display QR Code
    ↓
Passenger Scans QR
    ↓
Route Transferred to Mobile
    ↓
Continue Navigation
```

This allows passengers without prior access to the application to start navigation from a station kiosk.

---

# Railway Administration Dashboard

The administration dashboard provides railway staff with a centralized interface to manage station navigation information.

Administrators can:

- Add or update facilities
- Modify station paths
- Update zone conditions
- Mark facilities as unavailable
- Update lift/escalator status
- Add navigation anchors
- Mark temporary restrictions
- Monitor crowd conditions

Example:

```text
Station Administration Dashboard

Station: Central Railway Station

Zone A → Normal
Zone B → Medium Crowd
Zone C → High Crowd

Lift 1 → Operational
Lift 2 → Under Maintenance

Platform 1 → Open
Platform 2 → Open
Platform 3 → Temporary Restriction
```

---

# Use Cases

### Passenger

- Search for Facilities
- Search for Platform
- View Station Map
- Identify Current Location
- Start Navigation
- View Crowd Conditions
- Receive Route Instructions
- Receive Alternative Routes
- Find Accessible Facilities

### Railway Administrator

- Manage Station Map
- Manage Facilities
- Update Facility Status
- Update Crowd Conditions
- Manage Navigation Anchors
- Manage Temporary Restrictions
- Monitor Station Zones

### Kiosk User

- Select Destination
- View Station Map
- Generate Route
- Scan QR Code
- Transfer Route to Mobile

---

# Use Case Diagram

### StationFlow Use Cases

> **[Insert Use Case Diagram Here]**

```text
                    +--------------------------------+
                    |          StationFlow           |
                    |                                |
Passenger ----------|--> Search Facility             |
                    |--> Search Platform             |
                    |--> View Station Map             |
                    |--> Start Navigation             |
                    |--> Receive Guidance             |
                    |--> View Crowd Conditions        |
                    |--> Request Alternative Route   |
                    |                                |
Administrator ------|--> Manage Facilities           |
                    |--> Update Zone Conditions       |
                    |--> Update Path Status           |
                    |--> Manage Station Map           |
                    |--> Manage Anchors               |
                    |                                |
Kiosk User ---------|--> Select Destination          |
                    |--> Generate Route              |
                    |--> Scan QR Code                |
                    +--------------------------------+
```

---

# System Workflow Diagram

### Complete System Workflow

> **[Insert System Workflow Diagram Here]**

```text
Passenger / Kiosk
        ↓
User Request
        ↓
StationFlow Interface
        ↓
Backend API
        ↓
Station Database
        ↓
Station Map + Zone Data
        ↓
Navigation Engine
        ↓
Route Calculation
        ↓
Crowd / Facility Conditions
        ↓
Final Route
        ↓
Passenger Navigation
        ↓
Continuous Condition Monitoring
        ↓
Dynamic Rerouting if Required
```

---

# Technology Stack

### Frontend

- React.js
- JavaScript
- HTML5
- CSS3
- Leaflet / Interactive Map Library

### Backend

- Python
- FastAPI
- REST APIs
- WebSockets

### Navigation

- Graph-based Navigation
- Weighted Shortest Path Algorithm
- Dynamic Rerouting
- Accessibility Constraints

### Database

- PostgreSQL
- PostGIS

### Real-Time Services

- Redis
- WebSockets

### Navigation Assistance

- QR Codes
- Visual Station Anchors
- Web Speech API
- Text-to-Speech

### Deployment

- Docker
- Cloud Hosting

---

# Dependencies

The proposed system may require the following dependencies:

```text
Frontend:
- React
- React Router
- Leaflet
- Axios

Backend:
- Python
- FastAPI
- Uvicorn
- Pydantic

Database:
- PostgreSQL
- PostGIS

Real-Time:
- Redis
- WebSockets

Navigation:
- Graph algorithms
- Spatial data processing

Additional:
- QR Code generation and scanning
- Web Speech API
```

---

# Innovation

The main innovation of StationFlow is the combination of **indoor navigation and station-zone condition awareness**.

Traditional navigation systems primarily focus on finding a shortest path.

StationFlow additionally considers the current condition of the station.

```text
Traditional Navigation

Current Location
       ↓
Destination
       ↓
Shortest Path
```

```text
StationFlow

Current Location
       ↓
Destination
       ↓
Station Map
       ↓
Zone Conditions
       ↓
Crowd Level
       ↓
Facility Status
       ↓
Accessibility
       ↓
Path Availability
       ↓
Suitable Route
```

This allows the navigation system to respond to changing station conditions.

---

# Advantages

- Provides indoor station navigation
- Helps passengers locate facilities quickly
- Reduces dependence on static directions
- Considers crowded areas during navigation
- Supports accessible routes
- Provides alternative routes
- Supports mobile and kiosk interfaces
- Allows railway staff to update station information
- Supports real-time navigation updates
- Can be extended to large railway stations

---

# Example Scenario

Consider a passenger arriving at a large railway station.

The passenger wants to reach **Platform 5**.

StationFlow identifies the passenger's starting point and calculates a route.

Initially:

```text
Entrance
   ↓
Main Corridor
   ↓
Foot Overbridge
   ↓
Platform 5
```

Later, the main corridor becomes highly crowded.

StationFlow receives the updated zone condition and recalculates the route:

```text
Entrance
   ↓
Alternate Corridor
   ↓
Lift
   ↓
Foot Overbridge
   ↓
Platform 5
```

The passenger receives an updated route without manually searching again.

---

# Future Scope

Future versions of StationFlow can include:

- BLE-based indoor positioning
- UWB-based positioning
- Computer vision
- Multi-floor navigation
- Multilingual voice guidance
- AI-based crowd prediction
- Real-time train and platform information
- Emergency evacuation routing
- Hazard-aware navigation
- Railway mobile application integration
- Smart accessibility monitoring
- Integration with railway station IoT systems
- Personalized notification services

---

# Conclusion

StationFlow proposes a smart indoor navigation framework for railway stations that combines facility discovery, interactive station mapping, crowd-aware routing, accessibility support and dynamic route updates.

By representing the railway station as connected navigation zones and continuously considering station conditions, the system can provide passengers with clearer and more practical navigation inside complex railway environments.

The proposed system can be extended in the future with advanced indoor positioning technologies, real-time railway data and intelligent crowd prediction.

---

## Project Summary

**Project Name:** StationFlow

**Problem Statement:** SIH 1710 – Enhancing Navigation for Railway Station Facilities and Locations

**Organization:** Ministry of Railway

**Core Concept:** Crowd-Aware Indoor Railway Station Navigation

**Primary Users:**
- Railway Passengers
- Railway Administrators
- Kiosk Users

**Key Technologies:**
- React.js
- FastAPI
- PostgreSQL/PostGIS
- Redis
- WebSockets
- Graph-Based Navigation
- QR/Visual Anchors
- Web Speech API
