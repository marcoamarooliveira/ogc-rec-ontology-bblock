
# OGC Process Ontology (Model)

`ogc.inesctec.ontology.processOntology` *v1.0*

This Building Block represents the Ontology for the OGC API Processes schema, based on the results of the Iliad Project for a Registry of ApplicationPackages.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## My Schema

Defines a set of properties that may be used in **any** JSON schema.

> Note these properties may be used in the "properties" sub-component of a GeoJSON object, as a simple object

The numeric properties "b" and "c" have an example SHACL rule that if c is present, then c > b
## Examples

### This is an example with just a description and no code snippets.
This an example.

In **Markdown** format.
#### json
```json
{
  "geometry": {
    "coordinates": [
      [
        [
          -180.0,
          -90.0
        ],
        [
          180.0,
          -90.0
        ],
        [
          180.0,
          90.0
        ],
        [
          -180.0,
          90.0
        ],
        [
          -180.0,
          -90.0
        ]
      ]
    ],
    "type": "Polygon"
  },
  "type": "Feature",
  "properties": {
    "outputs": [
      {
        "format": "edam:format_3467",
        "id": "animation",
        "type": "File"
      }
    ],
    "registration_url": "https://pipe-drive.inesctec.pt/application-packages/tools/openoil-animation-duth/openoil_animation_duth_0_1_0.cwl",
    "programming_language": "python",
    "keywords": [
      "oil spill",
      "animation",
      "simulation",
      "openoil",
      "opendrift"
    ],
    "inputs": [
      {
        "format": "edam:format_3650",
        "doc": "The netcdf file containing the simulation results",
        "id": "file",
        "type": "File"
      }
    ],
    "description": "Animation of oil spill simulation",
    "maintainer": null,
    "sdPublisher": [
      {
        "name": "Application Package Registry",
        "class": "Organization",
        "url": "https://iliad-registry.inesctec.pt"
      }
    ],
    "temporal_coverage": null,
    "contributor": [
      {
        "name": "Miguel Correia",
        "email": "miguel.r.correia@inesctec.pt"
      }
    ],
    "spatial_coverage": {
      "geo": {
        "box": "-90 -180 90 180"
      },
      "class": "schema:GeoShape"
    },
    "id": "openoil_animation",
    "software_version": "0.1.0",
    "class": "CommandLineTool",
    "latest": false,
    "identifier": "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0",
    "citation": null,
    "date_created": "2025-11-14T22:12:16Z",
    "author": [
      {
        "name": "Georgios Sylaios",
        "email": "gsylaios@env.duth.gr"
      },
      {
        "name": "Nikolaos Kokkos",
        "email": "nikolaoskokkos@gmail.com"
      }
    ],
    "sdDatePublished": "2025-11-14T22:15:36.109964Z",
    "url": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl",
    "license": null,
    "code_repository": null,
    "source_organization": [
      {
        "address": {
          "address_country": "PT"
        },
        "name": "INESCTEC",
        "url": "https://inesctec.pt"
      },
      {
        "address": {
          "address_country": "GR"
        },
        "name": "D.U.TH",
        "url": "https://env.duth.gr"
      }
    ],
    "name": "openoil_animation",
    "producer": [
      {
        "address": {
          "address_country": "GR"
        },
        "name": "D.U.TH",
        "url": "https://env.duth.gr"
      }
    ],
    "family": "urn:apkg:tool:d.u.th:gr:openoil_animation",
    "cwl": "cwlVersion: v1.2\n$namespaces:\n  s: https://schema.org/\n  cwltool: http://commonwl.org/cwltool#\n  edam: http://edamontology.org/\n$graph:\n- class: CommandLineTool\n  id: openoil_animation\n  baseCommand: python\n  arguments:\n  - /opt/animation.py\n  - --file\n  - valueFrom: $( inputs.file )\n  inputs:\n    file:\n      format: edam:format_3650\n      type: File\n      doc: The netcdf file containing the simulation results\n  outputs:\n    animation:\n      format: edam:format_3467\n      type: File\n      outputBinding:\n        glob: result/animation.gif\n  requirements:\n    NetworkAccess:\n      networkAccess: true\n    EnvVarRequirement:\n      envDef:\n        PATH: /opt/miniconda3/envs/opendrift/bin:/opt/conda/bin:/opt/conda/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin\n    ResourceRequirement: {}\n    InlineJavascriptRequirement: {}\n    DockerRequirement:\n      dockerPull: iliad-repository.inesctec.pt/openoil-animation-duth:0.1.0\n  s:name: openoil_animation\n  s:description: Animation of oil spill simulation\n  s:keywords:\n  - oil spill\n  - animation\n  - simulation\n  - openoil\n  - opendrift\n  s:programmingLanguage: python\n  s:softwareVersion: 0.1.0\n  s:producer:\n    class: s:Organization\n    s:name: D.U.TH\n    s:url: https://env.duth.gr\n    s:address:\n      class: s:PostalAddress\n      s:addressCountry: GR\n  s:sourceOrganization:\n  - class: s:Organization\n    s:name: INESCTEC\n    s:url: https://inesctec.pt\n    s:address:\n      class: s:PostalAddress\n      s:addressCountry: PT\n  - class: s:Organization\n    s:name: D.U.TH\n    s:url: https://env.duth.gr\n    s:address:\n      class: s:PostalAddress\n      s:addressCountry: GR\n  s:author:\n  - class: s:Person\n    s:name: Georgios Sylaios\n    s:email: gsylaios@env.duth.gr\n  - class: s:Person\n    s:name: Nikolaos Kokkos\n    s:email: nikolaoskokkos@gmail.com\n  s:contributor:\n  - class: s:Person\n    s:name: Miguel Correia\n    s:email: miguel.r.correia@inesctec.pt\n  s:dateCreated: '2025-11-14T22:12:16Z'\n  s:identifier: urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0\n  s:sdDatePublished: '2025-11-14T22:15:36.109964Z'\n  s:sdPublisher:\n    class: Organization\n    name: Application Package Registry\n    url: https://iliad-registry.inesctec.pt\n"
  },
  "id": "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0",
  "links": [
    {
      "type": "application/json",
      "rel": "root",
      "title": "The landing page of this server as JSON",
      "href": "https://iliad-registry.inesctec.pt?f=json"
    },
    {
      "type": "text/html",
      "rel": "root",
      "title": "The landing page of this server as HTML",
      "href": "https://iliad-registry.inesctec.pt?f=html"
    },
    {
      "rel": "self",
      "type": "application/geo+json",
      "title": "This document as GeoJSON",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=json"
    },
    {
      "rel": "alternate",
      "type": "application/ld+json",
      "title": "This document as RDF (JSON-LD)",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld"
    },
    {
      "rel": "alternate",
      "type": "application/ld+json",
      "title": "This document as RDF (JSON-LD) APKG V2",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld_v2"
    },
    {
      "rel": "alternate",
      "type": "text/html",
      "title": "This document as HTML",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=html"
    },
    {
      "type": "application/cwl+yaml",
      "rel": "alternate",
      "title": "This document as CWL (YAML)",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl"
    },
    {
      "type": "application/cwl+json",
      "rel": "alternate",
      "title": "This document as CWL (JSON)",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwljson"
    },
    {
      "rel": "collection",
      "type": "application/json",
      "title": "Application Packages",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg"
    },
    {
      "type": "text/html",
      "rel": "alternate",
      "title": "All versions of this document as HTML",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items?family=\"urn:apkg:tool:d.u.th:gr:openoil_animation\"&sortby=-software_version"
    },
    {
      "type": "application/json",
      "rel": "alternate",
      "title": "All versions of this document as JSON",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items?f=json&family=\"urn:apkg:tool:d.u.th:gr:openoil_animation\"&sortby=-software_version"
    },
    {
      "type": "application/json",
      "rel": "alternate",
      "title": "All versions of this document as RDF (JSON-LD)",
      "href": "https://iliad-registry.inesctec.pt/collections/apkg/items?f=jsonld&family=\"urn:apkg:tool:d.u.th:gr:openoil_animation\"&sortby=-software_version"
    }
  ]
}

```


