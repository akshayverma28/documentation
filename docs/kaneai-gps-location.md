---
id: kaneai-gps-location
title: GPS Location Mocking for Mobile App and Mobile Browser Authoring
hide_title: false
sidebar_label: GPS Location
description: Learn how to use GPS Location Override feature in KaneAI for testing location-based functionalities in Mobile App and Mobile Browser sessions
keywords:
  - testmu ai automation
  - testmu ai kaneai
  - kaneai mobile app
  - kaneai mobile browser
  - gps location
  - location override
  - geolocation testing
  - mobile browser gps
url: https://www.lambdatest.com/support/docs/kaneai-gps-location/
site_name: LambdaTest
slug: kaneai-gps-location/
canonical: https://www.testmuai.com/support/docs/kaneai-gps-location//
---

<script type="application/ld+json"
      dangerouslySetInnerHTML={{ __html: JSON.stringify({
       "@context": "https://schema.org",
        "@type": "BreadcrumbList",
        "itemListElement": [{
          "@type": "ListItem",
          "position": 1,
          "name": "TestMu AI",
          "item": "https://www.lambdatest.com"
        },{
          "@type": "ListItem",
          "position": 2,
          "name": "Support",
          "item": "https://www.lambdatest.com/support/docs/"
        },{
          "@type": "ListItem",
          "position": 3,
          "name": "GPS location",
          "item": "https://www.lambdatest.com/support/docs/kaneai-gps-location/"
        }]
      })
    }}
></script>

> This document provides detailed instructions for utilizing the GPS Location Override feature in KaneAI for both Mobile App and Mobile Browser testing. It covers how to set GPS coordinates at the start of a session as well as within a running session to test location-based application behavior accurately.

## Overview

Testing location-based application behavior (such as geo-restricted content, regional UI, compliance flows, or location-aware features) is challenging when device GPS coordinates are dynamic or tied to the physical location of the tester.

The GPS Location Override feature solves this problem by allowing users to explicitly define latitude and longitude values. This ensures consistent, repeatable, and deterministic testing of location-dependent scenarios on supported mobile devices.

This feature is supported for both:
- **Mobile App Sessions** — GPS location can be set during session initialization.
- **Mobile Browser Sessions** — GPS location can be set during session initialization as well as changed within a running session.

## How To Use

### Mobile App Sessions

#### Set GPS Location at Session Start

While creating a test session, go to **Advanced Settings** and enable the GPS location mocking option. Either include the location coordinates or search for a particular location from the map. Ensure the coordinates fall within the allowed ranges:

- Longitude: -180 to 180
- Latitude: -90 to 90

<img loading="lazy" src={require('../assets/images/kane-ai/features/gps/gps-advanced-settings.jpg').default} alt="gps-enabled" className="doc_img"/>

1. Launch the session after providing the coordinates.
2. The device GPS location is mocked at session start.
3. The configured location remains active for the entire session of the test being authored.

### Mobile Browser Sessions

#### Set GPS Location at Session Start

While creating a Mobile Browser test session, go to **Advanced Settings** and enable the GPS location mocking option. Provide the desired coordinates or search for a location on the map.

- Longitude: -180 to 180
- Latitude: -90 to 90

<img loading="lazy" src={require('../assets/images/kane-ai/features/gps/gps-mobile-browser-start.png').default} alt="gps-mobile-browser-start" className="doc_img"/>

#### Change GPS Location Within a Running Session

You can also change the GPS location during an active Mobile Browser session:

1. Click on the **Advanced Settings** option inside the running session.
2. Update the GPS coordinates or search for a new location.
3. The updated location will be applied immediately to the session.

<img loading="lazy" src={require('../assets/images/kane-ai/features/gps/gps-mobile-browser-in-session.png').default} alt="gps-mobile-browser-in-session" className="doc_img"/>

### Verify the Applied Location

GPS coordinates can be verified:
- Inside the running session by clicking **Advanced Settings**
- On the Session Summary page after execution
- During Edit Test, the coordinates used in authoring would be autoselected in playground

<img loading="lazy" src={require('../assets/images/kane-ai/features/gps/gps-in-session.png').default} alt="GPS-in-session" className="doc_img"/>

## Limitations

- For Mobile App sessions, GPS override is applied only during session initialization and cannot be changed mid-session.
- Replay/Edit sessions reuse GPS values from the original session.

## Troubleshooting

### Invalid Latitude or Longitude Error

**Issue:** Session fails to start due to a validation error.

**Cause:**
- Longitude is less than -180 or greater than 180
- Latitude is less than -90 or greater than 90

**Resolution:**
- Verify that latitude and longitude values are within valid ranges
- Ensure values are passed as valid numbers or numeric strings


---

> Have any feedback or request? Reach out to us via [support@testmu.ai](mailto:support@testmu.ai) and we would be happy to hear from you.