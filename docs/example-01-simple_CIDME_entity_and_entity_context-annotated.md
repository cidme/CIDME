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

Looks kinda similar to an Entity, huh?  Most of this is just basic JSON-LD... the items that begin with the **@** symbol.  
The groupDataType array may be used to provide an easily identifiable *type of data* that the data in the *data* array is about.

So we had the following in our groupDataType array:

```json
      "groupDataType": [
        {
          "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
          "@type": "CreatedMetadata"
        }
      ],
```

Again, another basic JSON-LD node.  If we look at the *@context* URI and dig out *CreatedMetadata* we arrive at this URI: [http://cidme.net/vocab/core/0.4.0/CreatedMetadata/CreatedMetadata.jsonld](http://cidme.net/vocab/core/0.4.0/CreatedMetadata/CreatedMetadata.jsonld) which explains that *CreatedMetadata*: *Identifies MetadataGroup resource as having information relating to the creation of the MetadataGroup parent resource.*

**Duh**

Care to take a guess what *LastModifiedMetadata* ends up being defined as?  Bingo.

So let's look at what's in the data array of the *MetadataGroup* JSON-LD node.

```json
      "data": [
        {
          "@context": {
            "@vocab": "http://purl.org/dc/terms/"
          },
          "created": "2020-06-28T20:38:26.035Z",
          "creator": null
        }
      ]
```

Here we have a *@vocab* in our JSON-LD context.  Here we're pointing to [*Dublin Core*](https://dublincore.org/).  Dublin Core defines the *Created* term as: *Date of creation of the resource.*.

So what this data is saying is that the parent resource of this MetadataGroup resource, which is our top-level CIDME Entity, was created on 6/28/2020 at 8:38PM UTC.

We also have a *Creator* item here, but it's null, so we don't actually know *who* is responsible for creating this CIDME Entity.

The other MetadataGroup resource for our top-level CIDME entity specified the same date/time, so we can infer that our CIDME entity has not been modified since it was initially created.

So why do we have a groupDataType array if it clearly states in the data array that this data is about it's creation?  The simple example is it provides a faster way to locate specific information.  In our example we're using Dublin Core, which is a great standard.  But using Dublin Core is not required.  What if someone wanted to use CIDME, but wanted to use in-house developed context / vocabularies?  Here they have that freedom.  But CIDME itself has a helpful method for clearly identifying that information via the groupDataType array.

At this point we know we have an entity (which identifies some *thing*) and it was created on 6/28/2020 at 8:38PM UTC.  Now what?

Next up we look at the entityContexts array element in the CIDME entity.  If we collapse the metadata, we get this:

```json
  "entityContexts": [
    {
      "@context": "http://cidme.net/vocab/core/0.4.0/jsonldcontext.json",
      "@type": "EntityContext",
      "@id": "cidme://local/EntityContext/1b855da6-6011-495e-a204-e4dfef9149f2",
      "metadata": []
    }
  ]
```

Look familiar?  Not really much different than our CIDME entity itself.  As this is a very minimalist CIDME example we've not provided a lot of other things... which will be further explained in better detail in the next examples!

The data in the metadata array is almost the same as for the CIDME entity itself.  We have created and last modified metadata.  Which the exact same values as our entity.  What's up with that?  Simply that our entity and entity context were created at the same time.  Nothing more or less.