### This is an example with just a description and no code snippets.
This an example.

In **Markdown** format.
#### jsonld
```jsonld
{
  "@context": {
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "dct": "http://purl.org/dc/terms/",
    "dcat": "http://www.w3.org/ns/dcat#",
    "adms": "http://www.w3.org/ns/adms#",
    "apkg-rec": "http://w3id.org/apkg/v2/record#",
    "apkg-pro": "http://w3id.org/apkg/v2/process#",
    "bf": "http://id.loc.gov/ontologies/bibframe/",
    "foaf": "http://xmlns.com/foaf/0.1/",
    "geo": "http://www.opengis.net/ont/geosparql#",
    "pav": "http://purl.org/pav/",
    "vcard": "http://www.w3.org/2006/vcard/ns#"
  },
  "@id": "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0",
  "@type": [
    "apkg-pro:Process",
    "apkg-rec:Record"
  ],
  "dct:identifier": "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0",
  "dcat:qualifiedRelation": [
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt?f=json",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "root",
      "apkg-rec:mediaType": "application/json",
      "dct:title": "The landing page of this server as JSON"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt?f=html",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "root",
      "apkg-rec:mediaType": "text/html",
      "dct:title": "The landing page of this server as HTML"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=json",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "self",
      "apkg-rec:mediaType": "application/geo+json",
      "dct:title": "This document as GeoJSON"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "application/ld+json",
      "dct:title": "This document as RDF (JSON-LD)"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld_v2",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "application/ld+json",
      "dct:title": "This document as RDF (JSON-LD) APKG V2"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=html",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "text/html",
      "dct:title": "This document as HTML"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "application/cwl+yaml",
      "dct:title": "This document as CWL (YAML)"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwljson",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "application/cwl+json",
      "dct:title": "This document as CWL (JSON)"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "collection",
      "apkg-rec:mediaType": "application/json",
      "dct:title": "Application Packages"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items?family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "text/html",
      "dct:title": "All versions of this document as HTML"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items?f=json&family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "application/json",
      "dct:title": "All versions of this document as JSON"
    },
    {
      "@type": "apkg-rec:Link",
      "apkg-rec:href": {
        "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items?f=jsonld&family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version",
        "@type": "xsd:anyURI"
      },
      "apkg-rec:rel": "alternate",
      "apkg-rec:mediaType": "application/json",
      "dct:title": "All versions of this document as RDF (JSON-LD)"
    }
  ],
  "dct:title": "openoil_animation",
  "dct:description": "Animation of oil spill simulation",
  "geo:hasGeometry": {
    "@type": "apkg-rec:Geometry",
    "apkg-rec:geometryType": "Polygon",
    "apkg-rec:coordinates": "[[[-180.0,-90.0],[180.0,-90.0],[180.0,90.0],[-180.0,90.0],[-180.0,-90.0]]]"
  },
  "dcat:keyword": [
    "oil spill",
    "animation",
    "simulation",
    "openoil",
    "opendrift"
  ],
  "apkg-pro:processID": "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0",
  "apkg-pro:familyID": "urn:apkg:tool:d.u.th:gr:openoil_animation",
  "pav:version": "0.1.0",
  "apkg-pro:dateCreated": {
    "@value": "2025-11-14T22:12:16Z",
    "@type": "xsd:dateTimeStamp"
  },
  "apkg-pro:registrationDate": {
    "@value": "2025-11-14T22:15:36.109Z",
    "@type": "xsd:dateTimeStamp"
  },
  "apkg-pro:isLatestVersion": {
    "@value": "false",
    "@type": "xsd:boolean"
  },
  "apkg-pro:cwlDescriptor": {
    "@type": "apkg-pro:CWLDescriptor",
    "apkg-pro:descriptorURL": {
      "@value": "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl",
      "@type": "xsd:anyURI"
    },
    "apkg-rec:mediaType": "application/cwl+yaml"
  },
  "dct:creator": [
    {
      "@type": "apkg-pro:Person",
      "foaf:name": "Georgios Sylaios",
      "vcard:hasEmail": {
        "@type": "apkg-rec:Email",
        "vcard:value": "gsylaios@env.duth.gr"
      }
    },
    {
      "@type": "apkg-pro:Person",
      "foaf:name": "Nikolaos Kokkos",
      "vcard:hasEmail": {
        "@type": "apkg-rec:Email",
        "vcard:value": "nikolaoskokkos@gmail.com"
      }
    }
  ],
  "dct:contributor": {
    "@type": "apkg-pro:Person",
    "foaf:name": "Miguel Correia",
    "vcard:hasEmail": {
      "@type": "apkg-rec:Email",
      "vcard:value": "miguel.r.correia@inesctec.pt"
    }
  },
  "dct:publisher": {
    "@type": "apkg-pro:Organisation",
    "skos:prefLabel": "Application Package Registry",
    "apkg-pro:homepage": {
      "@value": "https://iliad-registry.inesctec.pt",
      "@type": "xsd:anyURI"
    }
  },
  "apkg-pro:hasSourceOrganisation": [
    {
      "@type": "apkg-pro:Organisation",
      "skos:prefLabel": "INESCTEC",
      "apkg-pro:homepage": {
        "@value": "https://inesctec.pt",
        "@type": "xsd:anyURI"
      },
      "vcard:hasAddress": {
        "@type": "apkg-rec:Address",
        "vcard:country-name": "PT"
      }
    },
    {
      "@type": "apkg-pro:Organisation",
      "skos:prefLabel": "D.U.TH",
      "apkg-pro:homepage": {
        "@value": "https://env.duth.gr",
        "@type": "xsd:anyURI"
      },
      "vcard:hasAddress": {
        "@type": "apkg-rec:Address",
        "vcard:country-name": "GR"
      }
    }
  ],
  "apkg-pro:hasProducerOrganisation": {
    "@type": "apkg-pro:Organisation",
    "skos:prefLabel": "D.U.TH",
    "apkg-pro:homepage": {
      "@value": "https://env.duth.gr",
      "@type": "xsd:anyURI"
    },
    "vcard:hasAddress": {
      "@type": "apkg-rec:Address",
      "vcard:country-name": "GR"
    }
  },
  "bf:geographicCoverage": {
    "@type": "apkg-pro:SpatialCoverage",
    "geo:hasGeometry": {
      "@type": "apkg-pro:Geo",
      "apkg-pro:box": "-90 -180 90 180"
    },
    "apkg-pro:geoClass": "schema:GeoShape"
  },
  "apkg-pro:programmingLanguage": "python",
  "apkg-pro:originalURL": {
    "@value": "https://pipe-drive.inesctec.pt/application-packages/tools/openoil-animation-duth/openoil_animation_duth_0_1_0.cwl",
    "@type": "xsd:anyURI"
  },
  "apkg-pro:processClass": "CommandLineTool",
  "apkg-pro:hasInput": {
    "@type": "apkg-pro:Parameter",
    "dct:identifier": "file",
    "apkg-pro:parameterType": "File",
    "dct:description": "The netcdf file containing the simulation results",
    "apkg-pro:format": "edam:format_3650"
  },
  "apkg-pro:hasOutput": {
    "@type": "apkg-pro:Parameter",
    "dct:identifier": "animation",
    "apkg-pro:parameterType": "File",
    "apkg-pro:format": "edam:format_3467"
  }
}

```

