---
title: Concert Details (Archive)
---

#### Page

# Concert Details (Archive)

{{% tabs %}}

{{% tab "Overview" %}}

![](/images/pages/details/concert/cover.jpg)
_**Temporary Image**_

This view contains all information related to a specific concert, including metadata and a browsable list of included works.

## Goals

* Inform user about concert details
* Display participant and conductor details
* Allow navigation within concert

{{% /tab %}}

{{% tab "Visual Reference" %}}

Click images for up-to-date measurements and features.

### XS
![](/images/pages/details/concert/xs.png)
_**Temporary Image**_

### S
![](/images/pages/details/concert/s.png)
_**Temporary Image**_

### M
![](/images/pages/details/concert/m.png)
_**Temporary Image**_

### L
![](/images/pages/details/concert/l.png)
_**Temporary Image**_

{{% /tab %}}

{{% tab "Labels" %}}

API: concert.type = "vod"

### Reference content

Use these concerts to test the interface during concept and development work.

* [23488 - Simon Rattle conducts “Bluebeard’s Castle”](https://www.digitalconcerthall.com/de/concert/23488)
* [2886 - Mariss Jansons conducts Dvořák’s Symphony “From the New World”](https://www.digitalconcerthall.com/de/concert/2886)
* [2580 - Sir Simon Rattle conducts Wagner’s “Die Walküre”](https://www.digitalconcerthall.com/de/concert/2580)
* [3923 - “40 Years of the Orchestra Academy” Gala Concert with Simon Rattle](https://www.digitalconcerthall.com/de/concert/3923)
* [1640 - Concert to commemorate the 25th anniversary of the Chernobyl nuclear disaster](https://www.digitalconcerthall.com/en/concert/1640)
* [81 - Claudio Abbado conducts the 1999 New Year’s Eve concert](https://www.digitalconcerthall.com/en/concert/81)

### Primary information

| Element                                  | Label key / API data                     | Example Content / Label text             |
| :--------------------------------------- | :--------------------------------------- | :--------------------------------------- |
| content type label                       | [DCH\_content\_type\_label\_concert](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?plural_suffix=&search=eyJmaWx0ZXJzIjpbIiIsInRyYW5zbGF0ZWQiLCJ1bnRyYW5zbGF0ZWQiLCJleGNsdWRlZCIsImluY2x1ZGVkIiwidW52ZXJpZmllZCIsInZlcmlmaWVkIiwicGx1cmFsaXplZCIsInVucGx1cmFsaXplZCJdLCJxdWVyeSI6ImNvbnRlbnRfdHlwZV8qIiwic29ydGluZyI6InNjb3JlIiwibG9jYWxlX2lkIjoiY2JmNDg2ODAyZmJkZTlkYWQ1ODc5MTQ2MmM4OTQyMTcifQ%3D%3D&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&translation_key_id=27ca6a2baf519430dcc88e7e3412eb1b) | concert                                  |
| free content label \(conditional, not for U3 state\) | [DCH\_free\_content\_label](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?search=eyJmaWx0ZXJzIjpbIiIsInRyYW5zbGF0ZWQiLCJ1bnRyYW5zbGF0ZWQiLCJleGNsdWRlZCIsImluY2x1ZGVkIiwidW52ZXJpZmllZCIsInZlcmlmaWVkIiwicGx1cmFsaXplZCIsInVucGx1cmFsaXplZCJdLCJxdWVyeSI6IkRDSF9mcmVlX2NvbnRlbnRfbGFiZWwiLCJzb3J0aW5nIjoic2NvcmUiLCJsb2NhbGVfaWQiOiJjYmY0ODY4MDJmYmRlOWRhZDU4NzkxNDYyYzg5NDIxNyJ9&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&translation_key_id=7da35eed57335f455a29ce6b7daa98a5) \(if concert.is\_free = true\) | free                                     |
| date                                     | concert.date.begin as \[DATE\]           | 08 Feb 2016                              |
| title                                    | concert.title                            | Simon Rattle conducts “Bluebeard’s Castle” |
| description                              | concert.description - regular text, treat "\[" and “\]" as custom tag to trigger italics formatting | Béla Bartók’s only opera _Bluebeard’s Castle_ sounds enigmatic and dark. This is a spectral psychological drama, clad in an impressionist music rich in allusions. The vocal soloists at this performance with Simon Rattle are Rinat Shaham and Gábor Bretz. As a counterpoint there is – with Emanuel Ax as soloist – a new piano concerto by HK Gruber, whose style is characterised by subtle wit and jazzy swing. |
| image                                    | concert.image.detail                     | -                                        |

### Secondary information

| Element      | API data                                 | Example content                          |
| :----------- | :--------------------------------------- | :--------------------------------------- |
| event title  | concert.event\_title                     | Benefit Concert of the Federal President of Germany in aid of UNICEF |
| copyright    | concert.copyright                        | © Berlin Phil Media GmbH                 |
| image credit | DCH\_image\_credit\_prefix + concert.image\_credit | Photo: Monika Rittershaus                |

### Primary buttons

| Element                                  | Label key                                | Label text    |
| :--------------------------------------- | :--------------------------------------- | :------------ |
| button to watch complete concert, should be highlighted | [DCH\_content\_detail\_screen\_button\_watch\_concert](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=06ab850e4dc04a7391e1473490d5a87f&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6IkRDSF9jb250ZW50X2RldGFpbF9zY3JlZW5fYnV0dG9uX3dhdGNoX2NvbmNlcnQiLCJzb3J0aW5nIjoic2NvcmUiLCJsb2NhbGVfaWQiOiJjYmY0ODY4MDJmYmRlOWRhZDU4NzkxNDYyYzg5NDIxNyJ9&next_translation_key_id=c508880756902781ee3db15c018f1a5d) | watch concert |
| button to watch preview \(conditional\)  | [DCH\_content\_detail\_screen\_button\_preview](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=c247c478111e0c3a38b10c01ca95847a&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6IkRDSF9jb250ZW50X2RldGFpbF9zY3JlZW5fYnV0dG9uX3ByZXZpZXciLCJzb3J0aW5nIjoic2NvcmUiLCJsb2NhbGVfaWQiOiJjYmY0ODY4MDJmYmRlOWRhZDU4NzkxNDYyYzg5NDIxNyJ9&next_translation_key_id=c508880756902781ee3db15c018f1a5d) | preview       |
| button to share concert                  | [DCH\_content\_detail\_screen\_button\_share](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=c78abeff6a369d1f8aadaa3c53958ebd&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&plural_suffix=&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6IkRDSF9jb250ZW50X2RldGFpbF9zY3JlZW5fYnV0dG9uX3NoYXJlIiwic29ydGluZyI6InNjb3JlIiwibG9jYWxlX2lkIjoiY2JmNDg2ODAyZmJkZTlkYWQ1ODc5MTQ2MmM4OTQyMTcifQ%3D%3D&next_translation_key_id=06ab850e4dc04a7391e1473490d5a87f) | share         |

#### Sharing concert data

Use available sharing apis for the current platform. Use [ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for \[LANG\] value of the sharing url. Please use "concert.title" as subject for sharing, if a subject is possible. Compose the body text from the following data:

| Content                                  | Reference data                           |
| :--------------------------------------- | :--------------------------------------- |
| concert.title                            | "European Concert from Cyprus with Mariss Jansons and Andreas Ottensamer" |
| concert.image.detail                     | [https://www.digitalconcerthall.com/cms/thumbnails/\[width\]x\[height\]/images/core/BPhil\_010517\_Paphos\_MJ\_AO\_020\_DCH.jpg](https://www.digitalconcerthall.com/cms/thumbnails/[width]x[height]/images/core/BPhil_010517_Paphos_MJ_AO_020_DCH.jpg) |
| text part 1: concert.date\_begin         | Fri, 25 Aug 2017, 19:00                  |
| text part 2 : concert.short\_description | This year’s European Concert took the Berliner Philharmoniker to Cyprus, more precisely: to the ancient port city of Pafos. Before the city’s Byzantine castle, the orchestra played works by Carl Maria von Weber and Antonín Dvořák which impress with their lyrical zest and warm colours. The conductor was Mariss Jansons, a close friend of the orchestra for several decades, and the soloist in Weber’s Clarinet Concerto no. 1 was Andreas Ottensamer. |
| referral code                            | API 1.2: get\_session, API 2.0: "/user"  |

### Secondary button

| Element                                  | Label key                                | Label text      |
| :--------------------------------------- | :--------------------------------------- | :-------------- |
| button to open programme guide \(conditional\) | [DCH\_content\_detail\_screen\_button\_programme\_guide](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=0f37fa45cd5285e7148dcc527587e2db&source_locale_id=2e3eb3fbbc8f10da6f649776af761bc9&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6InByb2dyYW1tZSBndWlkZSIsInNvcnRpbmciOiJzY29yZSIsImxvY2FsZV9pZCI6ImNiZjQ4NjgwMmZiZGU5ZGFkNTg3OTE0NjJjODk0MjE3In0%3D&next_translation_key_id=0f37fa45cd5285e7148dcc527587e2db) | programme guide |
| button to select programme information in the programme guide | [DCH\_content\_detail\_screen\_concert\_button\_programme](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=cc846c6f23f7a6cfb07b2bab6a3aa83d&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cc633ac7dc9eb8d6b8833e44642c8ff9&show_changes=false&search=eyJmaWx0ZXJzIjpbXSwicXVlcnkiOiJEQ0hfY29udGVudF9kZXRhaWxfc2NyZWVuX2NvbmNlcnRfYnV0dG9uX3Byb2dyYW1tZSIsInNvcnRpbmciOiJzY29yZSIsImxvY2FsZV9pZCI6IjJlM2ViM2ZiYmM4ZjEwZGE2ZjY0OTc3NmFmNzYxYmM5In0%3D&next_translation_key_id=a4b7b679ece6eeef928d00abaecd02ef) | programme       |
| button to select programme information in the programme guide | [DCH\_content\_detail\_screen\_concert\_button\_programme](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=9881a799072abb2569821703b22e2a41&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cc633ac7dc9eb8d6b8833e44642c8ff9&show_changes=false&search=eyJmaWx0ZXJzIjpbXSwicXVlcnkiOiJEQ0hfY29udGVudF9kZXRhaWxfc2NyZWVuX2NvbmNlcnRfYnV0dG9uX3dvcmtfaW50cm9kdWN0aW9uIiwic29ydGluZyI6InNjb3JlIiwibG9jYWxlX2lkIjoiMmUzZWIzZmJiYzhmMTBkYTZmNjQ5Nzc2YWY3NjFiYzkifQ%3D%3D&next_translation_key_id=a4b7b679ece6eeef928d00abaecd02ef) | musical work    |
| button to biography information in the programme guide | [DCH\_content\_detail\_screen\_concert\_button\_biographies](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=9881a799072abb2569821703b22e2a41&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbXSwicXVlcnkiOiJEQ0hfY29udGVudF9kZXRhaWxfc2NyZWVuX2NvbmNlcnRfYnV0dG9uX2Jpb2dyYXBoaWVzIiwic29ydGluZyI6InNjb3JlIiwibG9jYWxlX2lkIjoiMmUzZWIzZmJiYzhmMTBkYTZmNjQ5Nzc2YWY3NjFiYzkifQ%3D%3D&next_translation_key_id=a4b7b679ece6eeef928d00abaecd02ef) | biography       |

### Main artists and star soloists

Example concert: [https://www.digitalconcerthall.com/de/concert/286](https://www.digitalconcerthall.com/de/concert/286) / [https://api.digitalconcerthall.com/v2/concert/286](https://api.digitalconcerthall.com/v2/concert/286)

| Element                                  | API data               | Example content                          |
| :--------------------------------------- | :--------------------- | :--------------------------------------- |
| Main Artist\(s\) - artists who appear in the whole concert with the roles "group" or conductor in the order of their appearance in the API data. | concert.\_links.artist | Berliner Philharmoniker \([https://api.digitalconcerthall.com/v2/artist/1](https://api.digitalconcerthall.com/v2/artist/1%29\), Bernard Haitink \([https://api.digitalconcerthall.com/v2/artist/128](https://api.digitalconcerthall.com/v2/artist/128%29\) |
| Star soloist\(s\): artist who appear in at least one of the works of a concert as star soloist \(fame = 2\) in the order of their appearance in the api data. | concert.\_links.start  | Frank Peter Zimmermann \([https://api.digitalconcerthall.com/v2/artist/205](https://api.digitalconcerthall.com/v2/artist/205%29\) |

### List of works

API: concert.\_embedded.work

Example concert: [https://www.digitalconcerthall.com/de/concert/286](https://www.digitalconcerthall.com/de/concert/286) / [https://api.digitalconcerthall.com/v2/concert/286](https://api.digitalconcerthall.com/v2/concert/286)

| Element                                  | Label key / Spec                         | Label text / Example content |
| :--------------------------------------- | :--------------------------------------- | :--------------------------- |
| Element headline                         | [DCH\_content\_detail\_screen\_works](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=0c470571a8b1f3c91c5c85ab92270987&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6IkRDSF9jb250ZW50X2RldGFpbF9zY3JlZW5fd29ya3MiLCJzb3J0aW5nIjoic2NvcmUiLCJsb2NhbGVfaWQiOiJjYmY0ODY4MDJmYmRlOWRhZDU4NzkxNDYyYzg5NDIxNyJ9) | works                        |
| Length of all works combined \(conditional\) | concert.duration\_total as \[DURATION\], show this only when the concert consists of at least two works | 103 min.                     |

| Elements of each work                    | API date / Spec                          | Example content                          |
| :--------------------------------------- | :--------------------------------------- | :--------------------------------------- |
| work's composer                          | work.\_links.artist with role: composer  | György Kurtág                            |
| title                                    | work.title, treat "\[" and “\]" as custom tag to trigger italics formatting | _Stele_ for large orchestra, op. 33      |
| work's artist\(s\) w/o composer          | Name + _Role_                            | Frank Peter Zimmermann _Violin \(_[_https://api.digitalconcerthall.com/v2/artist/205_](https://api.digitalconcerthall.com/v2/artist/205)_\)_ |
| duration                                 | work.duration\_total as \[DURATION\]     | 109 min.                                 |
| button to watch this work                | icon or text                             | -                                        |
| button to favorite this work             | icon or text                             | -                                        |
| button to download this work \(conditional= | icon or text                             | -                                        |

#### Cue points for each work \(conditional, only if available\)

Display the available cue points with both the cue point text and cue point time as \[CUEPOINTTIME\].

### Related Artists \(this feature discussion is still in progress - please ignore for now\)

Todo: Define this part, will be a clickable selection of artists \(composers, main artists, star soloists\), a click would lead the user to the corresponding artist's profile page.

### Related interview\(s\)

Depending on the amount of interviews in concert.\_embedded.interview, use the following headline:

* "Related Interview" \([DCH\_content\_detail\_screen\_concert\_related\_interview](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=0c470571a8b1f3c91c5c85ab92270987&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6IkRDSF9jb250ZW50X2RldGFpbF9zY3JlZW5fY29uY2VydF9yZWxhdGVkX2ludGVydmlldyIsInNvcnRpbmciOiJzY29yZSIsImxvY2FsZV9pZCI6ImNiZjQ4NjgwMmZiZGU5ZGFkNTg3OTE0NjJjODk0MjE3In0%3D)\)
* "Related Interviews" \([DCH\_content\_detail\_screen\_concert\_related\_interviews](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=0c470571a8b1f3c91c5c85ab92270987&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6IkRDSF9jb250ZW50X2RldGFpbF9zY3JlZW5fY29uY2VydF9yZWxhdGVkX2ludGVydmlldyIsInNvcnRpbmciOiJzY29yZSIsImxvY2FsZV9pZCI6ImNiZjQ4NjgwMmZiZGU5ZGFkNTg3OTE0NjJjODk0MjE3In0%3D)\)

| Element of related interview             | API data                                 | Example content                          |
| :--------------------------------------- | :--------------------------------------- | :--------------------------------------- |
| title                                    | interview.title                          | Frank Peter Zimmermann in conversation with Christoph Streuli |
| content type label \(conditional\)       | [DCH\_content\_type\_label\_interview](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=0c470571a8b1f3c91c5c85ab92270987&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&show_changes=false&search=eyJmaWx0ZXJzIjpbIiJdLCJxdWVyeSI6IkRDSF9jb250ZW50X3R5cGVfbGFiZWxfaW50ZXJ2aWV3Iiwic29ydGluZyI6InNjb3JlIiwibG9jYWxlX2lkIjoiY2JmNDg2ODAyZmJkZTlkYWQ1ODc5MTQ2MmM4OTQyMTcifQ%3D%3D) | interview                                |
| date \(conditional\)                     | interview.date.begin as \[DATE\]         | 08 Feb 2016                              |
| duration                                 | interview.duration\_total as \[DURATION\] | 18 min.                                  |
| image                                    | interview.image.detail                   | -                                        |
| button to go to interview detail view\(conditional\) | icon or text                             | -                                        |

### Related content

Use the headline  "Watch now" \([DCH\_content\_detail\_screen\_concert\_watch\_now](https://phraseapp.com/accounts/digital-concert-hall/projects/dch-default-dictionary/editor?translation_key_id=01f292068a8f7ff3fa02b5571bc167b4&source_locale_id=cbf486802fbde9dad58791462c894217&target_locale_id=cbf486802fbde9dad58791462c894217&plural_suffix=&show_changes=false&search=eyJmaWx0ZXJzIjpbIiIsInRyYW5zbGF0ZWQiLCJ1bnRyYW5zbGF0ZWQiLCJleGNsdWRlZCIsImluY2x1ZGVkIiwidW52ZXJpZmllZCIsInZlcmlmaWVkIiwicGx1cmFsaXplZCIsInVucGx1cmFsaXplZCJdLCJxdWVyeSI6IkRDSF9jb250ZW50X2RldGFpbF9zY3JlZW5fY29uY2VydF93YXRjaF9ub3ciLCJzb3J0aW5nIjoic2NvcmUiLCJsb2NhbGVfaWQiOiJjYmY0ODY4MDJmYmRlOWRhZDU4NzkxNDYyYzg5NDIxNyJ9&next_translation_key_id=40b543225c4da8a8e41103bd30a3df15)\)

[See 2.5.10 Related Content Logic](https://docs.digitalconcerthall.com/2.0 Application/26221-related-content-logic.html)


{{% /tab %}}
{{% /tabs %}}