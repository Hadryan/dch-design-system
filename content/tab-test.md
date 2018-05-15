---
title: Tabs
---
# Tabs

## Dynamic tab
{{% tabs %}}

{{% tab "Overview" %}}

Here's some content

{{% /tab %}}

{{% tab "Profile" %}}

Content of the profile tab

{{% /tab %}}

{{% tab "Something Else" %}}

Something else goes here

{{% /tab %}}

{{% /tabs %}}


## Static tab

<!-- Nav tabs -->
<ul class="nav nav-tabs" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="home-tab" data-toggle="tab" href="#home" role="tab" aria-controls="home" aria-selected="true">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="profile-tab" data-toggle="tab" href="#profile" role="tab" aria-controls="profile" aria-selected="false">Profile</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="messages-tab" data-toggle="tab" href="#messages" role="tab" aria-controls="messages" aria-selected="false">Messages</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="settings-tab" data-toggle="tab" href="#settings" role="tab" aria-controls="settings" aria-selected="false">Settings</a>
  </li>
</ul>

<!-- Tab panes -->
<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel" aria-labelledby="home-tab">Home Content</div>
  <div class="tab-pane" id="profile" role="tabpanel" aria-labelledby="profile-tab">Something else</div>
  <div class="tab-pane" id="messages" role="tabpanel" aria-labelledby="messages-tab">Was?</div>
  <div class="tab-pane" id="settings" role="tabpanel" aria-labelledby="settings-tab">Hier</div>
</div>