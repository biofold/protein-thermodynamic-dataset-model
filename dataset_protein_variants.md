# JSON Schemas Documentation

## Introduction
This repository includes JSON schemas for data models representing a dataset of protein thermodynamic data.

## License
Copyright (C) 2024 Emidio Capriotti and Maria Paola Turina

This program and all programs in this package are free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

## 1. Protein Variants Dataset

- **Title:** Protein Variants Dataset Schema
- **Description:** Defines the structure for a dataset containing information about protein variants.
- **Properties:**
  - `name`: Name of the dataset.
  - `description`: Description of the dataset.
  - `version`: Version of the dataset.
  - `creation_date`: Date when the dataset was created.
  - `modification_date`: Latest date when the dataset was modified.
  - `additional_info`: Additional information about the dataset.
  - `author`: Author of the dataset.
  - `records`: Array of protein variants.
    - `record`: Protein variant object.
      - `_id`: Identifier.
      - `cluster_id`: Cluster identifier.
      - `cluster_info`: Information about the clustering procedure.
      - `protein_variant`: Protein variant object.
  - `reference`: Information about the publication reference.
- **Required Fields:** `name`, `records`, `reference`

## 2. Protein Variant

- **Title:** Protein Variant Schema
- **Description:** Defines the structure for a protein variant.
- **Properties:**
  - `pdb_variant`, `predicted_structure_variant`, `uniprot_variant`, `alt_sequence_variant`: Different types of variants.
  - `thermodynamic_data`: Thermodynamic data related to the protein variant.
- **Required Fields:** Depends on the variant type.

## 3. Amino Acid Variant

- **Title:** Amino Acid Variant Schema
- **Description:** Defines the structure for an amino acid variant.
- **Properties:**
  - `uniprot_variant`, `alt_sequence_variant`, `pdb_variant`, `predicted_structure_variant`: Different types of variants.
- **Required Fields:** Depends on the variant type.

## 4. Thermodynamic Data

- **Title:** Thermodynamic Data Schema
- **Description:** Defines the structure for thermodynamic data.
- **Properties:**
  - Various properties including `Tm`, `unfolding_percentage`, `dG_H2O`, etc.
- **Required Fields:** `experiment` and at least one of `Tm`, `dG_H2O`, `ddG_H2O`, `dG`, `ddG`

## 5. Thermodynamic Experiment

- **Title:** Experiment Schema
- **Description:** Defines the structure for experimental data.
- **Properties:**
  - `method`: Method used for the experiment.
  - `conditions`: Experimental conditions such as temperature, pH, etc.
  - `reference`: Information about the publication reference.
  - `metadata`: Additional metadata about the experiment.
- **Required Fields:** `method`, `conditions`, `reference`

These schemas provide a standardized format for organizing and validating data related to protein variants, experimental data, and thermodynamic properties. Each schema is tailored to capture specific aspects of protein data analysis, ensuring consistency and compatibility across datasets.

