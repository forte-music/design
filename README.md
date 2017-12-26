design
------

A collection of user interface and experience decisions, mock ups, and color
choices for a consistent experience across platforms.

Who is forte designed for?
--------------------------

There is a gradient from hoarder to nomad in music listeners. Nomads wander from
discover playlist to discover playlist searching for something new to listen to.
Hoarders are more selective and have collection which they listen from. Forte is
for the hoarders.

At its heart, forte is a music index upon which interfaces to access music are
built. Forte is for the ultra-horaders who have cold-hard digital copies of what
they listen to. We care about the quality of the audio which is shipped into our
headphones but we also want to access the music on the go without blowing
through mobile data caps.

What is forte?
--------------

There are a few parts to forte.

* Crawlers. These will keep the index up to date with the physical music files
  (mp3, flac, etc.) by looking at their tags. It doesn't try to fix metadata.
  There are other tools to fix bad metadata. People with curated collections
  have good metadata. Crawlers are the only way to add music to forte.

* Backend. The backend and crawlers share a database which points to music
  files. The backend serves data to the various frontends. [forte-music/schema].

* Frontends. Frontends are clients which talk to the backend to view the
  collection, modify it and play music.

Forte's goals are to:
* Index and serve metadata for massive, personal music collections.
* Provide rich, coherent, integrated (with the system playback features)
  interfaces to access music wherever you are. Whether that be on the web,
  desktop, iOS or Android.
* Provide a platform for building rich music driven applications (remote
  players, consensus queues, automatic dj, etc.)

Why does forte exist?
---------------------

There are a few other projects and services in the space. Here's why we built
forte instead of using each of these.

* [Koel] is a personal media streaming server which works. Forte was born out of
  koel's lack of a strong API (the entire database is sent to the client on
  application boot) making it hard to develop mobile apps. Changing the API
  would have involved a significant rewrite of both the backend and frontends.

* [Beets] has a better API, but it still lacked features (like pagination and on
  the fly transcoding) to build a powerful, efficient mobile app.

* [Spotify] has cross-platform apps but doesn't allow for storing a personal
  collection. Also spotify's queues make you commit to a list by not allowing
  for inserting songs after the current song or at the end of the queue.

* [Apple Music] allows for backing up your personal collection, but only lossy
  copies and apps are only available on iOS, Android, macOS and Windows. It
  lack's linux support.

* [Roon] provides most of what we were looking for except mobile apps.

* [Google Play Music] is one of the best services we've used but it has a few
  problems. Your personal music collection is limited to 50k songs, playlists
  are limited to 1k items and only lossy music can't be streamed. Google Play
  Music has great iOS, Android and Web apps with a consistent interface and
  integrated experience across platforms. Also it's free.

Pages
-----

A list of views which forte has.

* Songs. Every song in the library is put into a list of songs. This list can be
  enqued entirely and shuffled. It can also be sorted (and reverse sorted) by
  duration, play count, title, album title, artist name.

* Playlists. Playlists are a list of songs with a name. A playlist can be
  enqueud in their entirety and shuffled. Rich art is composed from the unique
  album art in the songs of the playlist. The most recently played playlists are
  showed above a fold and all playlists are also shown in arbritrary
  (consistent) order. Anything which can be enqued can be added to a playlist.

* Artists. Artists have a list of albums and a name. Artists can be enqueud in
  their entirety and can be shuffled. Artwork for an artist is composed from the
  artist's album's art. The artist's albums, singles and features are displayed.
  A lexicographically sorted list of artist is available.

* Albums. Albums are a list of songs with artwork. They can be enqueued in their
  entirety and shuffled.

* Home View. This displays recommendations for what to listen to next. This will
  display what list you were last listening to (album, artist, playlist) and
  newly added songs, artists and albums.

* Search. Search all abums, artists and songs matching a query.

Improvemens
-----------

* Advanced  Recommendations

Design Inspiration
------------------

Here are a list of places (along with the music platforms above) we drew
inspiration from when desigining the interfaces for forte.

* https://blog.prototypr.io/spotify-reverse-engineering-8f6a0d9850c8
* https://uxdesign.cc/why-spotify-s-navigation-is-broken-ce6b4783539d
* https://medium.com/startup-grind/i-got-rejected-by-apple-music-so-i-redesigned-it-b7e2e4dc64bf

[koel]: https://koel.phanan.net/
[beets]: http://beets.io/
[spotify]: https://spotify.com
[apple music]: https://www.apple.com/music/
[google play music]: https://play.google.com/music/listen
[roon]: https://roonlabs.com/index.html

[forte-music/schema]: github.com/forte-music/schema
