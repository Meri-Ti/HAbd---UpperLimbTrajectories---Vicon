# HAbd-UpperLimbTrajectories-Vicon

This repository contains MATLAB code for developing a rigid body tree-based biomechanical model of the upper limb and visualizing joint trajectories during the abduction (0°, 30°, 60°, 90°) and horizontal abduction (30°, 45°, 60°, 90°, 120°) exercises. The data used in this project have been recorded with the Vicon motion capture system.

## Project Overview

The goal of this project is to model the right human upper limb using the rigid body tree and analyze the abduction and horizontal abduction trajectories at different elevation angles of the main human upper limb joints: sternum, shoulder, elbow, wrist. The project includes:
- Importing each marker trajectory data from CSV files recorded in Vicon Nexus 2.12.1 software.
- Building a rigid body tree to represent the human upper limb for the subject under study using the static trial data.
- Visualizing joint motion for abduction and horizontal abduction exercises and the planes of elevation in which they occurred.
- Generating figures for joint trajectories with respect to different abduction angles.

## Directory Structure

- `S1_ABD`, `S2_ABD`, ..., `S11_ABD`: Folders containing CSV data for abduction exercises from subjects S1 to S11.
- `S1_HABD`, `S2_HABD`, ..., `S11_HABD`: Folders containing CSV data for horizontal exercises from subjects S1 to S11.

## Key Files

- `S1static1.csv`: Example file (1st static trial) for relaxed upper-limb data used for the rigid body tree computation for the horizontal abductions.
- `S1static2.csv`: Example file (2nd static trial) for elevated upper-limb at 90° from the right side of the human body used for the abductions.
- `S1AB0.csv`, `S1AB30.csv`, `S1AB60.csv`, `S1AB90.csv`: Example abduction data files for different abduction angles (0°, 30°, 60°, 90°).

## Code Overview

### Rigid Body Tree Creation

The MATLAB script builds a biomechanical model of the upper limb using the `rigidBodyTree` class:
- **Joints:** Sternum (STRN), shoulder (SHO), elbow (ELB), and wrist (WRIST).
- **Rigid Bodies:** Defined by the mean of corresponding marker positions.
- **Transformation Matrices:** Used to establish the positions of joints relative to each other.

### Visualization

The code includes:
- **3D Visualization** of the rigid body tree, showing the initial configuration of the upper limb.
- **Joint Trajectories** plotted in 3D for each abduction and horizontal abduction angle, with different colors representing each angle (e.g., 0°, 30°, 60°, 90°).
- **Surface Interpolation** for smoother visualization of joint motion for the plane in which they occurred.

### Functions

- `process_abduction_data(filename)`: Processes abduction data files and returns translated x, y, z coordinates for each marker (STRN, SHO, ELB, WRIST).

## Requirements

- **MATLAB R2020b** or later (for rigid body tree and visualization).
- CSV data files for subjects (S1 to S11) stored in respective folders.
