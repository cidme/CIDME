# CIDME Example 02 - Slightly less simple CIDME entity and entity context - annotated

This example builds upon the example described in (example 01)[example-01-simple_CIDME_entity_and_entity_context-annotated.md] and adds a few more features:
- Labels
- Entity context data

Full CIDME JSON-LD:

```json
{
  "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
  "@type": "Entity",
  "@id": "cidme://local/Entity/76a0d827-216b-43c1-ac74-e21161ce72c1",
  "metadata": [
    {
      "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
      "@type": "MetadataGroup",
      "@id": "cidme://local/MetadataGroup/3fd0738e-e5f8-4d87-81f7-478f914dcd33",
      "groupDataType": [
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "CreatedMetadata"
        }
      ],
      "data": [
        {
          "@context": {
            "@vocab": "http://purl.org/dc/terms/"
          },
          "created": "2020-06-28T20:38:26.035Z",
          "creator": null
        }
      ]
    },
    {
      "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
      "@type": "MetadataGroup",
      "@id": "cidme://local/MetadataGroup/20a45306-0bf8-4ab1-a56e-16914b60a756",
      "groupDataType": [
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "LastModifiedMetadata"
        }
      ],
      "data": [
        {
          "@context": {
            "@vocab": "http://purl.org/dc/terms/"
          },
          "modified": "2020-06-28T20:38:26.037Z",
          "creator": null
        }
      ]
    },
    {
      "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
      "@type": "MetadataGroup",
      "@id": "cidme://local/MetadataGroup/c729d415-8e08-4d61-ba9a-286bc7fb942e",
      "groupDataType": [
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "LabelMetadata"
        }
      ],
      "data": [
        {
          "@context": {
            "@vocab": "http://www.w3.org/2004/02/skos/core#"
          },
          "prefLabel": "CIDME Example Entity"
        }
      ]
    },
    {
      "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
      "@type": "MetadataGroup",
      "@id": "cidme://local/MetadataGroup/ab092690-4d9a-4b2b-bb6e-67815471a596",
      "groupDataType": [
        {
          "@context": "http://cidme.net/vocab/ext/0.1.0/jsonldcontext.json",
          "@type": "entityTypeMetadata"
        }
      ],
      "data": [
        {
          "@context": "http://cidme.net/vocab/ext/0.1.0/jsonldcontext.json",
          "entityType": "http://cidme.net/vocab/ext/0.1.0/ThingEntityType"
        }
      ]
    }
  ],
  "entityContexts": [
    {
      "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
      "@type": "EntityContext",
      "@id": "cidme://local/EntityContext/1b855da6-6011-495e-a204-e4dfef9149f2",
      "metadata": [
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "MetadataGroup",
          "@id": "cidme://local/MetadataGroup/aba90cd4-5629-43ff-afd7-101f7db44922",
          "groupDataType": [
            {
              "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
              "@type": "CreatedMetadata"
            }
          ],
          "data": [
            {
              "@context": {
                "@vocab": "http://purl.org/dc/terms/"
              },
              "created": "2020-06-28T20:38:26.038Z",
              "creator": null
            }
          ]
        },
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "MetadataGroup",
          "@id": "cidme://local/MetadataGroup/fb5cbdb0-e75f-48dc-af68-9132e7bbefea",
          "groupDataType": [
            {
              "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
              "@type": "LastModifiedMetadata"
            }
          ],
          "data": [
            {
              "@context": {
                "@vocab": "http://purl.org/dc/terms/"
              },
              "modified": "2020-06-28T20:38:26.039Z",
              "creator": null
            }
          ]
        }
      ]
    }
  ]
}
```