#### ttl
```ttl
@prefix apkg-pro: <http://w3id.org/apkg/v2/process#> .
@prefix apkg-rec: <http://w3id.org/apkg/v2/record#> .
@prefix bf: <http://id.loc.gov/ontologies/bibframe/> .
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix pav: <http://purl.org/pav/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0> a apkg-pro:Process,
        apkg-rec:Record ;
    bf:geographicCoverage [ a apkg-pro:SpatialCoverage ;
            apkg-pro:geoClass "schema:GeoShape" ;
            geo:hasGeometry [ a apkg-pro:Geo ;
                    apkg-pro:box "-90 -180 90 180" ] ] ;
    dct:contributor [ a apkg-pro:Person ;
            vcard:hasEmail [ a apkg-rec:Email ;
                    vcard:value "miguel.r.correia@inesctec.pt" ] ;
            foaf:name "Miguel Correia" ] ;
    dct:creator [ a apkg-pro:Person ;
            vcard:hasEmail [ a apkg-rec:Email ;
                    vcard:value "nikolaoskokkos@gmail.com" ] ;
            foaf:name "Nikolaos Kokkos" ],
        [ a apkg-pro:Person ;
            vcard:hasEmail [ a apkg-rec:Email ;
                    vcard:value "gsylaios@env.duth.gr" ] ;
            foaf:name "Georgios Sylaios" ] ;
    dct:description "Animation of oil spill simulation" ;
    dct:identifier "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0" ;
    dct:publisher [ a apkg-pro:Organisation ;
            apkg-pro:homepage "https://iliad-registry.inesctec.pt"^^xsd:anyURI ;
            skos:prefLabel "Application Package Registry" ] ;
    dct:title "openoil_animation" ;
    pav:version "0.1.0" ;
    apkg-pro:cwlDescriptor [ a apkg-pro:CWLDescriptor ;
            apkg-pro:descriptorURL "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl"^^xsd:anyURI ;
            apkg-rec:mediaType "application/cwl+yaml" ] ;
    apkg-pro:dateCreated "2025-11-14T22:12:16Z"^^xsd:dateTimeStamp ;
    apkg-pro:familyID "urn:apkg:tool:d.u.th:gr:openoil_animation" ;
    apkg-pro:hasInput [ a apkg-pro:Parameter ;
            dct:description "The netcdf file containing the simulation results" ;
            dct:identifier "file" ;
            apkg-pro:format "edam:format_3650" ;
            apkg-pro:parameterType "File" ] ;
    apkg-pro:hasOutput [ a apkg-pro:Parameter ;
            dct:identifier "animation" ;
            apkg-pro:format "edam:format_3467" ;
            apkg-pro:parameterType "File" ] ;
    apkg-pro:hasProducerOrganisation [ a apkg-pro:Organisation ;
            apkg-pro:homepage "https://env.duth.gr"^^xsd:anyURI ;
            skos:prefLabel "D.U.TH" ;
            vcard:hasAddress [ a apkg-rec:Address ;
                    vcard:country-name "GR" ] ] ;
    apkg-pro:hasSourceOrganisation [ a apkg-pro:Organisation ;
            apkg-pro:homepage "https://inesctec.pt"^^xsd:anyURI ;
            skos:prefLabel "INESCTEC" ;
            vcard:hasAddress [ a apkg-rec:Address ;
                    vcard:country-name "PT" ] ],
        [ a apkg-pro:Organisation ;
            apkg-pro:homepage "https://env.duth.gr"^^xsd:anyURI ;
            skos:prefLabel "D.U.TH" ;
            vcard:hasAddress [ a apkg-rec:Address ;
                    vcard:country-name "GR" ] ] ;
    apkg-pro:isLatestVersion false ;
    apkg-pro:originalURL "https://pipe-drive.inesctec.pt/application-packages/tools/openoil-animation-duth/openoil_animation_duth_0_1_0.cwl"^^xsd:anyURI ;
    apkg-pro:processClass "CommandLineTool" ;
    apkg-pro:processID "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0" ;
    apkg-pro:programmingLanguage "python" ;
    apkg-pro:registrationDate "2025-11-14T22:15:36.109Z"^^xsd:dateTimeStamp ;
    geo:hasGeometry [ a apkg-rec:Geometry ;
            apkg-rec:coordinates "[[[-180.0,-90.0],[180.0,-90.0],[180.0,90.0],[-180.0,90.0],[-180.0,-90.0]]]" ;
            apkg-rec:geometryType "Polygon" ] ;
    dcat:keyword "animation",
        "oil spill",
        "opendrift",
        "openoil",
        "simulation" ;
    dcat:qualifiedRelation [ a apkg-rec:Link ;
            dct:title "All versions of this document as RDF (JSON-LD)" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items?f=jsonld&family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version"^^xsd:anyURI ;
            apkg-rec:mediaType "application/json" ;
            apkg-rec:rel "alternate" ],
        [ a apkg-rec:Link ;
            dct:title "This document as GeoJSON" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=json"^^xsd:anyURI ;
            apkg-rec:mediaType "application/geo+json" ;
            apkg-rec:rel "self" ],
        [ a apkg-rec:Link ;
            dct:title "This document as CWL (YAML)" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl"^^xsd:anyURI ;
            apkg-rec:mediaType "application/cwl+yaml" ;
            apkg-rec:rel "alternate" ],
        [ a apkg-rec:Link ;
            dct:title "This document as CWL (JSON)" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwljson"^^xsd:anyURI ;
            apkg-rec:mediaType "application/cwl+json" ;
            apkg-rec:rel "alternate" ],
        [ a apkg-rec:Link ;
            dct:title "All versions of this document as HTML" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items?family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version"^^xsd:anyURI ;
            apkg-rec:mediaType "text/html" ;
            apkg-rec:rel "alternate" ],
        [ a apkg-rec:Link ;
            dct:title "This document as RDF (JSON-LD)" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld"^^xsd:anyURI ;
            apkg-rec:mediaType "application/ld+json" ;
            apkg-rec:rel "alternate" ],
        [ a apkg-rec:Link ;
            dct:title "The landing page of this server as JSON" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt?f=json"^^xsd:anyURI ;
            apkg-rec:mediaType "application/json" ;
            apkg-rec:rel "root" ],
        [ a apkg-rec:Link ;
            dct:title "This document as HTML" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=html"^^xsd:anyURI ;
            apkg-rec:mediaType "text/html" ;
            apkg-rec:rel "alternate" ],
        [ a apkg-rec:Link ;
            dct:title "Application Packages" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg"^^xsd:anyURI ;
            apkg-rec:mediaType "application/json" ;
            apkg-rec:rel "collection" ],
        [ a apkg-rec:Link ;
            dct:title "The landing page of this server as HTML" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt?f=html"^^xsd:anyURI ;
            apkg-rec:mediaType "text/html" ;
            apkg-rec:rel "root" ],
        [ a apkg-rec:Link ;
            dct:title "All versions of this document as JSON" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items?f=json&family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version"^^xsd:anyURI ;
            apkg-rec:mediaType "application/json" ;
            apkg-rec:rel "alternate" ],
        [ a apkg-rec:Link ;
            dct:title "This document as RDF (JSON-LD) APKG V2" ;
            apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld_v2"^^xsd:anyURI ;
            apkg-rec:mediaType "application/ld+json" ;
            apkg-rec:rel "alternate" ] .


```


