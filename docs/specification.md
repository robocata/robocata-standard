---
layout: default
title: Specification
---

# RoboCata Standard V1.0 — Specification

> **Note:** The canonical reference for this specification is the PDF document in [`pdf/RoboCata-Standard-V1.pdf`](../pdf/RoboCata-Standard-V1.pdf). This markdown version is provided for convenience and browsability.

---

## 1. Identification & Description

Core fields that identify a robot and provide textual descriptions.

| Field | Label | Type | Description |
|---|---|---|---|
| robot_code * | Robot Code | Text | Unique RoboCata identifier (format: RBC-TT-CC-XXXXXXX) |
| info_name * | Robot Name | Text | Full product name (e.g., "IRB 1400", "Spot Enterprise") |
| manufacturer_text * | Manufacturer | Text | Company name (e.g., "ABB", "Boston Dynamics") |
| type * | Type | Single code | Physical form factor classification (e.g., "Robotic Arm", "Mobile Platform") |
| domain * | Domain | Single code | Application domain — PRO (Professional & Services), HOME (Home & Consumer), IND (Industrial & Manufacturing) |
| category * | Category | Single code | Primary application category (e.g., "Medical & Healthcare", "Production & Assembly") |
| info_model | Model | Text | Model designation, if different from the product name |
| info_model_number | Model Number | Text | Alphanumeric model number for the specific variant |
| info_id | Product ID | Text | Manufacturer's unique product identifier or SKU |
| info_productline | Product Line | Text | Product line or family name (e.g., "GoFa") |
| short_description | Short Description | Text | Catalog summary for listings (40–100 words) |
| description_detailed | Detailed Description | Text | Full description covering capabilities, applications, features (80–200 words) |
| description_long | Long Description | Text | Extended narrative description (2–5 sentences) for SEO and detail pages |
| current_version | Version | Text | Current software or hardware version number |
| product_url | Product URL | URL | Link to the manufacturer's official product page |
| github_url | GitHub URL | URL | Link to open-source repository if available |
| github_repos | GitHub Repos | Number | Number of GitHub repositories related to this robot |
| meta_tags | Meta Tags | Text | Keywords and tags for search optimization |
| info_status | Product Status | Single code | Availability status (e.g. In Production, Pre-order, Coming Soon, Prototype) |
| info_release_year | Release Year | Number | Year the robot was first released or announced |
| info_status_since_date | Status Date | Date | Date when the status became effective |

\* Required fields

### Type

Physical form and morphology. Field: `type`

| Code | RBC Code | Name | Description |
|---|---|---|---|
| ARM | AR | Robotic Arm | Fixed-base manipulator arm |
| MOBI | MO | Mobile Platform | Wheeled or tracked ground robot |
| BIPD | BI | Biped | Bipedal/humanoid walking robot |
| QUAD | QU | Quadruped | Four-legged walking robot |
| HEXA | HE | Hexapod+ | Six or more legged robot |
| AERI | AE | Aerial | Flying robot (drone, VTOL, fixed-wing) |
| AQUA | AQ | Aquatic | Underwater/surface water robot |
| SERP | SE | Serpentine | Snake-like, limbless robot |
| SPHR | SP | Spherical | Ball or rolling form factor |
| SOFT | SO | Soft Robot | Soft-bodied, flexible material robot |
| WEAR | WE | Wearable | Body-worn, exoskeleton, prosthetic |
| VEHI | VE | Vehicle | Autonomous vehicle platform |
| APPL | AP | Appliance | Robot built into appliance |
| SWRM | SW | Swarm Unit | Designed for swarm operations |
| HYBR | HY | Hybrid | Hybrid or multi-modal form factor |

### Domain

High-level market segmentation. Each robot belongs to exactly one domain. Field: `domain`

| Code | Name | Description |
|---|---|---|
| IND | Industrial & Manufacturing | Factory floors, production lines, heavy industry |
| PRO | Professional & Services | Commercial, professional, and institutional use |
| HOME | Home & Consumer | Residential and personal use |

### Category

Primary application sector. 29 categories grouped by domain. Field: `category`

#### Industrial (5)

| Code | RBC Code | Name | Description |
|---|---|---|---|
| QC | QC | Quality Control | Inspection, testing, measurement |
| PROD | PR | Production & Assembly | Manufacturing, assembly lines |
| WELD | WL | Welding & Fabrication | Welding, cutting, metal work |
| HEAVY | HV | Heavy Industry | Mining, steel, foundry |
| PACK | PK | Packaging & Logistics | Palletizing, sorting, warehouse |

