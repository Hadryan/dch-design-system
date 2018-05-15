---
title: Breakpoints
---

{{% tabs %}}

{{% tab "Overview" %}}

## How It Works

When designing Digital Concert Hall, it's important that any decision takes into consideration that we support many platforms, and for each, an exponential number of devices, with screens of many sizes.

Each platform has its own way to define how to deal with different device sizes:

* Web uses *media queries*, with a wide choice of units (*px*/*em*/*%*/...)
* iOS & tvOS uses *size classes*, and *point*
* Android uses *screen density* and *density-independent pixels*
* ...

As disparate as all these methods and measurements may be, most responsive sizing issues are global. In this manual, we have decided to utilize our own scale of breakpoints, which will then be translated to each platform.

Throughout this document, these breakpoints will be referenced, and should be understood as the general guidelines for each platform's respective responsive methods.

## Units

Our system uses a simple naming convention (**XS**, **S**, **M**, **L** and **XL**) and are defined in **pixels**. As we design everything in 1x, these pixels are equivalent to 1 **point**/**dp**.

{{% /tab %}}

{{% tab "Sizes" %}}

| Name   | Min. Width | Max. Width |
| ------ | ---------- | ---------- |
| **XS** | 320px      | 374px      |
| **S**  | 375px      | 767px      |
| **M**  | 768px      | 1023px     |
| **L**  | 1024px     | 1365px     |
| **XL** | 1366px     | -          |

{{% /tab %}}

{{% tab "iOS" %}}

| Name                  | Size Classes                  | Orientation | Breakpoint |
| --------------------- | ----------------------------- | ----------- | ---------- |
| **iPhone (5.5 inch)** | Compact width, Regular height | Portrait    | S          |
| **iPhone (5.5 inch)** | Regular width, Compact height | Landscape   | M*         |
| **All Other iPhones** | Compact width, Regular height | Portrait    | S          |
| **All Other iPhones** | Compact width, Compact height | Landscape   | M*         |
| **iPhone SE**         | Compact width, Regular height | Portrait    | XS         |
| **iPad**              | Regular width, Regular height | Both        | M          |
| **iPad Pro**          | Regular width, Regular height | Both        | L          |

\* *when available; mobile versions currently don't work on landscape except for fullscreen playback.*

{{% /tab %}}

{{% tab "Android" %}}

{{% /tab %}}
{{% /tabs %}}