# synonymous
## Source Data
The data source for synonyms is the thesaurus for OpenOffice.org that's derived from the WordNet project, which I found through [StackOverflow](http://stackoverflow.com/a/4175371/1881379).

I initially started looking for an API to use as my thesaurus to lookup synonyms, but considering API limitations, I instead searched for a synonyms database.
### Data Structure
The raw data is in the file th_en_US_v2.dat, and the structure is described in data_layout.txt.

The script parse_thesaurus.py was used for data transformation into a JSON file.

The transformed data is in the file thesaurus.json, and an example of the structured data is below.
```javascript
[
  ...,
  {
    "word": "wonderfully",
    "numberOfSynonyms": 7,
    "synonyms": ["wondrous", "wondrously", "superbly", "toppingly", "marvellously", "terrifically", "marvelously"]
  },
  ...
]
```
### MongoDB
As part of the MEAN stack, MongoDB is used to import the data as a JSON array.