#### Professional (15)

| Code | RBC Code | Name | Description |
|---|---|---|---|
| MED | MD | Medical & Healthcare | Surgery, rehabilitation, patient care |
| AGR | AG | Agricultural | Farming, harvesting, crop management |
| CONST | CN | Construction & Building | Building, demolition, site work |
| TRANS | TR | Transportation & Delivery | Delivery, logistics, last-mile |
| LAB | LB | Laboratory & Research | Scientific research, lab automation |
| HOSP | HS | Hospitality & Food Service | Hotels, restaurants, food service |
| RET | RT | Retail & Commerce | Store operations, customer service |
| EDU | ED | Educational | Teaching, training, STEM |
| INFRA | IF | Infrastructure & Utilities | Power, water, telecom maintenance |
| LAND | LD | Landscaping & Grounds | Commercial landscaping |
| CLEAN | CL | Commercial Cleaning | Office, industrial, public space |
| SQP | SQ | Security (Professional) | Commercial/industrial security |
| SPORTP | ST | Sports (Professional) | Professional sports, training |
| OFF | OF | Office & Business | Office automation, telepresence |
| VET | VT | Veterinary & Animal Care | Animal healthcare, livestock |

#### Home & Consumer (9)

| Code | RBC Code | Name | Description |
|---|---|---|---|
| HCLEAN | HC | Home Cleaning | Residential cleaning (vacuuming, mopping) |
| YARD | YD | Yard & Garden | Lawn care, garden maintenance |
| COOK | CK | Kitchen & Cooking | Food preparation, cooking |
| ENT | EN | Entertainment & Gaming | Fun, games, recreation |
| COMP | CM | Companion | Social, emotional companionship |
| CARE | CR | Personal Care | Health monitoring, personal assistance |
| SQH | SH | Home Security | Residential security, patrol |
| SPORTH | SF | Sports & Fitness (Home) | Home fitness, personal training |
| CHILD | CH | Childcare & Education | Child supervision, home education |

### Conformance Definition (Normative)

A robot record shall be considered conformant with RoboCata Standard V1.0 (March 2026) if:

- It contains all required fields: `robot_code`, `info_name`, `manufacturer_text`, `type`, `domain`, `category`
- All coded fields use only values defined in Appendix E
- All numeric fields follow Appendix B unit conventions
- Field names match exactly the canonical field identifiers
- A conformant implementation may omit non-required fields, but must not redefine or alter field semantics

---

## 2. Media Requirements

Visual and video media are recommended for the standard. Every robot should have one image designated as the primary image. It is used as the main display image, thumbnail in listings, Open Graph image for social sharing, and representative image in comparisons.

### Image Fields

| Field | Label | Type | Description |
|---|---|---|---|
| media_primaryimage | Primary Image | URL | URL of the primary product image (used for thumbnails, OG tags, listings) |
| images | Image Gallery | JSON Array | Array of image URLs for the robot gallery |

#### Image Requirements

| Requirement | Specification | Notes |
|---|---|---|
| Formats | PNG or JPG (JPEG) | PNG preferred for transparency; JPG for photos |
| Min Resolution | 800 x 600 px | Higher resolution preferred |
| Max File Size | 5 MB per image | Optimize for web |
| Background | Clean / white preferred | Product shots on white; in-situ also accepted |
| Minimum | 1 per robot | At least one clear product photo required |
| Recommended | 3-5 per robot | Front, side, in-application, detail shots |

### Video Fields

| Field | Label | Type | Description |
|---|---|---|---|
| media_video_url | Video URL | URL | Primary product video (YouTube/Vimeo link or MP4) |
| media_demovideo_url | Demo Video | URL | Demonstration video showing the robot in operation |
| media_360view_url | 360° View | URL | Interactive 360-degree view URL |

#### Video Requirements

| Requirement | Specification | Notes |
|---|---|---|
| Formats | MP4 (H.264) or YouTube/Vimeo URL | Hosted links preferred |
| Min Resolution | 720p | 1080p preferred; 4K accepted |
| Duration | 30-90 seconds recommended | Max 5 minutes |
| Content | Robot in operation | Movement, manipulation, navigation, or task execution |

### Document Fields

