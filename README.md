# geoguessr-stuff
my geoguessr maps as json and geojson files (now also other stuff)

publishing them so that if others want, they can make their own maps out of this, just use some locs for their maps, or use it outside geo (idk if there's any usecase for that, but if there's ever a geo alternative where you can import jsons, there you go, they're now usable).

## ublock origin blocklist

you need to have [uBlock Origin](https://ublockorigin.com/) (pay attention to the Origin part!) installed. to add the element blocks (each line is a new item), click on the addon in the toolbar and go to the dashboard (3 cogs). in theory, you might be able to import the [raw link](https://github.com/itsjustduc/geoguessr-stuff/raw/main/geoguessr-ublock.txt) from the filter lists tab. but i have not tested this, and my blocks are pretty opinionated. so it's a better idea to go line-by-line and copy them into the text editing part of the "my filters" tab. every line has a note regarding what it blocks.
lines that begin with `!` are "comments" and therefore will be ignored by uBO. if you want, you can copy paste the whole thing into your filters, and put `!` in front of the lines you don't need blocked.

**NOTE: i don't use every single feature of geo. it is possible that these blocks accidentally block something unintended. if such is the case, please feel free to create an issue.**

## maps

### [Gorgeous Touge Roads](https://www.geoguessr.com/maps/6305565fde2667656468e9b2)

a collection of beautiful-looking roads that go through hills. has some hairpin turns (which is what might come to mind from the title), but also some less curvy mountain passes. it contains official coverage only. it should work fine on NMPZ, but the recommended way of playing it is NM.

if you have locations for this, an issue is welcome with google maps links. NOTE: i do try to have the locations balanced between regions of the world, otherwise the difficulty and odds would be skewed. you can simply import them with map-making.app to see current distribution. only the locations with a _continent tag are exported to geoguessr.

feel free to also create an issue if a location is bugged!

### Brazil Phone Codes (W.I.P.)

yet another one of these, mainly creating a new one, cause i didn't like any of the ones i've tried lol. i'm trying to put them in cities, but also making sure that no city or state name is visible on the NM view, so that one can practice without accidentally seeing where it is. i also think most practice maps have had updated coverage on some locs? so i'm selecting specific coverages (google pls no panoid kil).

progress: 1x phone numbers each have one

update: i think the one [plonkit](https://www.plonkit.net/brazil) links is actually decent. probably not getting finished as a result.

## chatguessr flags

to add flags to your chatguessr install, first you need to find the chatguessr user data directory. it should be in one of the following directories (if electron documentation is to be believed):

* `%APPDATA%` on Windows
* `$XDG_CONFIG_HOME` or `~/.config` on Linux
* `~/Library/Application Support` on macOS

inside that, you should find a `chatguessr` folder. there may or may not be a `flags` folder already, if not, create one and a `flags.json` text file inside it, looking something like this example:

```
[
{ "code": "agender", "names": "agender", "emoji": "\uD83C\uDFF3\uFE0F\u200D\uD83C\uDF08" },
{ "code": "aromantic", "names": "aromantic, aro", "emoji": "\uD83C\uDFF3\uFE0F\u200D\uD83C\uDF08" }
]
```

there needs to be a comma after every flag line, except for the last one. you can use a [json validator](https://jsonlint.com/) that will say whether it's ok or not. the 3 properties in a line are the following:

- `code` refers to the name of the file (png or svg), which should also be in the mentioned flags folder
- `names` is a list of alternative names, so that viewers can also assign flags using that in chat
- `emoji` is the emoji that is before the name of a viewer in chat (e. g. the name of the winner as submitted by the bot) - e. g. i made the above ones look like the general rainbow pride flag, as there is an emoji for that, but not for these specific flags

the flag pack(s) provided in this repo are not full/valid files, they are missing the 2 `[]` array markers. i felt that this way, they would be easier to add to already existing files.
