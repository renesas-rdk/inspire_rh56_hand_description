# inspire_rh56_hand_description

ROS2 package containing URDF description files for the Inspire RH56 dexterous hand.

## Overview

This package provides the robot description for the Inspire RH56 dexterous hand, including URDF/XACRO files, 3D meshes, and visualization launch files for Foxglove Studio. Supports both left and right hand configurations.

## Usage

### Foxglove Studio Visualization

```bash
ros2 launch inspire_rh56_hand_description display_foxglove.launch.py
ros2 launch inspire_rh56_hand_description display_foxglove.launch.py hand_side:=right
```

Connect Foxglove Studio to `ws://<foxglove_bridge_ip>:8765`.

### Using the XACRO Macro

For left hand:
```xml
<xacro:include filename="$(find inspire_rh56_hand_description)/urdf/inspire_hand_left_macro.xacro" />

<xacro:inspire_hand_left prefix="left_hand_" parent="tool0">
  <origin xyz="0 0 0" rpy="0 0 0" />
</xacro:inspire_hand_left>
```

For right hand:
```xml
<xacro:include filename="$(find inspire_rh56_hand_description)/urdf/inspire_hand_right_macro.xacro" />

<xacro:inspire_hand_right prefix="right_hand_" parent="tool0">
  <origin xyz="0 0 0" rpy="0 0 0" />
</xacro:inspire_hand_right>
```

## Hand Specifications

- **Type:** Dexterous anthropomorphic hand
- **Configurations:** Left and right hand variants
- **DOF:** Multiple articulated fingers with independent joint control
- **Coordinate frames:** base → hand_base_link → finger links → TCP

## License

Apache-2.0. URDF model for Inspire RH56 dexterous hand.
