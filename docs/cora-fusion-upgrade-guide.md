# CORA Fusion Upgrade Guide

## Purpose

This document is the upgrade path for the current CORA Fusion model.

It is written for the model state shown in the latest screenshot:

- top and bottom acrylic plates already exist
- a perimeter enclosure ring already exists
- 4 corner standoffs already exist
- the board outline and a first pass of the major chip blocks already exist
- connector placeholder bodies already exist

That means you are no longer starting from zero.

You are now in the stage where the job is to turn the model from:

- a credible enclosure study

into:

- a premium transparent reasoning appliance

## Submission Objective

The immediate objective is not to finish a production PCB or a fabrication-final hardware program.

The immediate objective is:

- make CORA look real
- make it look expensive
- make it look authored
- make it feel like a coherent new computing object
- make it strong enough for the `1517` submission and related concept materials

So this guide is optimized for:

- concept credibility
- premium industrial feel
- strong render readiness
- a board that looks intentional and valuable

It is **not** optimized for:

- final electronics correctness
- custom schematic capture
- production DFM
- final manufacturing tolerances
- a full redesign of the file structure

## Scope Lock

To keep momentum and avoid overbuilding, the following things are now considered locked unless something is clearly broken:

- the overall acrylic monolith direction
- the current browser structure
- the body-based modeling workflow
- the basic enclosure footprint
- the use of four visible corner standoffs
- the dev-board-based V1 concept path

That means the work ahead is mostly:

- refinement
- board detailing
- hardware identity
- cutout cleanup
- visual hierarchy
- render preparation

Not:

- re-architecting the whole model
- rebuilding the browser from scratch
- switching to a different CAD workflow
- diving into schematic or PCB work for this submission

## Premium Target

If this model is working at the right level by the end of the guide, it should feel like:

- a transparent premium appliance
- a serious compute object
- a machine with a point of view
- a board-centered monolith
- something that could plausibly appear in a grant deck, school feature, or founder profile

It should **not** feel like:

- a dev board in a clear box
- a student mounting frame
- a half-modeled enclosure
- a random AI gadget
- a generic mini-PC

## What Premium Means Here

For this specific CORA model, "premium" means:

- the acrylic has visual mass
- the perimeter frame feels polished and deliberate
- the standoffs feel like signature hardware, not placeholders
- the central compute region clearly dominates
- the board has enough memory, power, and SMD density to feel serious
- the I/O face is sparse, clean, and believable
- the object looks strong in `TOP`, `RIGHT`, `FRONT`, and `HOME`
- the exploded view explains the object cleanly

It does **not** mean:

- adding noise everywhere
- overloading the board with fake detail
- making the enclosure fully sealed and thermally absurd
- inventing a whole custom electronics stack inside this CAD file
- changing the file organization just to look cleaner

## Current Read Of The Model

What is already working:

- the acrylic monolith idea is visible
- the rounded perimeter frame is helping a lot
- the board is properly framed by the enclosure
- the object already has appliance energy instead of raw dev-board energy

What still needs to be upgraded:

- the board is still too sparse
- the main compute region is not dominant enough
- the standoffs still feel generic rather than signature hardware
- the I/O face needs cleaner hierarchy
- the board needs memory, power, and detail density
- the object still needs a stronger "hero render" read from the top and 3/4 views

## What Not To Touch Unless Necessary

Do not spend time here unless something is truly wrong:

- creating a schematic
- designing a real PCB layout
- changing the overall enclosure concept
- reorganizing the browser
- replacing the body-based structure with components
- adding lots of tiny underside detail no one will see
- creating extra ports just because space exists

The highest-leverage improvements from here are almost all visual and architectural.

## Working Rule

Do these sections one at a time.

Finish one section completely before starting the next.

Each section includes:

- the goal
- the exact Fusion actions
- the visual result you should get before moving on

## Recommended Starting Values

Use these unless the live model already looks better with a nearby value:

- board: `140 x 87 x 1.6 mm`
- plate footprint: `150 x 97 mm`
- plate thickness: `10 mm`
- plate corner fillet: `5 mm`
- perimeter ring thickness: `3.5 mm`
- gap below PCB: `8 mm`
- gap above PCB: `16 mm`
- standoff main diameter: `10 mm`
- standoff flange diameter: `14 mm`
- main compute package: `24 x 24 mm`

