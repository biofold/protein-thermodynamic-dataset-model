{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "https://github.com/biofold/protein-thermodynamic-dataset-model/blob/master/dataset_protein_variants.json",
  "title": "Protein Variants Dataset Schema",
  "type": "object",
  "properties": {
    "dataset": {
      "type": "object",
      "properties": {
        "name": { "type": "string" },
        "description": { "type": "string" },
        "version": { "type": "string" },
        "creation_date": { "type": "string" },
        "modification_date": { "type": "string" },
        "additional_info": { "type": "string" },
        "author": { "type": "string" },
        "records": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "_id": { "type": "string" },
              "record": { "$ref": "protein_variant.json" }
            },
            "required": ["_id", "record"]
          }
        },
        "reference": {
          "type": "object",
          "properties": {
            "publication": {
              "type": "string",
              "description": "Publication reference"
            },
            "PMID": {
              "type": "string",
              "pattern": "^[0-9]{8}$",
              "description": "PubMed Identifier (PMID) of the publication"
            },
            "DOI": {
              "type": "string",
              "description": "Digital Object Identifier (DOI) of the publication"
            }
          },
          "required": ["publication", "DOI"]
        }
      },
      "required": ["name", "records", "reference"]
    }
  },
  "required": ["dataset"]
}

