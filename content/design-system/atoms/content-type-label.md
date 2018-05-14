---
title: Content Type Label
---

#### Atom

# Content Type Label

{{% tabs %}}

{{% tab "Overview" %}}

![](/images/atoms/content-type-label/variants.png)

## Overview

These labels identify content items. They should be simple, readable and closely tied to the Digital Concert Hall brand colors.

## Goals

* Easily spot different content types
* Establish a color system across the app (live, archive, free)

{{% /tab %}}

{{% tab "Specs" %}}

## Specs

#### General Rules

![](/images/atoms/content-type-label/breakdown.png)

* Size defined by padding
* Label should not exceed 8 characters


### Visual Reference

[![](/images/atoms/content-type-label/variants.png)](http://zpl.io/a3xokRd)

{{% /tab %}}

{{% tab "Labels" %}}

## Labels

| Content               | Label key                        | Notes                                                        |
| --------------------- | -------------------------------- | ------------------------------------------------------------ |
| concert               | DCH_content_type_concert         |                                                              |
| upcoming live concert | DCH_content_type_live            |                                                              |
| running live concert  | DCH_content_type_live_now        | should be used only in DCH state D3                          |
| work                  | DCH_content_type_label_work      |                                                              |
| film                  | DCH_content_type_label_film      |                                                              |
| interview             | DCH_content_type_label_interview |                                                              |
| playlist              | DCH_content_type_label_playlist  |                                                              |
| free content          | DCH_free_content_label           | this is an additional label, it applies to all content types with attribute is_free = true |

{{% /tab %}}

{{% /tabs %}}