| Field | Label | Type | Description |
|---|---|---|---|
| media_brochure_url | Brochure URL | URL | Link to marketing brochure PDF |
| media_datasheet_url | Datasheet URL | URL | Link to technical datasheet PDF |

---

## 3. Physical Dimensions & Weight

Dimensions, weight, payload, and physical characteristics.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| dimensions_weight_kg | Weight | kg | Total robot weight without payload |
| dimensions_height_mm | Height | mm | Overall height |
| dimensions_width_mm | Width | mm | Overall width |
| dimensions_depth_mm | Depth/Length | mm | Overall depth or length |
| length_mm | Length | mm | Additional length measurement (if depth != length) |
| reach_mm | Reach | mm | Maximum operational reach distance |
| reach_max_mm | Max Reach | mm | Maximum reach distance (extended arm) |
| payload_max_kg | Max Payload | kg | Maximum payload capacity |
| payload_rated_kg | Rated Payload | kg | Rated (nominal) payload capacity |
| wrist_payload_kg | Wrist Payload | kg | Wrist/end-effector payload capacity |
| payload_capacity_kg | Weight with Payload | kg | Total weight including max payload |
| working_envelope | Working Envelope | Text | Description of reachable workspace geometry |
| footprint_area | Footprint | Text | Floor space required (e.g., "600x600 mm") |
| material_construction | Material | Text | Primary construction material (aluminum, steel, carbon fiber) |
| mounting_options | Mounting | Text | Mounting configurations (floor, ceiling, wall, rail) |

---

## 4. Motion & Kinematics

Movement capabilities, kinematic specifications, and joint details.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| mobility_primary | Primary Mobility | Single code | Primary locomotion type (see Mobility codes) |
| mobility_secondary_list | Secondary Mobility | List of codes | Secondary/alternative mobility modes |
| tech_maxspeedvalue | Max Speed Value | Number | Maximum speed as raw numeric value |
| speed_mobile_ms | Speed | m/s | Maximum movement speed in meters per second |
| speed_class | Speed Class | Text | Speed classification category |
| tech_speedunit | Speed Unit | Single code | Unit for speed measurement (m/s, mm/s, cm/s, RPM) |
| degrees_freedom | Degrees of Freedom (DoF) | Single code | Number of degrees of freedom (joints/axes) |
| sys_kinematic | Kinematics | Single code | Kinematic structure (articulated, SCARA, delta, cartesian) |
| joint_specs | Joint Specs | Text | Detailed joint specifications |
| joint_speeds | Joint Speeds | Text | Individual joint rotation speeds (deg/s per axis) |
| joint_rotation_range | Joint Range | Text | Joint rotation range (±degrees per axis) |
| joint_torque_max | Max Joint Torque | Text | Maximum torque per joint (Nm) |
| repeatability_position_mm | Repeatability | ±mm | Position repeatability accuracy |
| acceleration_max | Max Acceleration | Text | Maximum acceleration specification |
| dynamic_model | Dynamic Model | Single code | Available dynamic model format (URDF, STEP, CAD) |
| moment_of_inertia | Moment of Inertia | Text | Moment of inertia at wrist flange |
| backlash_arcmin | Backlash | arcmin | Backlash in arc minutes |

---

## 5. Navigation & Localization

Navigation systems, path planning, and obstacle handling.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| navigation_list | Navigation Methods | List of codes | All navigation systems (SLAM, GPS, VSLAM, LiDAR, wire-guided) |
| navigation_system | Navigation System | Text | Primary navigation system description |
| path_planning | Path Planning | Text | Path planning algorithm (A*, RRT, potential fields) |
| mapping_capability | Mapping | Text | Mapping capability (SLAM, pre-mapped, dynamic) |
| localization_method | Localization | Text | Localization method (LiDAR, visual, UWB, GPS) |
| obstacle_avoidance | Obstacle Avoidance | Text | Obstacle avoidance method (reactive, predictive, 3D) |
| obstacle | Obstacle Detection | Single code | Obstacle detection capability (None, Limited, Extensive) |
| multifloor | Multi-Floor | Single code | Multi-floor capability (None, Single, Multi) |

---

## 6. Power & Energy