## Locked Browser Structure

Keep the current browser structure.

Do not convert the file into a component hierarchy just for cleanliness.
Do not rename the existing bodies, sketches, or named views just to match a different workflow.

Use the browser exactly as it already exists.

### Current key bodies

- `Bottom_Plate`
- `Top_Plate`
- `PCB_REF_PYNQ-Z2`
- `Standoff_FL`
- `Standoff_FR`
- `Standoff_BL`
- `Standoff_BR`
- `Flange_Bot_FL`
- `Flange_Bot_FR`
- `Flange_Bot_BL`
- `Flange_Bot_BR`
- `Flange_Top_FL`
- `Flange_Top_FR`
- `Flange_Top_BL`
- `Flange_Top_BR`
- `Connector_HDMI`
- `Connector_USB_A`
- `Connector_DC_Barrel`
- `Connector_MicroSD`
- `Connector_MicroUSB`
- `SoC_XC7Z020`
- `DDR3_Left`
- `DDR3_Bottom`
- `DDR3_Top`
- `DDR3_Right`
- `PowerIC_1`
- `PowerIC_2`
- `PowerInductor_1`
- `SMD_01` to `SMD_14`
- `Perimeter_Wall`

### Current key sketches

- `SK_Bottom_Plate`
- `SK_Bottom_M3`
- `SK_Bottom_Connectors`
- `SK_Top_Plate`
- `SK_Top_M3_Connectors`
- `SK_PCB`
- `SK_Flange_Bottom`
- `SK_Flange_Top`
- `SK_Standoff_Bore`
- `SK_Connectors`
- `SK_SoC_Memory`
- `SK_Power_SMD`
- `SK_Perimeter_Wall`
- `SK_IO_Face_Cuts`
- `SK_Service_Face_Cuts`
- `Sketch29` to `Sketch36`

### Current named views

- `TOP`
- `FRONT`
- `RIGHT`
- `HOME`

### Rule

If you add anything new, do it sparingly and append it to the current browser rather than reorganizing the whole file.

## 20 Upgrade Sections

Use the 20 sections in three passes:

- `Sections 1–6`
  - lock and polish the enclosure you already have
- `Sections 7–17`
  - make the board feel expensive, dense, and authored
- `Sections 18–20`
  - lock plausibility, presentation, and render readiness

### 1. Save a clean baseline and duplicate the current design

**Goal**

Create a safe checkpoint before you start pushing the model toward the premium version.

**Fusion actions**

1. Open the current CORA design.
2. Use `File > Save` to create a clean saved version.
3. If your workflow supports it, create a duplicate or new version named something like:
   - `CORA_V1_UPGRADE_PASS_01`
4. Do not overwrite the only working version.

**Done when**

- you have a safe rollback point
- you can now edit aggressively without fear

### 2. Keep the current browser and use it as the source of truth

**Goal**

Work inside the existing body/sketch organization without rebuilding the file structure.

**Fusion actions**

1. Leave the browser structure as it is.
2. Identify the current bodies you will actively edit:
   - `Bottom_Plate`
   - `Top_Plate`
   - `PCB_REF_PYNQ-Z2`
   - `Perimeter_Wall`
   - `Standoff_*`
   - `Flange_*`
   - `Connector_*`
   - `SoC_XC7Z020`
   - `DDR3_*`
   - `PowerIC_*`
   - `PowerInductor_1`
   - `SMD_*`
3. Identify the current sketches that drive those bodies:
   - `SK_Bottom_Plate`
   - `SK_Top_Plate`
   - `SK_PCB`
   - `SK_Flange_Bottom`
   - `SK_Flange_Top`
   - `SK_Standoff_Bore`
   - `SK_Connectors`
   - `SK_SoC_Memory`
   - `SK_Power_SMD`
   - `SK_Perimeter_Wall`
   - `SK_IO_Face_Cuts`
   - `SK_Service_Face_Cuts`
4. Do not migrate the model into components unless something breaks and absolutely forces it.

**Done when**

- you know exactly which existing bodies and sketches control the upgrade work
- the browser remains unchanged

### 3. Lock the reference dimensions before changing the look

**Goal**

Stop the model from drifting while you refine it.

**Fusion actions**

1. Open `SK_Bottom_Plate`.
2. Confirm or set:
   - plate length `150 mm`
   - plate width `97 mm`
