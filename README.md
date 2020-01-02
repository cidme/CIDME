![CIDME project banner logo - dual](logos/cidme-banner_logo-dual-750x150.png "CIDME project banner logo - dual")
![CIDME GitHub repo QR code - cidme://public/EntityContext/f35b23ca-27a9-4724-b047-e8a5c7267db1](logos/cidme-github_repo-qr_code-350x350.png "CIDME GitHub repo QR code - cidme://public/EntityContext/f35b23ca-27a9-4724-b047-e8a5c7267db1")

CIDME GitHub repository CIDME ID/URL: _cidme://public/EntityContext/f35b23ca-27a9-4724-b047-e8a5c7267db1_

# CIDME (_Pronounced SID-MEE_)
_**C**ontextual **ID**entity **M**anagement **E**ngine (**CIDME**)_: Giving an identity to, and storing contextualized information about people, organizations, places, and things.   Your knowledge, _connected_.

📌⛔⚠ **_IMPORTANT NOTE:_ This project is in it's very early stages.  Therefore anything in this document may change at any time, and any information in this document may also be incorrect or outdated at any point!!!**

<a name="toc"/></a>
## Table of Contents

* [Summary](#summary)
* [Intended audience](#audience)
* [Introduction](#intro)
* [Why the name *CIDME*?](#whythename)
* [Current project status](#status)
* [Documentation](#docs)
* [Entity Relationship Diagram (*ERD*)](#erd)
* [Other projects making use of *CIDME*](#otherprojects)
* [Who is "*we*"?](#whoiswe)
* [Who is *Joe Thielen*?](#joethielen)


<a name="summary"/></a>
## Summary
CIDME is an umbrella software project which encompasses a set of specifications as well as implementations of those specifications.  The specifications deal with giving an identity to, and storing contextualized information about people, organizations, places, and things.  In CIDME these are referred to as entities.

[*Back to TOC*](#toc)


<a name="audience"/></a>
## Intended audience
CIDME is not meant for use by non-developer end-users.  CIDME is not an app, nor a program.  CIDME is for use by other software developers / projects and is meant to be built upon.  Many software projects, from the smallest batch scripts to the largest enterprise implementations, need a way to store information about various entities (people, organizations, places, and things).  CIDME is an attempt to standardize how this is done, creating a re-usable means to do so, allowing other software developers / projects to save time in not having to re-create this functionality while also allowing for a means for sharing this information in a standardized manner.

[*Back to TOC*](#toc)


<a name="intro"/></a>
## Introduction
CIDME is an umbrella software project which encompasses a set of specifications as well as implementations of those specifications.  The specifications deal with giving an identity to, and storing information about entities - people, organizations, places, and things.

In many cases, existing software projects attempt to lump all information about an entity into one place, when instead that information may be better separated into distinct parts, while still maintaining links to each other, forming parts of a whole.  Contact information, for example.  Let's give an example where a person has multiple jobs.  They may have many phone numbers and email addresses, especially over time.  A personal-use set of contact information, one set for one job, and still another set for the other job!  The address books and contact managers we currently use tend to not easily allow us to manage information this way.  You have no idea if a number is attached to a given job... only that it's labeled as 'work'.   Additionally, as people drop old numbers and addresses and adopt new ones, history becomes muddled.  When looking through old emails you may come across a cryptic address (ed209@example.com) and wonder, who was that?  The context has been lost.  You've since deleted that email address from your contact manager because the person doesn't use it any more.  You don't want to keep it listed for fear of accidentally sending a new email to that old address.  But wouldn't it be nice to still have a way to keep it somewhere for posterity?

CIDME allows you to keep this infordf base64 xsd:base64Binaryrmation, group it, and give it context.  Here, we can create at least three contexts... one for personal-use information, and one for each of the two jobs.  You can then associate their personal/private contact information with the personal one, then the relevant items with the appropriate job-related contexts.  When this person switches jobs you can still keep this information, but give it a date-range, so you know it was only valid at that time.  You can also give it an inactive status, so it does not show up as an available address when creating new emails, sending texts, or making a phone call.  The end result is you can go back and look up ed209@example.com and note it related to our example person, and the fact that they used it while working at a certain job during a given time (date range), but know to not use this information for new contacts with this person.  CIDME gives context to this identity information.

CIDME is all about managing this information.  Not simply just at one given point in time, but also managing information as it ages and/or about an entity's state at different points in time.  For example, both people and organizations change their names or contact information.  Instead of just deleting or changing the existing information in your system about these entities, CIDME allows you to keep it, referencing it by dates in time or status (active/inactive).  CIDME also allows for structured archiving and/or purging of old information.  CIDME can be referred to as an engine to manage this information.

Hence the CIDME project acronym:  Contextualized IDentity Management Engine.

At the heart of CIDME are the entities and entity contexts.  These are realized via JSON-LD serialized strings (RDF can also be used) and are referred to as resources.  These resources themselves are natively operating system and programming language agnostic.  This means any programming language which has support for JSON and/or JSON-LD has the functionality necessary to deal with CIDME resources. 

An *extremely minimial* example of a CIDME entity resource for purely illustrative purposes:
```json
{
    "@context": "http://cidme.net/vocab/0.2.0/jsonldcontext.json",
    "@type": "Entity",
    "@id": "cidme://local/Entity/db9b4bdb-50b7-483d-95a6-b3884ecd4137"
}
```

As CIDME resources are just strings, they may be stored in many different ways.  The CIDME project was envisioned to be able to be used by a very, very wide audience of developers on an equally wide variety of platforms.  CIDME resources may be used on embedded platforms with very limited computational power and memory.   Likewise they may be used on extremely scaled up scenarios involving databases of millions upon millions of resources.

Additionally, CIDME may be used in very simple ways, such as by a single developer working on a small home-brew project involving batch/shell scripts.  However, it can also be scaled up for use in complex scenarios involving AI with semantic understanding of the linked data!

CIDME usage examples... CIDME does not necessarily DO all of the these items, but it does provide a standardized way of managing data that can enable these types of systems.

Simple:
* Storage of a user list for one application.
* Contact/personal information (PIM) management / storage.
* A method to provide a (structured/standardized) identity to nearly any type of object, tangible or not.
* A way to add standardized/structured metadata to files in a file system.
  * Pictures and video as well.
  * Can also link subjects within the pictures and video to contacts.

Intermediate:
* Centralized storage of user / contact / entity management for multiple simultaneous applications.
  * Similar to a implementations of LDAP / Active Directory, while providing context functionality.
* A personal or professional Farley File
  * https://en.m.wikipedia.org/wiki/Farley_file
* Linking real world objects to metadata via QR codes.
  * Have CIDME entity or entity context ID placed in the QR code as a URL.
  * This QR code may provide a public CIDME ID.  The entity scanning the QR code can create a new local entity and link the local one to the public one.  Now the entity has its own copy for posterity and can add any data wished and/or link to other entities.

Complex:
* Usage in an AI-based system involving semantic and linked big data.


[*Back to TOC*](#toc)


<a name="whythename"/></a>
## Why the name *CIDME*?

After putting a considerable amount of thought into what this project was to be, as well as what it was not, the CIDME acronym was chosen as it's contents best accurately describes what the project provides.  An _engine_ to _manage contextualized identity_ information.  

The only other major usage of the term which turns up during web searches is a Dental clinic in Spain.  I figured the acronym was unique enough to use and build upon for a software project.

[*Back to TOC*](#toc)


<a name="status"/></a>
## Current project status

* The project was first created in October 2016 and has undergone several major foundational changes.
* As of Jan 2020 the project focus is creating the specifications and an implementation of the core engine in JavaScript.
* Actual code (_all currently in **alpha** stages!_):
  * [vocabulary definition files](http://cidme.net/vocab).  
    * See the [*gh-pages* branch of the CIDME GitHub repository](https://github.com/cidme/CIDME/tree/gh-pages) to find the vocab directory.
  * [JavaScript/TypeScript CIDME Core implementation](http://github.com/cidme/CIDME-JS).
  * [JavaScript/Node-based Command-Line Interface (CLI) for CIDME Core](http://github.com/cidme/CIDME-CLI).
  * [CIDME UI extensions](http://github.com/cidme/CIDME-UI).

[*Back to TOC*](#toc)


<a name="docs"/></a>
## Documentation

This document serves as an overview of the various parts of the CIDME project.  There are a few different GitHub repositories for more  information on specific portions:

* [CIDME/CIDME-Core-Spec](http://github.com/CIDME/CIDME-Core-Spec) - The CIDME Core specification.
* [CIDME/CIDME-Ext-Spec](http://github.com/CIDME/CIDME-Ext-Spec) - The CIDME Recommended Extensions specification.
* [CIDME/CIDME-JS](http://github.com/CIDME/CIDME-JS) - The JavaScript (TypeScript) CIDME implementation.
* [CIDME/CIDME-CLI](http://github.com/CIDME/CIDME-CLI) - The Node-based CIDME CLI.
* [CIDME/CIDME-UI](http://github.com/CIDME/CIDME-UI) - User interface extensions for CIDME.

Aside from these repositories, please refer to the [vocabulary definition files](http://cidme.net/vocab).  See the [*gh-pages* branch of the CIDME GitHub repository](https://github.com/cidme/CIDME/tree/gh-pages) to find the vocab directory.

There is also a [project wiki](../../wiki/), but it currently has limited information.


[*Back to TOC*](#toc)


<a name="erd"/></a>
## Entity Relationship Diagram (*ERD*)

**NOTE - This is a DRAFT and may change at any time!**

![DRAFT CIDME ERD](/docs/CIDME-Entity_Rel_Diagram-DRAFT.png "DRAFT CIDME ERD")
[Click here to view the entire diagram/file](/docs/CIDME-Entity_Rel_Diagram-DRAFT.png)

[*Back to TOC*](#toc)


<a name="otherprojects"/></a>
## Other projects making use of CIDME

* [IMSFAY](http://www.github.com/IMSFAY/IMSFAY) - *Information Management System for Families, Adults, and Youth* 
  * Now a defunct project, used a previous prototype version of CIDME created with PHP and the Neo4j graphing database.

[*Back to TOC*](#toc)


<a name="whoiswe"/></a>
## Who is behind CIDME?

Well, um, currently, it's just me, Joe Thielen, project creator.  But I'm hoping in time the project will grow and be joined by other individuals who share similar beliefs in the project goals / guidelines.

Please, *feel free* to drop me a line!  I've created this project on GitHub specifically to help attract attention and make the project larger than myself.

[*Back to TOC*](#toc)


<a name="joethielen"/></a>
## Who is *Joe Thielen*?

I've been creating fairly complex, but monolithic, LAMP apps for both non- and for-profit companies for over 25 years.  My experience lies with small- and medium- sized organizations / businesses in the USA.  Most of these apps have, in one form or another, made heavy use of, or even dealt primarily with, contact / identity information.  The genesis of this project was to create a separate piece of software to provide this functionality, so as to be able to be used by other software projects.

View my [LinkedIn Profile](https://www.linkedin.com/in/joethielen) for more professional (*or lack thereof*) information.


[*Back to TOC*](#toc)
