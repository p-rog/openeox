# Use Case 1 - Red Hat Enterprise Linux

### Title

Red Hat Enterprise Linux (RHEL) Life Cycle problem

### Used definitions

- `End-of-Life`: as defined in OpenEoX
- `End-of-Maintenance`
- `End-of-Extended-Support`
- `Full-Support`
- `product`: as defined in [CSAF](https://docs.oasis-open.org/csaf/csaf/v2.0/os/csaf-v2.0-os.html#12-terminology)
- `vendor`: as defined in [CSAF](https://docs.oasis-open.org/csaf/csaf/v2.0/os/csaf-v2.0-os.html#12-terminology)
- `product_identification_helper` to cover product versions (supported product streams)

### Description

Red Hat Enterprise Linux has two main versions: 8 and 9  
Both verisons deliver a ten year life cycle in Full Support and Maintenance Support Phases followed by an Extended Life Phase.  
In addition, Red Hat Enterprise Linux 8 and 9 customers may purchase annual Add-on subscriptions called Extended Life-cycle Support (ELS) to extend limited subscription services beyond the Maintenance Support Phase.  

Each main (major) version is devided to minor versions, called also supported streams, which are directly correlated with the content distribution channels and has its own supprot start and end dates.  
New version release does not define the end of support of the previous version.  
Customers still have some time to prepare for migration to the new minor version.

Supported documentation:  
https://access.redhat.com/support/policy/updates/errata  

### Example lifecycle schema

The OpenEoX file for the RHEL 9 high level schema:  

**document:**
- document metadata
  - id
  - notes
  - publisher
- tracking
- revision_history

**products:**
- RHEL 9.2
  - ID: Product_ID-1
  - based_on: rhel_9.1
  - product_identification_helper
    - product_stream: rhel_9.2
    - product_cpes: cpe:/o:redhat:enterprise_linux:9.2::baseos
- RHEL 9.3
  - ID: Product_ID-2
  - based_on: rhel_9.2
  - product_identification_helper
    - product_stream: rhel_9.3
    - product_cpes: cpe:/o:redhat:enterprise_linux:9.3::baseos

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
- RHEL 9.2
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
- RHEL 9.3
  - active_phases[]:
    - ID:1
      - GA: July 1 2023
      - March 1 2024
    - ID:2
      - March 1 2024
