# <img src="http://i.imgur.com/Wbss2gh.png" alt="YTFS">

**YTFS** - File system which enables you to search and play movies from YouTube as files - with tools of your choice.  
Based on FUSE, written in Python 3.

Dependencies, manual and documentation: [Read the Docs](http://ytfs.readthedocs.org/en/latest/)

# Installation

You can install YTFS with pip:

```
$ pip3 install ytfs
```

You need **Python 3.4** or newer.

# Usage

Here some basics are shown. See [docs](http://ytfs.readthedocs.org/en/latest/tutrial.html) for more detailed description

## Mount

Mount YTFS in an empty directory, for example:

```
$ mkdir youtube
$ ytfs youtube
```

## Search

Enter the directory where YTFS is mounted and create a directory whose name is your search query. You can use GUI or CLI (note that the latter is most stable). If you like command line:

```
$ cd youtube
$ mkdir "rick astley"
```

Search results will appear in the directory you have created.

You can narrow your search to a specific channel:

```
$ mkdir "foo bar baz channel:foochannel"
```

Other additional parameters like `before:`, `after:` or `max:` are available. See [docs](http://ytfs.readthedocs.org/en/latest/tutorial.html#advanced-search-parameters) for details.

To navigate between search pages use ` next` and ` prev` scripts in the search directory. Note that they have a space character at the beginning, thereby in most shells/file managers they should be alphabetically first.

```
$ ./\ next
$ ./\ prev
```

## Playback

You can use search results as regular files. Open them with your favourite player, for example:

```
$ mkdir "rick astley"
$ cd rick\ astley
$ mplayer "Rick Astley - Never Gonna Give You Up.mp4"
```

Or you can copy them on your hard drive:

```
$ cp "Rick Astley - Never Gonna Give You Up.mp4" ~/youtube-collection/
```

# Dependencies

* FUSE (Python module: [fusepy](https://github.com/terencehonles/fusepy))
* [youtube-dl](https://github.com/rg3/youtube-dl/tree/master/youtube_dl) (this dependency will be droped in the future)
* [Requests](https://github.com/kennethreitz/requests)

If you mount YTFS with options to download full videos at heighest quality, then audio and video merging may be needed. In such case FFmpeg or Libav is required.

# Contribute

If you want to suggest a new feature or help with development in any way, please open an issue or contact me via email.

# Licence

MIT &copy; Adrian Włosiak
