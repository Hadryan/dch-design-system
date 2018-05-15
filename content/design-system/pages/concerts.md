---
title: Concerts
---

#### Page

# Concerts

{{% tabs %}}

{{% tab "Overview" %}}

![A sample concerts page](/images/pages/Concerts.jpg)

## Overview

This is the main entry point for users who want to browse our archive, as well as check on upcoming live concerts. It should be seen as a space for curated content rather than a warehouse of information. Make use of **Content Lists** for this purpose.


## Goals

* Expose users to fresh/recently added content
* Draw attention to upcoming live presentations and capture viewers
* Display evergreen content in inviting and creative ways
* Encourage exploration of archive

## Breakdown

_here should we list the specific contents of the content lists for example?_

{{% /tab %}}

{{% tab "Specs" %}}

If the interface offers a space for section titles, as in the mobile app ui, use the label [DCH\_navigation\_concerts](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=68c70d893e366b8021fcd494351255da&amp;source_locale_id=cbf486802fbde9dad58791462c894217&amp;target_locale_id=cbf486802fbde9dad58791462c894217&amp;show_changes=false&amp;search=eyJmaWx0ZXJzIjpbIiIsInRyYW5zbGF0ZWQiLCJ1bnRyYW5zbGF0ZWQiLCJleGNsdWRlZCIsImluY2x1ZGVkIiwidW52ZXJpZmllZCIsInZlcmlmaWVkIiwicGx1cmFsaXplZCIsInVucGx1cmFsaXplZCJdLCJxdWVyeSI6IkRDSF9uYXZpZ2F0aW9uKiIsInNvcnRpbmciOiJzY29yZSIsImxvY2FsZV9pZCI6IjJlM2ViM2ZiYmM4ZjEwZGE2ZjY0OTc3NmFmNzYxYmM5In0%3D&amp;next_translation_key_id=10cc98d088adbddfa1e64f7a6638e850).

## [Featured Content Area](Design System/components/Featured Content Area)

Featured content is determined by [User States](/Conventions/User States) and [DCH States](/Conventions/DCH States). To prevent doublings, it should never show the same content as the Featured Area of [Home]().

### U1 - not logged in, U2/U3 - logged in with or without ticket

| DCH state | Purpose | Content item | Button |
| --- | --- | --- | --- |
| D1 | Advertise the upcoming live concert. | **Upcoming live concert** with image, title, date as \[DATE\_FULL\], content type label: DCH\_content\_type\_label\_live, free content label: DCH\_free\_content\_label, countdown | DCH\_button\_more |
| D2, D3a/b | Advertise the latest concert that has been added to the archive. | **Latest  archive concert** with: title, image, date as \[DATE\], content type label: DCH\_content\_type\_label\_concert, free content label: DCH\_free\_content\_label \(conditional\) | DCH\_button\_more |

---

## [Content Lists]()

Displays the following content lists. For the structure of Content Items see: [Content Item]().

In the initial state of the view and after clearing filter results the content item that is shown in the Featured Area should not be displayed within the content list to prevent doubling.

### U1 - not logged in, U2/U3 - logged in with or without ticket

**TBD: Filters**

| List title | List title label | Content list type |
| --- | --- | --- |
| “Archive” | DCH\_content\_list\_title\_concert\_archive | Concert List with all archive concerts, sorted by concert.date.begin and in descending order |
| “Upcoming Live Concerts” | DCH\_content\_list\_title\_live| Concert List with all upcoming live concerts, sorted by concert.date.begin and in ascending order |
| “Education Programme” | DCH\_content\_list\_title\_education | Concert List with with all archive concerts of the category "education", sorted by concert.date.begin and in descending order |



{{% /tab %}}

{{% /tabs %}}
