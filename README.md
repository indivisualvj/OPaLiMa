# Open Paraglider Line Map (OPaLiMa) Standard Documentation

## Overview

The Open Paraglider Line Map (OPaLiMa) standard is designed to systematically represent the detailed specifications of paraglider lines and configuration. It caters to a wide range of needs from manufacturers, repair services, and enthusiasts who seek a standardized format for documenting and sharing paraglider line information.

## Version

- **Standard Version**: opalima-alpha-1

## Structure

The OPaLiMa standard is structured into several key components, each designed to capture essential aspects of a paraglider's line architecture and specifications.

### Glider Variant

This section outlines the specific variant of the glider, including its model, manufacturer, and relevant tolerances.

- **name**: Identifier of the glider variant.
- **manufacturerTolerance**: The tolerance level set by the manufacturer, expressed in percentage.
- **gliderModel**: Detailed information about the glider model.
  - **gliderManufacturer**: Information about the manufacturer.
    - **name**: The short name of the manufacturer.
    - **fullName**: The full legal name of the manufacturing entity.
  - **checkIntervalAirtime**: The recommended airtime in hours before the glider should be checked.
  - **checkIntervalMonths**: The recommended interval in months for regular checks.
  - **name**: The model name of the glider.
  - **year**: The year the model was released.

### Sections

The sections component is a collection of grouped line information, segmented into different parts of the glider for detailed mapping.

- **position**: The sequential position of the section on the glider.
- **name**: The name or identifier of the section.
- **groups**: A collection of line groups within the section.
  - **position**: The position of the group within the section (if applicable).
  - **name**: The name or identifier of the group.
  - **knotSet**: Detailed information about the knots in the group.
    - **knotLengths**: A list of knots and their lengths.
      - **knot**: The knot number.
      - **length**: The length of the line at the knot, measured from the riser (can be negative for adjustments).
  - **offsetDesign**: The design offset for the group.
  - **rows**: A detailed breakdown of the rows within a group.
    - **position**: The position of the row within the group (if applicable).
    - **index**: The index of the row within the group.
    - **points**: Specific points within a row.
      - **position**: The position of the point within the row.
      - **name**: The name or identifier of the point.
      - **stabilo**: A boolean indicating if the point is a stabilo point.
      - **distanceToRiser**: The distance from the point to the riser, measured in millimeters.

## Example

Below is an example snippet from an OPaLiMa document detailing the glider variant and a section of its line map.

```yaml
gliderVariant:
  name: MS
  manufacturerTolerance: 10
  gliderModel:
    gliderManufacturer:
      name: Ozone
      fullName: 'Ozone Paragliders LTD'
    checkIntervalAirtime: 100
    checkIntervalMonths: 24
    name: 'Zeno 2'
    year: 2022
sections:
  - position: 1
    name: S1
    groups:
      - position: null
        name: AR1
        knotSet:
          knotLengths:
            - knot: 0
              length: 0
            - knot: 1
              length: -13
            # Additional knots omitted for brevity
        offsetDesign: 0
        rows:
          - position: null
            index: 0
            points:
              - position: 1
                name: A1a
                stabilo: false
                distanceToRiser: 7651
              # Additional points omitted for brevity
```

This example outlines the structure and information detail available in the OPaLiMa standard, demonstrating its capability to provide comprehensive and precise specifications for paraglider lines and configurations.
