# Contributing to IEEE Robotics 2026 Hardware Challenge - Drone

## Overview
This document outlines guidelines for contributing to the drone project. Our goal is to maintain clean, collaborative development practices.

## Repository Structure

- **firmware/** - MCU code (flight controller, sensor drivers, control loops)
- **src/** - Higher-level tooling (Python utilities, test harnesses)
- **hardware/** - CAD files, schematics, PCB layouts, BOM
- **docs/** - Design documents, meeting notes, task breakdowns
- **sim/** - Gazebo/PX4/ROS or custom simulation configs
- **tests/** - Hardware-in-the-loop tests, unit tests
- **scripts/** - Build, flash, and log-download helper scripts

## Git Workflow

### Branching
- Always work on feature branches
- Branch naming convention: `feature/<description>`, `fix/<description>`, `docs/<description>`
- Examples:
  - `feature/imu-driver`
  - `fix/compass-calibration`
  - `docs/setup-guide`

### Committing
- Use conventional commit messages:
  - `feat: add motor mixing algorithm`
  - `fix: correct IMU axis mapping`
  - `docs: update sensor integration guide`
  - `test: add unit tests for PID controller`
  - `refactor: optimize communication protocol`

### Pull Requests
1. Create a feature branch from `main`
2. Make your changes
3. Push to your branch
4. Open a PR with a clear description of changes
5. Request review from at least one team member
6. Address feedback in review
7. Merge once approved

## Code Style

### C/C++ (Firmware)
- Use meaningful variable names
- Follow embedded conventions (e.g., snake_case for functions)
- Document critical control loops

### Python (Utilities)
- Follow PEP 8
- Use type hints where practical
- Document functions with docstrings

### Hardware (CAD/Schematics)
- Use consistent naming conventions
- Include revision numbers in filenames
- Document part numbers and vendors

## Testing Before Merge
- Ensure code compiles without warnings
- Run local tests: `./scripts/test.sh`
- Verify changes don't break existing functionality
- Add tests for new features

## Communication
- Use GitHub Issues to track tasks and bugs
- Use GitHub Discussions for design questions
- Tag team members with @ mentions for visibility

## Hardware Change Management
- Hardware changes require approval from the lead engineer
- Update BOM and schematics in the same PR
- Include a changelog entry describing modifications

