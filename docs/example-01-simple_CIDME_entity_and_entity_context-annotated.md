# CIDME Example 01 - Simple CIDME entity and entity context - annotated

This example displays a somewhat minimal but yet complete CIDME entity and one entity context.  The only metadata included is the created and last modified information for each major node (Entity/EntityContext).

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

If we collapse the metadata and entityContexts arrays in the top-level CIDME Entity we're left with the following.  Anything in the metadata array is specific to this Entity node.  All top-level entity contexts reside in the entityContexts array.  Entity contexts may be nested, so entity contexts may have their own entity contexts and so on, *ad infinitum*.


```json
{
  "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
  "@type": "Entity",
  "@id": "cidme://local/Entity/76a0d827-216b-43c1-ac74-e21161ce72c1",
  "metadata": [],
  "entityContexts": []
}
```

As you can see, CIDME Entities aren't very useful, in-and-of themsevles, aside from being top-level placeholders.  

Remember, CIDME stands for ***C**ontextual **ID**entity **M**anagement **E**ngine*.  CIDME provides the following functions:
- Giving things an identity
- Providing context about those things
- Managing the above two items

The Entity gives *some thing* an identity.  Now, unless you create a QR code from the Entity @id and slap it on that *thing* (if that *thing* is even tangible) then it's hard to know what *thing* we're talking about.  We can provide hints in the form of metadata, but typically it'll be defined in the context.

Continuing on with our example... if we open the metadata array again we end up with two array elements.  Both are almost the same, with just two differences.  Firstly, each MetadataGroup has it's own unique @id.  Secondly, the first item relates to the created date/time of it's parent resource (the top-level Entity), while the second relates to the last modified date/time of the Entity resource.

```json
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
```

Let's collapse the groupDataType and data arrays:

```json
  "metadata": [
    {
      "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
      "@type": "MetadataGroup",
      "@id": "cidme://local/MetadataGroup/3fd0738e-e5f8-4d87-81f7-478f914dcd33",
      "groupDataType": [], 
      "data": []
    },
```