3. Open `SK_Top_Plate`.
4. Confirm the top plate still matches the bottom plate footprint.
5. Open `SK_PCB`.
6. Confirm or set:
   - board length `140 mm`
   - board width `87 mm`
   - board thickness `1.6 mm`
7. Confirm the vertical stack by checking the current board elevation relative to the plates:
   - `8 mm` below the board
   - `16 mm` above the board

**Done when**

- the footprint and stack are intentional
- later edits will refine the object rather than re-invent it

### 4. Re-center the board and define the real internal composition

**Goal**

Make the PCB feel deliberately suspended inside the enclosure instead of merely placed there.

**Fusion actions**

1. Select `PCB_REF_PYNQ-Z2`.
2. Use `Modify > Move/Copy`.
3. In top view, center the board inside the acrylic footprint.
4. In side view, confirm the board sits at the locked height with `8 mm` below and `16 mm` above.
5. Use `Inspect > Section Analysis` if needed.

**Done when**

- the board sits mathematically centered
- the empty volume above and below feels balanced

### 5. Increase the authority of the acrylic plates

**Goal**

Make the acrylic read as expensive material, not thin sheet stock.

**Fusion actions**

1. Select `Top_Plate`.
2. Edit the plate extrusion to `10 mm` or `12 mm`.
3. Repeat for `Bottom_Plate`.
4. Use `Modify > Fillet` on the outer plan-view corners.
5. Start with `5 mm` on the major corners.
6. Add smaller edge fillets only if needed on exposed perimeter edges.

**Done when**

- the acrylic feels thick and architectural
- the object looks less fragile

### 6. Rebuild the perimeter ring as a premium enclosure frame

**Goal**

Turn the ring from "closure geometry" into "product silhouette."

**Fusion actions**

1. Select `Perimeter_Wall`.
2. Edit `SK_Perimeter_Wall` if needed.
3. Confirm the wall thickness is about `3.5 mm`.
4. Make sure the ring inner face does not crowd the board.
5. Use `Modify > Fillet` on the outer vertical corners.
6. Start with `4 mm`.
7. Add small top and bottom edge fillets around `1 mm` to `1.5 mm` if the ring still feels raw.

**Done when**

- the enclosure reads as one coherent monolith
- the frame no longer feels like a quick shell

### 7. Choose and commit to one primary I/O face

**Goal**

Give CORA a frontality.

**Fusion actions**

1. Use the edge that already carries the main connector cluster in the current `HOME` view as the primary I/O face.
2. Treat the `HDMI`, `USB-A`, and `DC barrel` side as the main public hardware face.
3. Treat the `MicroSD` and `MicroUSB` side as the quieter service face.
4. Do not move connectors to new sides unless the current layout is clearly broken.
5. Keep the service side visually quieter than the main I/O face.

**Done when**

- one side clearly reads as the interface side
- the object has orientation and product logic

### 8. Cut the I/O openings cleanly into the perimeter ring

**Goal**

Make the enclosure look manufactured around the connectors.

**Fusion actions**

1. Select `Perimeter_Wall`.
2. Open `SK_IO_Face_Cuts` for the main connector face.
3. Use `Create > Project/Include > Project` only if the current sketch needs refreshed connector references.
4. Edit the existing cutouts for:
   - HDMI
   - USB-A
   - power
5. Keep the cutouts rectangular, tight, and calm.
6. Leave about `0.75 mm` to `1.5 mm` clearance around each connector.
7. Finish the sketch.
8. Use `Extrude` with operation `Cut` through the ring.
9. Open `SK_Service_Face_Cuts` and refine the service-side openings for:
   - MicroSD
   - MicroUSB
10. Keep those service openings smaller and quieter than the main face.
11. Cut those through the ring only if they are meant to be externally accessible.

**Done when**

- connectors no longer appear to clip through acrylic
- the I/O face feels intentional and believable

### 9. Refine the existing standoffs into signature hardware

**Goal**

Make the corner hardware part of CORA's identity without changing the browser structure.

**Fusion actions**

1. Keep the existing corner-body structure:
   - `Standoff_FL`
   - `Standoff_FR`
   - `Standoff_BL`
   - `Standoff_BR`
   - `Flange_Bot_*`
   - `Flange_Top_*`
