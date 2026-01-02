# Physical Design – RTL to GDS using OpenLane

This directory contains the complete RTL to GDS-II physical design implementation of an 8-bit Arithmetic Logic Unit (ALU) using the OpenLane automated ASIC flow and the Sky130 open-source PDK.

The objective of this stage was to transform a synthesized gate-level netlist into a manufacturable GDS-II layout while meeting timing, area, and design rule constraints.


## Toolchain Used
- OpenLane – End-to-end RTL to GDS automation
- OpenROAD – Floorplanning, placement, CTS, routing
- OpenSTA – Static Timing Analysis
- Magic – Layout visualization and DRC
- KLayout – GDS inspection
- PDK – Sky130 (sky130_fd_sc_hd standard cell library)


## Design Configuration
- Top Module: ALU_8bit
- Clock Port: clk
- Target Clock Period: 10 ns
- Target Frequency: 100 MHz
- Process Node: Sky130 (130 nm)
- Standard Cell Library: sky130_fd_sc_hd


## Physical Design Metrics

| Metric | Value |
|------|------|
| Flow Status | Completed Successfully |
| Total Standard Cells | 1,675 |
| Core Area | 12,011.52 µm² |
| Die Area | 0.01609 mm² |
| Core Utilization | ~48 % |
| Final Utilization | ~55 % |
| Total Wire Length | 15,136 µm |
| Total Vias | 4,371 |
| Worst Negative Slack (WNS) | 0 ns |
| Total Negative Slack (TNS) | 0 |
| DRC Violations | 0 |
| LVS Errors | 0 |
| Antenna Violations | 0 |
| Final Output | GDS-II Generated |


## Layout Snapshots

### Floorplan
![Floorplan](Screenshots/floorplan.png)

### Placement
![Placement](Screenshots/placement.png)

### Final Routed Layout (GDS-II)
![Final GDS](Screenshots/gds_full_chip.png)

### Zoomed View – Standard Cells
![Zoomed Layout](Screenshots/gds_zoom_standard_cells.png)


## Signoff Summary
- Timing closure achieved with zero negative slack
- No DRC, LVS, or antenna violations reported
- Routing completed successfully with balanced metal utilization
- A clean, manufacturable GDS-II was generated


## Generated Outputs
- GDS-II
- DEF
- LEF
- SPEF
- SDC
- Gate-level Verilog netlist


## Key Takeaways
- Demonstrates complete RTL to GDS ASIC flow
- Highlights understanding of physical design metrics and signoff
- Validates use of open-source EDA tools for industry-relevant design


