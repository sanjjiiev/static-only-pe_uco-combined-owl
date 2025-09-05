The Static PE + UCO Combined Ontology is a domain-specific OWL ontology that integrates structural features of Windows Portable Executable (PE) files with the UCO framework for cyber threat intelligence, while excluding all dynamic/runtime features.

Purpose

To provide a knowledge representation of malware and benign PE files based purely on their static properties.
To enable semantic mapping between real-world datasets (e.g., Avast JSON dataset) and a cyber ontology.
To support reasoning, correlation, and knowledge graph building for static malware analysis.

What It Contains

PE Features (Static only):

File header attributes (e.g., Machine type, Number of sections, Characteristics)
Section table features (e.g., .text, .data, .rdata sizes, entropy, raw/virtual sizes)
Import/Export table (list of DLLs and functions statically declared)
Resource directory entries (icons, version info, manifests)
Strings present in the binary

UCO Concepts (Relevant Mappings):

uco-core:File → Represents the PE file as an object.
uco-observable:Executable → The PE file as an executable entity.
uco-observable:Section → Maps to PE sections.
uco-observable:Library → Represents imported DLLs.
uco-observable:Function → Represents imported/exported functions.
uco-types:Hash → For MD5/SHA256 static hash values.

Relationships Between Them:

hasSection links a PE file to its sections.
importsLibrary links to DLLs.
callsFunction links to API functions.
hasHash links to cryptographic identifiers.

What It Excludes

Any dynamic/runtime execution data (e.g., system calls, network traffic, process creation).
Any behavioral features (like API calls captured during sandbox execution).
Any time-series data (no CCA or runtime clustering features).

Applications

Static malware classification (benign vs malicious).
Ontology-based dataset mapping (e.g., Avast JSON → OWL).
Knowledge graph construction for threat intelligence.
Rule-based reasoning and semantic queries (SPARQL).
