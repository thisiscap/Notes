# Useful snippets for InDesign

## Keep foreign characters in a `.csv` for data merge

- Export data as `.csv` from Excel
- `cd` to the file location
- Use the following command (changing file names)
  ```
  iconv -f utf-8 -t utf-16 < oldData.csv > newData.csv
  ```
- Data merge using the new file

[Source and credit](http://ollehost.dk/blog/2016/02/16/convert-character-encoding-of-a-csv-file-for-indesign-data-merge/)

## Quickly remove empty paragraph breaks from imported text

- Bring up `Find/Change`
- Select `GREP` query
- Into `Find what:` type `\r\r+`
- Into `Change to:` type `\r`