2. Open `SK_Flange_Bottom`, `SK_Flange_Top`, and `SK_Standoff_Bore`.
3. Refine the existing profile logic so the standoffs read more like precision hardware:
   - main diameter around `10 mm`
   - flange diameter around `14 mm`
   - slightly cleaner lip transitions
   - matching top and bottom visual weight
4. If one sketch controls all corners, use it as the master.
5. If the corners are independent bodies, repeat the same dimensional changes across all four corners manually.

**Done when**

- the standoffs feel like precision columns
- they no longer read like generic spacer tubes

### 10. Add top fastener detail and bottom foot logic

**Goal**

Give the corners believable assembly logic.

**Fusion actions**

1. Use the existing `Flange_Top_*` bodies to carry the top hardware read.
2. Sketch a centered circle on the top face of one top flange.
3. Use `Extrude > Cut` to create a shallow top recess for fastener logic.
4. Repeat the same recess on the other three top flanges.
5. Use the existing `Flange_Bot_*` bodies to refine the lower foot logic.
6. If you want more visual weight at the bottom, thicken or slightly widen the lower flange bodies instead of adding a separate new foot system.
7. Keep all four corners visually identical.

**Done when**

- the corners explain how the object is assembled
- CORA looks like it would sit properly on a desk

### 11. Make the central compute package dominate the board

**Goal**

Create a true focal point in top and 3/4 views.

**Fusion actions**

1. Select `SoC_XC7Z020`.
2. Edit the body or the sketch that drives it, most likely `SK_SoC_Memory`.
3. Push it toward `24 x 24 mm` or `26 x 26 mm` if needed.
4. Keep it centered.
5. Add a slight top-edge fillet or chamfer if it helps the package read better.
6. Make sure the SoC clearly dominates each single DDR package by eye.

**Done when**

- the board has a visual heart
- the top view feels much more serious immediately

### 12. Add the 4 memory packages around the compute core

**Goal**

Make the board feel dense and intentional.

**Fusion actions**

1. Use the existing memory bodies:
   - `DDR3_Left`
   - `DDR3_Bottom`
   - `DDR3_Top`
   - `DDR3_Right`
2. Edit them directly or use `SK_SoC_Memory` if it is driving the memory layout.
3. Preserve the current cross-like arrangement around `SoC_XC7Z020`.
4. Balance their spacing so the center zone feels dense and intentional.
5. Keep them close enough to feel coupled to the SoC without crowding it.

**Done when**

- the compute zone feels like a real high-value board area
- the top view gains immediate density

### 13. Build a real power-delivery cluster

**Goal**

Create a distinct subsystem on the board rather than a flat field of parts.

**Fusion actions**

1. Use the current power bodies as the base:
   - `PowerIC_1`
   - `PowerIC_2`
   - `PowerInductor_1`
2. Open `SK_Power_SMD`.
3. Refine the spacing and proportions of those bodies.
4. Bias the power cluster toward the side where it feels most plausible relative to the connector entry path.
5. Add any additional small power-detail bodies only if the area still feels too empty.
6. Keep the power zone denser than the rest of the board.

**Done when**

- the board clearly has a power subsystem
- the layout feels engineered, not random

### 14. Add support ICs and SMD banks

**Goal**

Move the board from sparse prototype to premium concept board.

**Fusion actions**

1. Use the current SMD bodies `SMD_01` through `SMD_14` as the active detail layer.
2. Reposition or resize them for cleaner banks using `Move/Copy` or by editing their source sketch if shared.
3. Arrange them in more disciplined rows near:
   - the compute region
   - the power zone
   - the I/O edge
4. Use these to reduce the obvious dead space that still exists around the center-left, lower-center, and right-side board zones.
5. Add only a few more small bodies if you truly need them, and append them after the current SMD list instead of reorganizing the browser.

**Done when**

- the board feels populated
- the empty dead zones are reduced

### 15. Draw the hero traces

**Goal**

Give the board a circuitry language that catches light and sells the concept.

**Fusion actions**

1. Start from one of the existing helper sketches such as `Sketch29` to `Sketch36`, or reuse `SK_SoC_Memory` only if doing so will not break current chip placement.
2. Place the sketch on the top face of `PCB_REF_PYNQ-Z2`.
3. Use `Line`, `Arc`, and `Sketch Fillet` to draw the main visible traces:
   - SoC to memory
   - SoC to power
   - SoC to I/O
