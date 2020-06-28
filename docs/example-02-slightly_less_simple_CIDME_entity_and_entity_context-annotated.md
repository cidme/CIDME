# CIDME Example 02 - Slightly less simple CIDME entity and entity context - annotated

This example builds upon the example described in [example 01](example-01-simple_CIDME_entity_and_entity_context-annotated.md) and adds a few more features:
- Label metadata
- Entity type metadata
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
      ],
      "entityContextData": [
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "EntityContextDataGroup",
          "@id": "cidme://local/EntityContextDataGroup/a9a5f72c-89cf-4e05-94b0-929cf01bad8c",
          "data": [
            {
              "@context": {
                "@vocab": "http://xmlns.com/foaf/0.1/"
              },
              "homepage": "https://github.com/cidme/CIDME/blob/master/docs/example-01-simple_CIDME_entity_and_entity_context-annotated.md"
            }
          ],
          "metadata": [
            {
              "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
              "@type": "MetadataGroup",
              "@id": "cidme://local/MetadataGroup/026fd089-a208-499b-856d-a1a0b0d726be",
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
              "@id": "cidme://local/MetadataGroup/23ac8746-f641-409d-bb72-25e8b16aa63b",
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
  ]
}
```

The first thing we're going to look at in this example is the third element of the metadata array of the top-most element, the CIDME entity.

```json
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
```

In the *groupDataType* array we're specifying this as *label metadata*.  In the *data* array we're providing a [*SKOS prefLabel*](https://www.w3.org/2009/08/skos-reference/skos.html#prefLabel), in otherwords - a preferred label.  This acts together to provide an easy-to-reference human-readable label for our CIDME entity.

Now we have a better idea of what this CIDME entity refers to.

The very next metadata array element is our next focus:

```json
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
```

In the *groupDataType* array we're specifying this as *entity type metadata*.  In the *data* array we're providing an entity type of *ThingEntityType*.

CIDME divides all entites into one of four categories:
- People
- Organizations
- Places
- Things

In the previous item we labeled this entity as our CIDME example entity.  It's not a person, organization, or place.  But it sure is a thing.  *Thing* covers a whole lot of ground... tangible and not.  In fact, it could be argued that people, organizations, and places are subsets of things.  But that being the case, what would you call something that's not a person, organization, or place??

Anyway, we've added some helpful info here.  When searching through CIDME entities, being able to filter by entity type can be extremely helpful.

Finally, in our entity context we have this (metadata removed for easier reading):

```json
      "entityContextData": [
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "EntityContextDataGroup",
          "@id": "cidme://local/EntityContextDataGroup/a9a5f72c-89cf-4e05-94b0-929cf01bad8c",
          "data": [
            {
              "@context": {
                "@vocab": "http://xmlns.com/foaf/0.1/"
              },
              "homepage": "https://github.com/cidme/CIDME/blob/master/docs/example-01-simple_CIDME_entity_and_entity_context-annotated.md"
            }
          ],
          "metadata": []
        }
      ]
```

Note that we don't have a groupDataType array here.  It's not required.  So in this example we're skipping it.  Could it help?  For sure.  Should it have one?  Likely. So why doesn't this one have it?  Because, for just one JSON-LD node, we're going to be rebels.  *Savor it*.

So what we're doing here is defining a [FOAF](http://www.foaf-project.org/) *homepage*.  We're saying the URL we've specified is the homepage for this thing.