Power supply, consumption, battery, and charging specifications.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| powersource | Power Source | Single code | Primary power type (AC Mains, Battery, Pneumatic, Solar) |
| powersource_secondary_list | Secondary Power | List of codes | Secondary/backup power sources |
| power_voltage_min | Voltage (min) | V | Minimum operating voltage |
| power_voltage_max | Voltage (max) | V | Maximum operating voltage |
| power_phases | Power Phases | Number | Number of power phases (1/3) |
| power_frequency_hz | Power Frequency | Hz | Power frequency (50/60 Hz) |
| power_consumption_normaluse_w | Power (Normal) | W | Typical power consumption during normal use |
| power_consumption_peakuse_w | Power (Peak) | W | Peak power consumption |
| bat_type | Battery Type | Single code | Battery chemistry (Li-ion, LiPo, LiFePO4, Lead-acid) |
| bat_capacity_wh | Battery Capacity | Wh | Battery capacity in watt-hours |
| bat_voltage_v | Battery Voltage | V | Nominal battery voltage |
| bat_runtime_hours | Runtime | hours | Typical operating time per charge |
| bat_charge_time_hours | Charge Time | hours | Full charge time |
| bat_swap | Battery Swap | Boolean | Whether battery is hot-swappable |
| bat_cycles | Battery Cycles | Number | Rated charge/discharge cycle count |
| charging_method | Charging Method | Text | Charging method (dock, cable, wireless, solar) |
| energy_rating | Energy Rating | Single code | Energy efficiency rating (A+++ through D) |

---

## 7. Performance & Throughput

Speed, throughput, and operational performance metrics.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| throughput_value | Throughput Value | Number | Raw throughput value |
| throughput_units | Throughput Units | Single code | Unit for throughput measurement |
| cycle_time_seconds | Cycle Time | seconds | Time per complete operation cycle |
| accuracy_mm | Accuracy | mm | Positioning or task accuracy |
| operating_hours_per_day | Operating Hours | hours/day | Designed continuous operating hours |
| uptime_percent | Uptime | % | Expected uptime percentage |
| mtbf_hours | MTBF | hours | Mean time between failures |

---

## 8. Environment & Operating Conditions

Environmental and operating condition requirements.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| environment_type_list | Environment Types | List of codes | Compatible operating environments |
| ip_rating | IP Rating | Single code | Ingress Protection rating |
| operating_temp_min_c | Temp Min | °C | Minimum operating temperature |
| operating_temp_max_c | Temp Max | °C | Maximum operating temperature |
| operating_humidity_min | Humidity Min | % | Minimum operating humidity |
| operating_humidity_max | Humidity Max | % | Maximum operating humidity |
| altitude_max_m | Max Altitude | m | Maximum operating altitude |
| noise_level_db | Noise Level | dB(A) | Maximum noise level during operation |

---

## 9. Safety & Certifications

Safety features and collaborative operation specifications.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| safety_feat_list | Safety Features | List of codes | Safety features and systems |
| safety_compliance_list | Safety Compliance | List of codes | Industry-specific compliance certifications |
| collaboration | Collaboration Level | Single code | Human-robot collaboration capability |
| child_safe | Child Safety | Single code | Child safety classification |
| pet_safe | Pet Safety | Single code | Pet safety classification |
| collision_force_n | Collision Force | N | Maximum collision force limit |

---

## 10. Connectivity & Communication

Communication interfaces and network connectivity.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| connectivity_list | Connectivity | List of codes | All connectivity interfaces |
| api_doc | API Documentation | Single code | API documentation availability |
| data_protocols | Data Protocols | Text | Supported data communication protocols |
| cloud_platform | Cloud Platform | Text | Associated cloud management platform |
| ota_updates | OTA Updates | Boolean | Over-the-air update capability |

---

## 11. Control & Programming

Control interfaces, programming methods, and software interfaces.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| control_interface_list | Control Interfaces | List of codes | All control interface methods |
| control_programming_list | Programming Methods | List of codes | Available programming methods |
| control_architecture | Control Architecture | Single code | Control system architecture |
| teach_pendant_included | Teach Pendant | Boolean | Teach pendant included |
| simulation_support | Simulation Support | Text | Supported simulation environments |

---

## 12. Software & Operating Systems

Software platforms, operating systems, and development tools.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| software_platform | Software Platform | Single code | Primary software/OS platform |
| operating_system_list | Operating Systems | List of codes | All compatible operating systems |
| ros_package_list | ROS Packages | List of codes | Compatible ROS packages and versions |
| tech_sdk | SDK Availability | Single code | SDK availability and licensing |

---

## 13. Sensors & Perception

