# Useful snippets related to Adobe CC

**Keep foreign characters in a `.csv` for data merge with InDesign**
- Save data as `.csv` from Excel
- `cd` to the file location in Terminal
- Use the following command (changing file names)
  ```
  iconv -f utf-8 -t utf-16 < data.csv > newData.csv
  ```
- Use new file as data source for InDesign

[Source and credit](http://ollehost.dk/blog/2016/02/16/convert-character-encoding-of-a-csv-file-for-indesign-data-merge/)

**Remove empty paragraph breaks from imported text in InDesign**
- Bring up `Find/Change`
- Select `GREP` query
- Into `Find what:` type `\r\r+`
- Into `Change to:` type `\r`