### Examples can have content and/or code snippets.
The content of this example. 
#### rdf
```rdf
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix dcat: <http://www.w3.org/ns/dcat#> .
@prefix adms: <http://www.w3.org/ns/adms#> .
@prefix apkg-rec: <http://w3id.org/apkg/v2/record#> .
@prefix apkg-pro: <http://w3id.org/apkg/v2/process#> .
@prefix bf: <http://id.loc.gov/ontologies/bibframe/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix geo: <http://www.opengis.net/ont/geosparql#> .
@prefix pav: <http://purl.org/pav/> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .

# Converted from urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0
# following the APKG-LDAP v2 application profile (SCRIPTS/json2rdf.py).

<urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0> a apkg-pro:Process, apkg-rec:Record ;
    dct:identifier "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0" ;
    dcat:qualifiedRelation [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt?f=json"^^xsd:anyURI ;
        apkg-rec:rel "root" ;
        apkg-rec:mediaType "application/json" ;
        dct:title "The landing page of this server as JSON"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt?f=html"^^xsd:anyURI ;
        apkg-rec:rel "root" ;
        apkg-rec:mediaType "text/html" ;
        dct:title "The landing page of this server as HTML"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=json"^^xsd:anyURI ;
        apkg-rec:rel "self" ;
        apkg-rec:mediaType "application/geo+json" ;
        dct:title "This document as GeoJSON"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "application/ld+json" ;
        dct:title "This document as RDF (JSON-LD)"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=jsonld_v2"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "application/ld+json" ;
        dct:title "This document as RDF (JSON-LD) APKG V2"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=html"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "text/html" ;
        dct:title "This document as HTML"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "application/cwl+yaml" ;
        dct:title "This document as CWL (YAML)"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwljson"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "application/cwl+json" ;
        dct:title "This document as CWL (JSON)"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg"^^xsd:anyURI ;
        apkg-rec:rel "collection" ;
        apkg-rec:mediaType "application/json" ;
        dct:title "Application Packages"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items?family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "text/html" ;
        dct:title "All versions of this document as HTML"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items?f=json&family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "application/json" ;
        dct:title "All versions of this document as JSON"
    ], [
        a apkg-rec:Link ;
        apkg-rec:href "https://iliad-registry.inesctec.pt/collections/apkg/items?f=jsonld&family=%22urn:apkg:tool:d.u.th:gr:openoil_animation%22&sortby=-software_version"^^xsd:anyURI ;
        apkg-rec:rel "alternate" ;
        apkg-rec:mediaType "application/json" ;
        dct:title "All versions of this document as RDF (JSON-LD)"
    ] ;
    dct:title "openoil_animation" ;
    dct:description "Animation of oil spill simulation" ;
    geo:hasGeometry [
        a apkg-rec:Geometry ;
        apkg-rec:geometryType "Polygon" ;
        apkg-rec:coordinates "[[[-180.0,-90.0],[180.0,-90.0],[180.0,90.0],[-180.0,90.0],[-180.0,-90.0]]]"
    ] ;
    dcat:keyword "oil spill", "animation", "simulation", "openoil", "opendrift" ;
    apkg-pro:processID "urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0" ;
    apkg-pro:familyID "urn:apkg:tool:d.u.th:gr:openoil_animation" ;
    pav:version "0.1.0" ;
    apkg-pro:dateCreated "2025-11-14T22:12:16Z"^^xsd:dateTimeStamp ;
    apkg-pro:registrationDate "2025-11-14T22:15:36.109Z"^^xsd:dateTimeStamp ;
    apkg-pro:isLatestVersion "false"^^xsd:boolean ;
    apkg-pro:cwlDescriptor [
        a apkg-pro:CWLDescriptor ;
        apkg-pro:descriptorURL "https://iliad-registry.inesctec.pt/collections/apkg/items/urn:apkg:tool:d.u.th:gr:openoil_animation:0.1.0?f=cwl"^^xsd:anyURI ;
        apkg-rec:mediaType "application/cwl+yaml"
    ] ;
    dct:creator [
        a apkg-pro:Person ;
        foaf:name "Georgios Sylaios" ;
        vcard:hasEmail [
            a apkg-rec:Email ;
            vcard:value "gsylaios@env.duth.gr"
        ]
    ], [
        a apkg-pro:Person ;
        foaf:name "Nikolaos Kokkos" ;
        vcard:hasEmail [
            a apkg-rec:Email ;
            vcard:value "nikolaoskokkos@gmail.com"
        ]
    ] ;
    dct:contributor [
        a apkg-pro:Person ;
        foaf:name "Miguel Correia" ;
        vcard:hasEmail [
            a apkg-rec:Email ;
            vcard:value "miguel.r.correia@inesctec.pt"
        ]
    ] ;
    dct:publisher [
        a apkg-pro:Organisation ;
        skos:prefLabel "Application Package Registry" ;
        apkg-pro:homepage "https://iliad-registry.inesctec.pt"^^xsd:anyURI
    ] ;
    apkg-pro:hasSourceOrganisation [
        a apkg-pro:Organisation ;
        skos:prefLabel "INESCTEC" ;
        apkg-pro:homepage "https://inesctec.pt"^^xsd:anyURI ;
        vcard:hasAddress [
            a apkg-rec:Address ;
            vcard:country-name "PT"
        ]
    ], [
        a apkg-pro:Organisation ;
        skos:prefLabel "D.U.TH" ;
        apkg-pro:homepage "https://env.duth.gr"^^xsd:anyURI ;
        vcard:hasAddress [
            a apkg-rec:Address ;
            vcard:country-name "GR"
        ]
    ] ;
    apkg-pro:hasProducerOrganisation [
        a apkg-pro:Organisation ;
        skos:prefLabel "D.U.TH" ;
        apkg-pro:homepage "https://env.duth.gr"^^xsd:anyURI ;
        vcard:hasAddress [
            a apkg-rec:Address ;
            vcard:country-name "GR"
        ]
    ] ;
    bf:geographicCoverage [
        a apkg-pro:SpatialCoverage ;
        geo:hasGeometry [
            a apkg-pro:Geo ;
            apkg-pro:box "-90 -180 90 180"
        ] ;
        apkg-pro:geoClass "schema:GeoShape"
    ] ;
    apkg-pro:programmingLanguage "python" ;
    apkg-pro:originalURL "https://pipe-drive.inesctec.pt/application-packages/tools/openoil-animation-duth/openoil_animation_duth_0_1_0.cwl"^^xsd:anyURI ;
    apkg-pro:processClass "CommandLineTool" ;
    apkg-pro:hasInput [
        a apkg-pro:Parameter ;
        dct:identifier "file" ;
        apkg-pro:parameterType "File" ;
        dct:description "The netcdf file containing the simulation results" ;
        apkg-pro:format "edam:format_3650"
    ] ;
    apkg-pro:hasOutput [
        a apkg-pro:Parameter ;
        dct:identifier "animation" ;
        apkg-pro:parameterType "File" ;
        apkg-pro:format "edam:format_3467"
    ] .

```

## Sources

* [OGC API - Records, Part 1, ](https://docs.ogc.org/is/20-004r1/20-004r1.html)
* [OGC API - Process, Part 1, ](https://docs.ogc.org/is/18-062r2/18-062r2.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/marcoamarooliveira/ogc-rec-ontology-bblock](https://github.com/marcoamarooliveira/ogc-rec-ontology-bblock)
* Path: `_sources/processOntology`

