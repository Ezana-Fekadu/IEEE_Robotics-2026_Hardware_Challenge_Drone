# IEEE Robotics 2026 - Hardware Challenge: Autonomous Drone

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/Ezana-Fekadu/IEEE_Robotics-2026_Hardware_Challenge_Drone/blob/main/LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/Ezana-Fekadu/IEEE_Robotics-2026_Hardware_Challenge_Drone)](https://github.com/Ezana-Fekadu/IEEE_Robotics-2026_Hardware_Challenge_Drone/issues)

## Overview

This repository contains the complete design, firmware, and documentation for the IEEE Robotics 2026 Hardware Challenge autonomous drone project. Our goal is to develop a robust, efficient quadcopter capable of autonomous flight with sensor integration, failsafe mechanisms, and real-time telemetry.

## Project Status

**Current Phase:** Architecture & Sensor Integration  
**Last Updated:** February 2026  
**Team Lead:** [Team Member Name]  

## Quick Start

### Prerequisites
- Git
- Python 3.8+
- ARM GCC Toolchain (for firmware compilation)
- PlatformIO or equivalent embedded IDE

### Setup

```bash
# Clone the repository
git clone https://github.com/Ezana-Fekadu/IEEE_Robotics-2026_Hardware_Challenge_Drone.git
cd IEEE_Robotics-2026_Hardware_Challenge_Drone

# Set up your local environment
cp .env.example .env  # Configure if applicable

# Create a feature branch for your work
git checkout -b feature/<your-feature-name>
```

For detailed setup instructions, see [docs/SETUP.md](docs/SETUP.md) (coming soon).

## Repository Structure

```
.
├── firmware/              # Flight controller code (C/C++ for MCU)
│   ├── src/              # Main firmware source
│   ├── drivers/          # Sensor drivers (IMU, barometer, GPS, etc.)
│   └── control/          # Flight control algorithms (PID, mixing)
│
├── hardware/             # PCB design, schematics, CAD models
│   ├── schematics/       # KiCAD or Eagle schematics
│   ├── pcb/              # PCB layouts
│   ├── cad/              # 3D frame designs (FreeCAD, STEP files)
│   └── bom/              # Bill of Materials & vendor links
│
├── src/                  # High-level utilities & ground station tools
│   ├── ground_station/   # Ground control station (Python)
│   ├── telemetry/        # Telemetry processing & logging
│   └── utils/            # General utilities
│
├── tests/                # Unit & integration tests
│   ├── unit/             # Sensor driver tests
│   ├── hil/              # Hardware-in-the-loop tests
│   └── bench/            # Bench testing scripts
│
├── sim/                  # Simulation environment
│   ├── gazebo/           # Gazebo simulator configs
│   ├── px4/              # PX4 autopilot simulation
│   └── models/           # Physics models
│
├── scripts/              # Build, flash, & utility scripts
│   ├── build.sh          # Compile firmware
│   ├── flash.sh          # Program MCU
│   ├── monitor.sh        # Serial monitor for debugging
│   └── test.sh           # Run test suite
│
├── docs/                 # Documentation
│   ├── CONTRIBUTING.md   # Contributing guidelines
│   ├── ARCHITECTURE.md   # System architecture (coming soon)
│   ├── TASKS.md          # Development roadmap
│   └── API.md            # Protocol & API reference
│
├── .gitignore            # Git ignore patterns
└── README.md             # This file
```

## Key Features

- **Multi-Sensor Integration:** IMU, barometer, magnetometer, GPS, optical flow
- **Real-Time Flight Control:** PID-based attitude & altitude stabilization
- **Failsafe Mechanisms:** Watchdog timer, low-battery detection, radio failsafe
- **Telemetry System:** Real-time data logging and ground station communication
- **Modular Firmware:** Clean driver architecture for easy sensor integration
- **Simulation Support:** Gazebo/PX4 HIL testing before flight

## Hardware Overview

| Component | Specification | Notes |
|-----------|---------------|-------|
| **Flight Controller** | STM32H7 (TBD) | Main MCU for flight logic |
| **IMU** | MPU-9250 or ICM-20689 | 9-DOF inertial measurement |
| **Barometer** | BMP390 | Altitude estimation |
| **Motors** | 920KV brushless | High efficiency |
| **ESCs** | 30A (TBD) | Electronic speed controllers |
| **Battery** | 3S LiPo, 5000mAh (TBD) | Power source |
| **Radio** | 2.4GHz (TBD) | Telemetry & control link |
| **Frame** | 450mm wheelbase (TBD) | 3D-printed or carbon fiber |

*TBD = To Be Determined during design phase*

## Getting Started

### For Firmware Development

```bash
cd firmware
# Build firmware
./scripts/build.sh

# Flash to device (if MCU is connected)
./scripts/flash.sh

# Monitor serial output for debugging
picocom /dev/ttyUSB0 -b 115200
```

### For Hardware Design

- CAD files are in `hardware/cad/` (FreeCAD format)
- Schematics in `hardware/schematics/` (KiCAD format)
- See `hardware/bom/BOM.csv` for component sourcing

### For Testing

```bash
# Run unit tests
./scripts/test.sh unit

# Run hardware-in-the-loop tests
./scripts/test.sh hil
```

## Development Workflow

1. **Create a feature branch:** `git checkout -b feature/description`
2. **Make your changes** following code style guidelines in [CONTRIBUTING.md](docs/CONTRIBUTING.md)
3. **Test locally** before committing
4. **Commit with descriptive messages:** `git commit -m "feat: description"`
5. **Push to your fork** and **open a Pull Request**
6. **Request review** from at least one team member
7. **Address feedback** and merge once approved

See [CONTRIBUTING.md](docs/CONTRIBUTING.md) for detailed guidelines.

## Documentation

- **[CONTRIBUTING.md](docs/CONTRIBUTING.md)** - Contributing guidelines & code style
- **[TASKS.md](docs/TASKS.md)** - Development roadmap by phase
- **[ARCHITECTURE.md](docs/ARCHITECTURE.md)** - System design & diagrams (coming soon)
- **[API.md](docs/API.md)** - Communication protocol reference (coming soon)

## Safety & Compliance

⚠️ **Important:** 
- This drone operates at high power and can cause injury. Handle with extreme caution.
- Always perform pre-flight checks and failsafe tests before each flight.
- Comply with local drone regulations and airspace restrictions.
- Never fly in populated areas or near people/animals.

## Team

IEEE Robotics 2026 Hardware Challenge Team

- **Project Lead:** [Name]
- **Firmware Lead:** [Name]
- **Hardware Lead:** [Name]
- **Team Members:** [Names]

## Contributing

We welcome contributions! Please read [CONTRIBUTING.md](docs/CONTRIBUTING.md) first, then:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'feat: add feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see LICENSE file for details.

## Contact

For questions or issues, please:
- Open a [GitHub Issue](https://github.com/Ezana-Fekadu/IEEE_Robotics-2026_Hardware_Challenge_Drone/issues)
- Contact the project lead
- Post in the team discussion board

## Acknowledgments

- IEEE Robotics Student Organization
- PX4 Autopilot Project
- Open-source drone development community

---

**Last Updated:** February 2026  
**Repository:** [GitHub Link](https://github.com/Ezana-Fekadu/IEEE_Robotics-2026_Hardware_Challenge_Drone)