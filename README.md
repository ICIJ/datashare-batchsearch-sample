# Introduction

This is a project to help [Datashare](https://datashare.icij.org/) users to easily find common searches through the batchSearches.

### How to use it ?
- Choose a *.csv file from this repo.
- Download it
- Go to Datashare
- Click Batch searches
- Choose the downloaded file to create your new batch search


### Something is missing ?
Do not hesitate to contribute or open an issue.

### French IBANs

- Filter on French IBAN

    `/FR[0-9]{2}/`

- Sometimes, OCR confuses "5" and "S"

    `/FR[0-9S]{2}/`

- Match the IBAN written without separator

    `/FR[0-9S]{2}/ OR /FR[0-9S]{2}[0-9S]{10}[0-9a-zA-Z]{11}[0-9S]{2}/`

- I had the idea to add `ìban` as searched term, but it seems that this condition is too restrictive
- I encountered one occurrence that seems complicated to match : "FR 40 3000 2056 4600 0011 7081 X45" because a regexp
like `fr AND /[0-9]{2}/` will collect to many results. So this one will not be matched.