Sensors, perception systems, and environmental awareness.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| sensor_list | Sensors | List of codes | All onboard sensors |
| vision_system_list | Vision Systems | List of codes | Computer vision capabilities |
| sensor_update_rate_hz | Sensor Rate | Hz | Primary sensor update frequency |
| lidar_range_m | LiDAR Range | m | Maximum LiDAR detection range |

---

## 14. AI & Autonomy

Artificial intelligence capabilities and autonomy level.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| autonomy | Autonomy Level | Single code | Level of autonomous operation (L0-L5) |
| ai_capabilities_list | AI Capabilities | List of codes | AI and machine learning capabilities |
| processor_list | Processors | List of codes | Onboard computing processors |
| onboard_compute | Onboard Compute | Text | Onboard computing hardware description |

---

## 15. Hardware & Actuators

Actuator types and mechanical hardware.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| actuator_type_list | Actuator Types | List of codes | Types of actuators used |
| gripper_type | Gripper Type | Text | End effector/gripper type |
| tool_changer | Tool Changer | Boolean | Automatic tool changer capability |

---

## 16. Features & Capabilities

General features and special capabilities.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| smart_home_list | Smart Home Integration | List of codes | Compatible smart home platforms |
| interaction | Daily Interaction | Single code | Required daily human interaction level |
| learning_curve | Learning Curve | Single code | Time required to learn operation |
| skill_level_required | Skill Level | Single code | Required operator skill level |
| mod_friendly | Mod Friendly | Single code | Modification/customization friendliness |

---

## 17. Installation & Space

Installation requirements and space needs.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| installation_type_list | Installation Types | List of codes | Supported installation methods |
| setup_time | Setup Time | Single code | Time required for initial setup |
| space_required_class | Space Required | Single code | Floor space classification needed |
| scale | Scale | Single code | Physical size classification |

---

## 18. Commercial & Pricing

Commercial information and pricing tiers.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| pricetier | Price Tier | Single code | Price range classification |
| price_exact | Exact Price | Number | Exact price in USD (if publicly available) |
| price_currency | Currency | Text | Currency for exact price |
| lead_time | Lead Time | Single code | Delivery lead time estimate |
| demo_avail_list | Demo Availability | List of codes | Available demonstration options |
| roi | ROI Period | Single code | Expected return on investment timeline |

---

## 19. Support & Maintenance

Support options, maintenance, and warranty.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| warranty_months | Warranty | Single code | Warranty duration |
| support_types_list | Support Types | List of codes | Available support channels |
| service_option_list | Service Options | List of codes | Available service plans |
| maintenance_interval | Maintenance Interval | Single code | Recommended maintenance schedule |
| spare_parts_avail | Spare Parts | Single code | Spare parts availability |
| consum_req_list | Consumables | List of codes | Required consumable items |
| manual_avail | Manual Availability | Single code | User manual availability |

---

## 20. Applications & Use Cases

Target applications, demographics, and use cases.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| user_demographic_list | User Demographics | List of codes | Target user segments |
| training_list | Training Options | List of codes | Available training programs |
| application_examples | Application Examples | Text | Specific application examples |

---

## 21. Certifications & Standards

Industry certifications and standards compliance.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| certifications_list | Certifications | Text | Industry certifications held |
| standards_compliance | Standards | Text | Standards the robot complies with |
| country_of_origin | Country of Origin | Text | Manufacturing country |

---

## 22. Ratings & Metrics

User ratings and performance metrics.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| user_rating | User Rating | Number | Average user rating (1-5 scale) |
| review_count | Review Count | Number | Number of user reviews |
| expert_rating | Expert Rating | Number | Expert/professional rating |

---

## 23. Manufacturer & Origin

Manufacturer details and production information.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| manufacturer_url | Manufacturer URL | URL | Manufacturer's website |
| manufacturer_country | Manufacturer Country | Text | Manufacturer's headquarters country |
| manufacturing_location | Manufacturing Location | Text | Where the robot is manufactured |
| founded_year | Founded Year | Number | Year the manufacturer was founded |

---

## 24. Research & Popularity

Research metrics and popularity indicators.

| Field | Label | Unit/Type | Description |
|---|---|---|---|
| academic_papers | Academic Papers | Number | Number of published academic papers |
| citations | Citations | Number | Total academic citations |
| github_stars | GitHub Stars | Number | Total GitHub stars across repositories |
| market_share | Market Share | Text | Estimated market share information |
| sys_lang_list | System Languages | List of codes | Supported interface languages |
