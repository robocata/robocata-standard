---
layout: default
title: "Appendix B: Unit Conventions"
---

# Appendix B: Unit Conventions

All numeric specification fields in the RoboCata Standard follow these unit conventions. Implementations must use the specified units to ensure comparability.

| Measurement | Unit | Symbol | Field Examples |
|---|---|---|---|
| Weight / Mass | Kilograms | kg | dimensions_weight_kg, payload_max_kg |
| Length / Distance | Millimeters | mm | dimensions_height_mm, reach_mm |
| Speed (linear) | Meters per second | m/s | speed_mobile_ms |
| Temperature | Degrees Celsius | °C | operating_temp_min_c, operating_temp_max_c |
| Voltage | Volts | V | power_voltage_min, bat_voltage_v |
| Power | Watts | W | power_consumption_normaluse_w |
| Energy | Watt-hours | Wh | bat_capacity_wh |
| Time | Hours | h | bat_runtime_hours, bat_charge_time_hours |
| Sound Level | Decibels (A-weighted) | dB(A) | noise_level_db |
| Repeatability | Plus/minus millimeters | ±mm | repeatability_position_mm |
| Force | Newtons | N | collision_force_n |
| Altitude | Meters | m | altitude_max_m |
