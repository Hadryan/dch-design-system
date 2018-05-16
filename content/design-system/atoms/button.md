---
title: Button
---

{{% tabs %}}

{{% tab "Overview" %}}

![](/images/atoms/button/cover.png)

## Usage

Buttons are used primarily on action items. Some examples include Watch Concert, Preview, Share. Do not use Buttons as navigational elements.

## Variants

![](/images/atoms/button/variants.png)

### Types of Button

#### Icon Only

Use this option only for commonly identifiably icons (favorite star, play/pause, etc), and only where the layout requires a small button.

#### Text Only

Most calls to action can be solved with only text, as language is less dubious than iconography. Use clear, short and concise language, always from the user's standpoint, and not our own (i.e. why would I click this?)

#### Icon and Text

This type of button is useful to reinforce an important call to action. For example, the "Watch Concert" button with a "play" icon helps catch the user's attention to the function they are probably looking for. Avoid adding icons to buttons just for the sake of it, as text is often clearer than icons.

---

### Hierarchy

#### Primary

Every page should have only one primary button. This should be the main action we expect the user to be looking for (as well as the one we would like them to choose). Avoid more than one primary action within the same viewport.

#### Secondary

Secondary actions are what most buttons will be on a page. They should not be split 50/50 with a primary action, but they can be split with other secondary actions.

---

### States

Different platforms may require different button states. Please use the spec link as your reference for those.

{{% /tab %}}

{{% tab "Specs" %}}

### Button states

![](/images/atoms/button/states.png)

### Visual Reference

* Buttons may be:
  * **Dynamic width**
    * Defined by the size of the label
    * Fixed button padding (defined in each breakpoint)
  * **Fixed width**
    * Width is specified as a number of grid columns, like full-width (100%) or half-width (1/2 columns, spaced by gutter)
    * Padding is **half** the padding (defined in breakpoint)
    * Label width should not exceed space within padding
    * If that happens, use ellipsis (…) and report to the content team for editing

#### XS

[![](/images/atoms/button/xs.png)](https://zpl.io/bJOXMM3)

* One button per row; do not fit two buttons side-by-side
* The "half-width" buttons simply become full-width

#### S

[![](/images/atoms/button/s.png)](https://zpl.io/be1l69Y)

* Two buttons may be used side-by-side (half-width), spaced by the gutter

#### M

[![](/images/atoms/button/m.png)](https://zpl.io/VkYgQ4G)

* Component/Page define number of columns for full width/side-by-side buttons
* Number of columns must be even
* Half-width buttons are as wide as 1/2 of available columns, spaced by the gutter

{{% /tab %}}
{{% tab "Accessibility" %}}

## Accessibility

### alternative text

### status

{{% /tab %}}

{{% /tabs %}}