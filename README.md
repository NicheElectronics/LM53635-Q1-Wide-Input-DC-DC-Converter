# LM53635-Q1 Wide-Input DC-DC Converter

A four-layer, **5 V / 3.5 A design-target** synchronous buck converter built around the Texas Instruments **LM53635-Q1**. The board is intended for a **6–36 V input** and provides a choice of direct or EMI-filtered input paths for evaluating power-supply behavior.

> **Status:** PCB design and PSpice simulation are complete. The board has not yet been fabricated or electrically validated. The voltage, current, efficiency and EMI performance described here are design goals, not measured results.

## At a glance

| Item | Design |
| --- | --- |
| Controller | TI LM53635-Q1 automotive synchronous step-down converter |
| Intended input | 6–36 V DC |
| Intended output | 5 V, up to 3.5 A design target |
| PCB | Four layers, designed in KiCad |
| Input options | Direct path and EMI-filtered path |
| Analysis | PSpice startup and steady-state/transient simulations |
| Hardware verification | Pending fabrication and bench measurements |

The **6–36 V** range is this board's intended range. The IC's own operating limits and transient ratings are specified in the [TI LM53635-Q1 datasheet](https://www.ti.com/product/LM53635-Q1); they should not be treated as a measured rating of the assembled board.

## Design overview

```mermaid
flowchart LR
    VIN["6–36 V input"] --> PATH["Direct or filtered input"]
    PATH --> BUCK["LM53635-Q1 buck stage"]
    BUCK --> OUT["5 V output"]
```

The layout emphasizes a compact switching-current loop, local decoupling, sensible AGND/GND handling, input filtering and accessible measurement points. The filtered and direct input options support comparison during later EMI and transient testing. The project files include KiCad hardware data, manufacturing outputs, board renders and PSpice work; consult those source files for exact component values and connector pinouts.

## Simulation and validation

Startup and transient behavior have been examined in **PSpice for TI**. Simulation helps check the design before fabrication but does not establish hardware output ripple, efficiency, thermal behavior or emissions.

Once a board is assembled, the planned checks are:

1. Inspect assembly, polarity and resistance between each power rail and ground.
2. Power the board from a current-limited bench supply and verify the 5 V output at light load.
3. Check startup and output regulation across the intended input range and representative loads.
4. Measure ripple, load-transient response and component temperature; record the instruments and test conditions.
5. Compare direct and filtered input paths and evaluate conducted EMI with a suitable measurement setup.

No bench measurements or compliance results are claimed at this stage.

## Design files and reference

The repository contains the schematic, PCB design, manufacturing material, renders and simulation results. Use the **KiCad source files** as the authority for the actual revision and the [TI datasheet](https://www.ti.com/product/LM53635-Q1) for device limits and recommended layout practice.

## Author

**Nishant Patil**

No license has been specified for the project files. Add one if you want to define reuse terms.
