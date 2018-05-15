---
title: VOD servers
weight: 2
---

## Video on Demand Streaming

### Server Locations

We are hosting the vod files on several systems around the world and deliver video streams directly without the use of a CDN. You can read more about his decision in Alex' blogpost: http://www.mcwilliam.biz/blog/vastly-improve-your-video-delivery-by-ridding-your-cdn

Most systems are bare metal servers from Softlayer or Hetzner, some are virtual machines provided by IIJ.

Every system hosts the complete DCH video archive, meaning every content that requires a user to have at least a registration to be played.

| Name                    | Location                  | Hosting Company |
| ----------------------- | ------------------------- | --------------- |
| australia.dchdns.net    | Sydney                    | Softlayer       |
| brazil.dchdns.net       | Sao Paulo                 | Softlayer       |
| california.dchdns.net   | San Jose, US West Coast   | Softlayer       |
| england.dchdns.net      | London                    | Softlayer       |
| germany.dchdns.net      | Nuremberg                 | Hetzner         |
| hongkong.dchdns.net     | Sydney                    | Softlayer       |
| japan.dchdns.net        | Tokyo                     | Softlayer       |
| japan-2.dchdns.net      | Tokyo                     | IIJ             |
| maryland.dchdns.net     | Washington, US East Coast | Softlayer       |
| netherlands.dchdns.net  | Amsterdam                 | Softlayer       |
| pool-asia.dchdns.net    | Tokyo                     | Softlayer       |
| pool-europe.dchdns.net  | Amsterdam                 | Softlayer       |
| pool-europe2.dchdns.net | Amsterdam                 | Softlayer       |
| pool-usa.dchdns.net     | Dallas, US                | Softlayer       |



### Routing

Routing is done via Amazon Web Services (AWS) with Route 53. The routing chooses the vod server on a geo-distance basis.

### Bandwidth Test

DCH users can test their connectivity to our vod systems with a publicly available bandwidth test on the DCH website: https://www.digitalconcerthall.com/de/bandwidth

This test is also available for registered users on the "my account" page, and it enables a user to find out which systems works best for them and save this one as a personal default. However, this is optional as the general default routing is automated.