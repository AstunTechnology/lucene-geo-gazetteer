You need to use https://github.com/DmitryKey/luke/releases/tag/luke-5.2.0 (which needs java 8) for the version of lucene included in this repository.

Download the zip file and extract it, then run `luke.sh` or `luke.bat` in a terminal, depending on your OS.

In the file chooser window that opens, browse to the root folder where the index lives, eg `/some/location/lucene-geo-parser/geoIndex`

You can search for a term using the Search tab, eg a single term like `name: Lancaster` or a multi-word term like `name: Abraham name:Heights`. You can experiment with different query analysers here (though the lucene-geo-parser uses `org.apache.lucene.analysis.standard.StandardAnalyzer` afaict)

You can double-click on a document in the search results to see all of its fields in the index.