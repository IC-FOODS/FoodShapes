#### Key value pairs needed to capture information about a sample of milk

- SampleID
- Source Organism (uses NCBI taxonomy)-- 
    - Genus eg bos
    - Species eg taurus
- Organoleptic properties
    - Aroma (the "nasal appearance"): multiple terms from a controlled vocabulary (uses UC_Sense perceived Odor) 
        - can be multiple aromas
        - e.g. perceived butterscotch odor, perceived burnt odor
    - Taste: all characteristics might not be present but there are no other properties can be multiple values from:
        - Sweetness: as per a scale
        - Sourness: as per a scale
        - Bitterness: as per a scale
        - Saltiness: as per a scale
        - Umami: as per a scale
    - Texture: controlled vocabulary from uc_Sense perceived_Texture:  
    - Mouth Feel: controlled vocabulary from uc_Sense perceived_Mouthfeel e.g. perceived chewiness, perceived astringency
    - VisualAppearance:
        - Color
        - Opaqueness
- Physical properties:
    - Density
    - Freezing Point
    - Acid-base Equilibria
    - Viscosity
    - Volume
    - Optical Properties
        - Color: what wavelengths (spectrometer reading)
        -Absorbance:
    - Temperature
- Chemical Components:
    - Molecules (classes of molecules)
        - Lipids 
        - Carbohydrates:
            - total carbohydrates 
                - value and unit e.g. 2 grams
            - individual carbohydrates 
                - sequence string, value, and units from https://tinyurl.com/yaxhwygf
        - Free amino acids
        - Peptides: sequence string and amount value, and unit 
        - e.g. from values at https://tinyurl.com/yaxhwygf
            - 
        - 
    - phValue value as per pH scale
    - Xenobiotics
- Biological Components:
    - Microbiological

#### Molecular entity properties

* accession (and source it refers to)
* prefName, altName
* description
* organism (in particular, NCBITax ID)
* provenance (URI or string)

#### Properties from gene, protein

* sequence, chromosome, begin, end

#### Relations to other entities

* ontology annotation/xref (GO, trait ontology, phenotype ontology)
* associated with
* encodes
* part-of (eg, pathway, molecular complex)
* input-of/output-of (eg, reaction, pathway)