4. Keep the trace routing elegant and organized.
5. If you want stronger richness, convert only the most important traces into shallow embossed or recessed geometry with a very small `Extrude`.
6. Prioritize traces that will actually read in `TOP` and `HOME` view.

**Done when**

- the board surface looks designed
- the top view feels much closer to the reference images

### 16. Refine the connector bodies on the board itself

**Goal**

Make the board edge read like real appliance hardware.

**Fusion actions**

1. Use the existing connector bodies:
   - `Connector_HDMI`
   - `Connector_USB_A`
   - `Connector_DC_Barrel`
   - `Connector_MicroSD`
   - `Connector_MicroUSB`
2. Clean up their block shapes and seating.
3. Make the HDMI, USB, power, and service port bodies feel crisp and properly seated on the PCB edge.
4. Reduce any oversized placeholder geometry.
5. Keep the I/O layout sparse and readable.
6. Make sure the main I/O face feels stronger and more public than the service face.

**Done when**

- the board edge looks curated
- the I/O face reads like a product, not placeholder geometry

### 17. Add the status LED and one quiet identity element

**Goal**

Give CORA life without cluttering the board.

**Fusion actions**

1. If you add these, append them to the existing browser rather than restructuring it.
2. Sketch a small LED body in the lower-central or lower-front zone of the board so it will read through the acrylic in `HOME` view.
3. Extrude it slightly.
4. Add one small quiet identity element:
   - `CORA`
   - a serial plate
   - a board revision block
5. Keep the text and plate minimal.

**Done when**

- the board has one clear emotional focal point
- the object begins to feel branded and alive

### 18. Tune spacing, thermal honesty, and visual breathing room

**Goal**

Make the object believable from side view and section view.

**Fusion actions**

1. Use `Inspect > Section Analysis`.
2. Confirm there is still:
   - `8 mm` below the board
   - `16 mm` above the board
3. Check the tallest connector and chip bodies against the top acrylic.
4. Make sure the perimeter ring is not pressing too close to the board edge.
5. If needed, add very subtle vent cues or internal breathing space rather than sealing the object like a dead acrylic brick.

**Done when**

- nothing looks mechanically impossible
- the object still feels premium and not thermally absurd

### 19. Create the review views inside Design

**Goal**

Judge the object like a product before switching to Render.

**Fusion actions**

1. Keep the current named views:
   - `TOP`
   - `FRONT`
   - `RIGHT`
   - `HOME`
2. Re-save them if needed after the geometry improves.
3. Use `HOME` as the main 3/4 review view if it already works well.
4. Add only new named views if a genuinely missing angle is needed.
5. Orbit through each and look for weak geometry.

**Done when**

- the object works from the top, side, and 3/4 views
- you can evaluate it like a real product sheet

### 20. Build the exploded view and freeze the geometry

**Goal**

Reach a stable design state that is ready for Render and concept-sheet export.

**Fusion actions**

1. Use `Move/Copy` on selected bodies, since this file is body-based rather than component-based.
2. Pull apart:
   - `Top_Plate`
   - `Perimeter_Wall`
   - `Standoff_*`
   - `Flange_*`
   - `PCB_REF_PYNQ-Z2`
   - connector bodies if they help the read
   - `Bottom_Plate`
3. Keep the exploded spacing aligned and restrained.
4. Save an exploded named view only if you need it for presentation.
5. Return to the assembled state and save again.
6. Do not reopen the fundamental silhouette after this unless something is actually broken.

**Done when**

- you have both the assembled hero object and the exploded concept-sheet view
- the design is ready to move into `Render`

## Final Standard

When these 20 sections are done, the model should no longer read like:

- a board fixture
- a dev board in acrylic
- an early CAD shell

It should read like:

- a transparent premium reasoning appliance
- a coherent CORA concept object
- something strong enough for a grant sheet, school feature, and hero render

## Done For 1517 When

You are done enough for the submission when all of the following are true:

- the enclosure feels complete and premium
- the board has a dominant compute core
- the memory, power, and SMD layers feel intentionally populated
- the main I/O face is clean and believable
- the service face is quieter and controlled
- the standoffs feel like signature hardware
- `TOP`, `FRONT`, `RIGHT`, and `HOME` all look strong
- you can generate:
  - one hero 3/4 render
  - one exploded render
  - one top or side technical render

At that point, stop refining the electronics fantasy and move to rendering and presentation.
