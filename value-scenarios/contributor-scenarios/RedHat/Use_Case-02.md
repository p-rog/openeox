# Use Case 2 - Red Hat OpenShift Container Platform

### Title

Red Hat OpenShift Container Platform Life Cycle problem

### Used definitions

- `End-of-Life`: as defined in OpenEoX
- `End-of-Maintenance`
- `End-of-Extended-Support`
- `Full-Support`
- `product`: as defined in [CSAF](https://docs.oasis-open.org/csaf/csaf/v2.0/os/csaf-v2.0-os.html#12-terminology)
- `vendor`: as defined in [CSAF](https://docs.oasis-open.org/csaf/csaf/v2.0/os/csaf-v2.0-os.html#12-terminology)
- `product_identification_helper` to cover product versions (supported product streams)

### Description

Red Hat OpenShift container platform v4 provides a time-delineated, phased life cycle, where in at least 4 minor versions can be supported at any time.  
The time period of support is fixed from the point of minor version release and offers varying levels of support and maintenance.  
Red Hat aims to forecast releases at a 4 month cadence, providing customers ample opportunity to plan.

Supported documentation:  
https://access.redhat.com/support/policy/updates/openshift

### Example lifecycle schema

The OpenEoX file for the OpenShift 4 high level schema:  

**document:**
- document metadata
  - id
  - notes
  - publisher
- tracking
- revision_history

**products:**
- OCP 4.12
  - ID: Product_ID-1
  - based_on: rhel_9.1
  - product_identification_helper
    - product_stream: 4.12
    - product_cpes: cpe:/a:redhat:openshift:4.12::el9
- OCP 4.13
  - ID: Product_ID-2
  - based_on: rhel_9.2
  - product_identification_helper
    - product_stream: 4.13
    - product_cpes: cpe:/a:redhat:openshift:4.13::el9
- OCP 4.14
  - ID: Product_ID-3
  - based_on: rhel_9.2
  - product_identification_helper
    - product_stream: 4.14
    - product_cpes: cpe:/a:redhat:openshift:4.14::el9
- OCP 4.15
  - ID: Product_ID-4
  - based_on: rhel_9.2
  - product_identification_helper
    - product_stream: 4.15
    - product_cpes: cpe:/a:redhat:openshift:4.15::el9
- OCP 4.16
  - ID: Product_ID-5
  - based_on: rhel_9.4
  - product_identification_helper
    - product_stream: 4.16
    - product_cpes: cpe:/a:redhat:openshift:4.16::el9
- OCP 4.17
  - ID: Product_ID-6
  - based_on: rhel_9.4
  - product_identification_helper
    - product_stream: 4.17
    - product_cpes: cpe:/a:redhat:openshift:4.17::el9


**lifecycle phases:**
- ID:1
  - type: Full-Support
  - desc: "The time when the product version is released, the GA date"
  - scope: [bugs, vulnerability updates, configuration support]
  - visibility: public
- ID:2
  - type: End-of-Life
  - desc: "end of life"
  - scope: []
  - visibility: public
- ID:3
  - type: End-of-Maintenance
  - desc: "we are shipping Critical + Important"
  - scope: [critical bugs, Critical and Important vulnerability updates]
  - visibility: public
- ID:4
  - type: End-of-Extended-Support
  - desc: "we are shipping Critical only"
  - scope: [Critical vulnerability updates]
  - visibility: public
- ID:5
  - type: End-of-Extended-Support
  - desc: "CustomerX-specific phase"
  - scope: [critical bugs, Critical and Important vulnerability updates]
  - visibility: private

**mapping:**
- OCP 4.12
  - active_phases[]:
    - ID:1
      - GA: Jan 1
      - July 1 2023
    - ID:3
      - March 2025
    - ID: 4
      - March 2027
    - ID: 2
      - March 2027
- OCP 4.13
  - active_phases[]:
    - ID:1
      - GA: July 1 2023
      - March 1 2024
    - ID:2
      - March 1 2024
- OCP 4.14
  - active_phases[]:
    - ID:1
      - GA: Jan 1
      - July 1 2023
    - ID:3
      - March 2025
    - ID: 4
      - March 2027
    - ID: 2
      - March 2027
- OCP 4.15
  - active_phases[]:
    - ID:1
      - GA: Jan 1
      - July 1 2023
    - ID:3
      - March 2025
    - ID: 4
      - March 2027
    - ID: 2
      - March 2027
- OCP 4.16
  - active_phases[]:
    - ID:1
      - GA: Jan 1
      - July 1 2023
    - ID:3
      - March 2025
    - ID: 4
      - March 2027
    - ID: 2
      - March 2027
- OCP 4.17
  - active_phases[]:
    - ID:1
      - GA: Jan 1
      - July 1 2023
    - ID:3
      - March 2025
    - ID: 4
      - March 2027
    - ID: 2
      - March 2027