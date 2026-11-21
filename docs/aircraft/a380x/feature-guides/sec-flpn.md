---
title: Secondary Flight Plan
description: Overview and usage of the A380X secondary flight plan feature.
---
# Secondary Flight Plan

The A380X now supports creating up to three secondary flight plans. This is a flight plan that exists in parallel with the primary flight plan.
On the A380, Secondary flight plans are primarily used to plan returns to the departure airfield, runway changes, or emergency scenarios in advance and can be activated when needed. In this section of the guide, we will go over example use cases for this feature.

??? info "Recommendations"

    It is recommended to use SEC 1 for an immediate return to the departure airfield and SEC 2 for alternate runway or procedure planning. SEC 3 should be left empty and dedicated to any route uplinks.

## Engine-out Departure Procedure
### Preparation

In real life, one of the most common use cases for the secondary flight plan is programming an alternative departure procedure in case of an engine failure at takeoff. For this guide, we assume that the FMS has been set up for a flight from Dubai International Airport (OMDB) to London Heathrow Airport (EGLL). In the primary flight plan, we have planned a departure from runway 30L following the SENP2F SID.

![active-flp](../assets/feature-guides/sec-flpn/active-flp.png){loading=lazy}

Due to the steep initial climb gradient requirements and airspace constraints in the vicinity of the airport, we cannot follow our planned SID out of Runway 30L in the event of an engine failure. Instead, we follow an alternative Engine-Out SID (EOSID) procedure.

To program this in the secondary flight plan, we start by creating a copy of the active flight plan. We start on the SEC INDEX page, and then import our primary flight plan using the IMPORT button. This is one way of This is one way to create a secondary flight plan. Another option is to create one from scratch using the INIT button, or perform a CPNY F-PLN request.

![import-sec-flp](../assets/feature-guides/sec-flpn/import-sec-flp.png){loading=lazy}

First, we remove the SID and import our Engine Out SID. We do this by clicking the F-PLN button, and then clicking on our departure runway. We can then select insert next waypoint.

For our Engine Out SID, we will climb on runway track 299° for 25 NM to our engine-out acceleration altitude, and enter a holding pattern. For this, we enter `OMDB30L/299/25` as our waypoint, and then add a holding pattern at this waypoint.

![insert-next-wpt-sec-flp](../assets/feature-guides/sec-flpn/insert-next-wpt-sec-flp.png){loading=lazy}

We can now prepare the arrival back into Dubai. We can do this by selecting the PDB01 waypoint, and select NEW DEST. There, we type OMDB and enter it as our new destination. Then, we select an ILS approach to runway 30L. At this point, we have a rough flight plan programmed, and we can review the ND to confirm that it makes sense.

To be fully prepared for our return, we also want to set up the PERF page for the approach into Dubai. To do this, we use the SEC F-PLN key on the MCDU to return to the main secondary flight plan menu. Compared to the first time, we can now access the PERF page. From there, we navigate to the APPR page and enter the weather and approach data for Dubai as we would for a normal approach.

We are now well prepared for a quick return to Dubai, should it be required.

## Activating the Secondary Flight Plan

We now wish to activate the secondary flight plan to guide us safely and into the holding pattern, while we troubleshoot the issue. Thanks to our preparation, all we have to do is go to the SEC F-PLN page and select ACTIVATE SEC.

!!! warning "Activation of the Secondary Flight Plan"
    The ACTIVATE SEC and SWAP ACTIVE options do not appear unless the active plan and the secondary plan have the same active leg, or the aircraft is in HDG mode. If you do not see the ACTIVATE SEC option, switch to HDG mode. After activating the plan, you can re-engage NAV by performing a direct-to to a suitable waypoint.

After activating the secondary plan, all prepared entries—including route and performance data—are transferred into the active flight plan. The data that was previously in the active plan is overwritten. In some cases, you may wish to retain the original active plan; in such cases, you can swap between the active and secondary plans using the SWAP ACTIVE option.

## Advanced Secondary Flight Plan Operations

The examples covered in this guide demonstrate the basic functionality of the secondary flight plan. In more complex scenarios, secondary flight plans can be used to prepare alternative routes and procedures in advance, allowing the flight crew to respond more efficiently to changing conditions.

For more advanced examples and realistic operational scenarios, see the advanced guide for [Secondary Flight Plan Operations](../../../pilots-corner/a380x/a380x-advanced-guides/sec-flpn.md) guide.