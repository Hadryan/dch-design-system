---
title: Content Data Structures
weight: 1
---

### Concert

Full-length concerts are the Digital Concert Hall’s primary content type , both live and on-demand. [Read more](https://docs.digitalconcerthall.com/1.0%20Service/1_6_content.html#161-concerts) about concert content.

#### Concert data - not language specific

| Attribute              | Example                                                      | Type         | Notes                                                        |
| ---------------------- | ------------------------------------------------------------ | ------------ | ------------------------------------------------------------ |
| id                     | [466](https://admin.digitalconcerthall.com/concert/466/en/edit) | int(11)      | only not used in public                                      |
| product_id             | [23442](https://www.digitalconcerthall.com/de/concert/23442) | varchar(255) | the publicly used id for concerts                            |
| created_by             | 1                                                            | int(11)      | user ID of admin user who created the entry (1 for imported data) |
| published              | yes / no                                                     | tinyint(1)   | is this concert available in DCH applications or not         |
| is_free                | yes / no                                                     | tinyint(1)   | is this concert available to play for registered DCH users without a valid ticket or not |
| locked_for_import      | yes / no                                                     | tinyint(1)   | can the current data be overwritten by importing new data or not |
| created                | timestamp                                                    | int(11)      | concerts can be created manually or by importing new concert data |
| updated                | timestamp                                                    | int(11)      | concerts can be updated manually or by importing new concert data |
| type                   | vod or live                                                  | varchar(255) | is it an upcoming live concert or an archive concert         |
| begin_date             | 2017-07-01 20:15:00                                          | datetime     | planned start of the performance                             |
| end_date               | 2017-07-01 23:15:00                                          | datetime     | planned end of the live streaming, corrected directly after the event |
| publish_date           | 2017-07-3 10:00:00                                           | datetime     | when was this concert publised in the archive (type=vod)     |
| pre_event_opening_time | 15                                                           | int(11)      | the number of minutes the live stream is made available before concert begin |

#### Concert data - language specific

| Attribute | Example | Type | Notes |
|---|---|---|---|
| image_id | 2312 | int(11)	 | photo of this concert |
| language | language code - [ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)  | varchar(2)	| see 2.7 localization |
| title |  Andris Nelsons conducts the “Symphonie fantastique” at Musikfest Berlin | varchar(255) |  |
| event_title | "Musikfest Berlin"  | varchar(255) | optional meta title, shown as additional information |
| url_path | *not used*  | varchar(255) | |
| tiny_description | *not used*  | varchar(255) | |
| short_description | Fanatical love, drug rapture, execution: there’s hardly an extreme experience that Hector Berlioz’ <em>Symphonie fantastique</em> leaves out. At the same time, the feverish expressivity is based on a cleverly calculated use of a tremendously large orchestra. In addition, Andris Nelsons and the Berliner Philharmoniker are presenting Debussy’s dreamy <em>Prélude à l’après-midi d’un faune</em> and Edgard Varèse’s orchestral work <em>Arcana</em>, which conjures up cosmic forces, on this French programme.  | longtext | short text, written exclusively for the Digital Concert Hall - this is displayed on all DCH interfaces and is typically available in all supported languages |
| description | “Only when I heard Prélude à l’après-midi d’un faune for the first time did I realize what music really is.” None other than Maurice Ravel said that about Claude Debussy’s epoch-making masterpiece, based on the poem of the same name by Stéphane Mallarmé. His artful play with timbres rang in modernism in music: “Music began to draw new breath with the flute of the faun” (Pierre Boulez). The audience at the premiere was enthusiastic about the piece: “There was a vast silence in the hall as I ascended to the podium and our splendid flutist, Barrère, unfolded his opening line,” the evening’s conductor, Gustave Doret, recalled. “All at once I felt behind me […] an audience that was totally spellbound. It was a complete triumph.” The music, whose iridescent sound images evoke the world of ancient Arcadia conveyed by the poetry, was so wildly applauded that it had to be repeated.<br><br>At his guest appearance this year, Andris Nelsons, who has regularly conducted the Berliner Philharmoniker since his debut in October 2010, has placed Debussy’s Prélude at the beginning of a French evening. The shooting star on the classical music scene – appointed the new Kapellmeister at Leipzig’s Gewandhaus (thus following in the footsteps of Felix Mendelssohn Bartholdy, Arthur Nikisch, Wilhelm Furtwängler and Bruno Walter) only one year after his leap to heading up the Boston Symphony Orchestra – will then address Edgard Varèse’s magnum opus Arcana, a visionary homage to the doctor, philosopher and alchemist Paracelsus: “arcana” are those substances which aid in opening up worlds that are actually beyond human access. <br><br>The main symphonic work on the two evenings is Hector Berlioz’s burlesque Symphonie fantastique, which as a “fantastic tale” plays in the imaginary world of an imaginary musician “of pathological sensitivity” who, “convinced that his love is unappreciated,” poisons himself with opium (Berlioz). The work ends with Songe d’une Nuit du Sabbat, a “bizarre night piece” (Heinrich Heine) which could not be explained using the form criteria developed until then. We can particularly look forward to Nelsons’ impulsive interpretation: his infectious enthusiasm for music when conducting seems to know no yesterday and no tomorrow! “Compared to the Witches’ Sabbath,” wrote the Allgemeine musikalische Zeitung in 1843, “[…] Weber’s Wolf’s Glen is a lullaby.”  | longtext | long form description, originally written for the programme brochure for the event in the Berliner Philharmonie, typically only available in DE / EN |
| sponsors | *not used* | longtext | |
| photo_credit | Photo: Wilfried Hösl | varchar(255) | name of photographer or agency / copyright |
| trailer_url_sd | *only used until end of 2017* | varchar(255) | low resolution trailer |
| trailer_url_hd |  *only used until end of 2017* | varchar(255) | high resolution trailer |

### Concert Relations

Please check the following database tables for detailed information about data releated to concerts :

- [dchcore -> cms_concert](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsconcert)
- [dchcore -> cms_concert_artist](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsconcertartist)
- [dchcore -> cms_concert_category](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsconcertcategory)
- [dchcore -> cms_concert_piece](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsconcertpiece)
- [dchcore -> cms_concert_season](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsconcertseason)
- [dchcore -> cms_concert_season_label](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsconcertseasonlabel)
- [dchcore -> cms_concert_translation](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsconcerttranslation)

#### Programme, booklet and biographies
Each concert programme is accompanied by a programme booklet and a biography of the performing artist(s). These two rich text documents consist of simple (non-semantic) HTML. They use a limited set of styles such as headline, subline, paragraph as well as bold and italic inline formatting. 

The programme booklet and the biography are complementary to every concert. While they may detail individual pieces and artists they are written in the context of the entire concert. They may be left out if the user experience is compromised (too small screen, inappropriate reading length) or when viewing a piece outside the context of its concert. 

Available only in German and English:

- [dchcore -> cms_program_data](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsprogramdata)
- [dchcore -> cms_program_data_translation](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsprogramdatatranslation)

Both will be added to a live concert only shortly before the live concert begins, usually within the last 48 hours.






### Film

In addition to full-length concerts the Digital Concert Hall features one other distinct type of video content: films.  [Read more](https://docs.digitalconcerthall.com/1.0%20Service/1_6_content.html#films) about film content.



#### Film data - not language specific

| Attribute | Example | Type | Notes |
| -- | -- |-- |-- |
| id | [47](https://admin.digitalconcerthall.com/film/47/en/edit) | int(11) | not used in public |
| product_id | [304](https://www.digitalconcerthall.com/de/film/304) | varchar(255) |  the publicly used id for films |
| published | yes / no  | tinyint(1) | is this film available in DCH applications or not |
| is_free | yes / no  | tinyint(1) | is this concert available to play for registered DCH users without a valid ticket or not |
| created_by | 1 | int(11) | user ID of admin user who created the entry (1 for imported data) |
| position | 8 | int(11)  | used to sort films in DCH applications |
| created | timestamp | int(11) | films are created manually by the DCH editorial team |
| updated | timestamp  | int(11) | films are updated manually by the DCH editorial team  |
| licenser_id | 1 | int(11) | id of the related licenser |
| publish_date | 2015-12-07 10:15:00  | datetime | used to make films appear in the "recently added" content item list in DCH applications |
| duration | 6458 | int(11)  | duration of the film in seconds |
| year_of_production | 2012 | smallint(6) | ... |

#### Film data - language specific

| Attribute | Example | Type | Notes |
| -- | -- |-- |-- |
| id | standard identifier | int(11) | |
| movie_id | [302](https://www.digitalconcerthall.com/de/film/302)  | int(11) | the publicly used id for films | 
| teaser_image_id | word  | int(11) | |
| poster_image_id | word  | int(11) | |
| created_by | 1 | int(11) | user ID of admin user who created the entry (1 for imported data) |
| created | timestamp | int(11) | concerts can be created manually or by importing new concert data |
| updated | timestamp  | int(11) | concerts can be updated manually or by importing new concert data |
| language | language code - [ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)  | varchar(2)	| see 2.7 localization |
| title | Rhythm Is It!  | varchar(255) | ... |
| tiny_description | ...  | varchar(255) | ... |
| short_description | ...  | longtext | ... |
| description | ...  | longtext | ... |
| credits | A BOOMTOWNMEDIA production in co-production with Cine Plus, co-financed by RBB Rundfunk Berlin Brandenburg/Arte and in cooperation with Berliner Philharmoniker »Zukunft@BPhil« and Dance United, funded by Medienboard Berlin-Brandenburg. Im Verleih der Piffl Medien. Verleih gefördert von FFA und Medienboard Berlin-Brandenburg. © 2004 BOOMTOWNMEDIA GmbH &amp; Co KG Berlin.  | longtext | additional credit information for this film, might be changed to a more structured approach soon |
| trailer_url_sd | *only used until end of 2017* | varchar(255) | low resolution trailer | 
| trailer_url_hd |  *only used until end of 2017* | varchar(255) | high resolution trailer |
| photo_credits | not used  | varchar(255 | ... |
| cuepoints | not used  | varchar(255)	 | ... |
| captions | not used  | varchar(255)	 | ... |
| video_path | films/maestros-in-democracy_sub-de
  | varchar(255) | path to the video file on  |

Films have no date information. They should be sorted by their sorting number.

### Film Relations

Please check the following database tables:

- [dchcore -> cms_movie](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsmovie)
- [dchcore -> cms_movie_artist](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsmovieartist)
- [dchcore -> cms_movie_translation](https://docs.digitalconcerthall.com/5.0%20Database/5_1_dchcore.html#cmsmovietranslation)


---

##TODO


### Work

In several, older parts of the documentation and in many DCH interfaces, the word "piece" is used synonymously for "work". We aim to use "work" publicly because it is the correct wording, also from a musicology standpoint. 


### Interview

An interview is structurally almost identical to a work. An interview entity contains:


### Artists
- An artist entity contains:
- a name
- references to concerts, pieces and/or interviews
- a role category (composer, soloist, conductor, group, other, …)
- a role name
- a fame level (1 = superstar, 2 = star, 0 = regular soloist)

---

### Playlists 
* (also known as collection or anthology)
* Playlists are editorially composed lists of concert pieces. 

They are designed to aggregate and promote concert pieces in the archive outside the context of - their parent concerts.  


