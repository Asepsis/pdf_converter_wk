# 🏊‍♂️ PDF to CSV converter


## 📌 Description
This programm will convert a pdf for swim-meets to a csv file.
You have to mention a team name by executing the programm with the command line.

The main Branch will convert meldeergebnis from EasyWK to a CSV file.

This is pretty specific and only works propably with meldeergebnis from EasyWK.


## 👨‍💻 Compile 🦀
To build the .exe just run the following command in the terminal:
`cargo build --release`


## 🤷‍♂️ Example
1. Download the PDF from the source
2. Build the .exe
3. execute the programm in the command line

<details>
  <summary>🔍 Some Details</summary>
  
  `Wettkampf` have to look like one of the following in order to get parsed correctly:
  
  ```txt
  Wettkampf 56 - 200m Freistil männlich
  noch Wettkampf 56 - 200m Freistil männlich
  ```

  The headline from a `Lauf` have to look like the following example in order to get parsed correctly:
  
  ```txt
  Lauf 5/12 (ca. 18:52 Uhr)
  ```

  The following Block shows how a `Bahn` can look like to get parsed correctly for junior and master:
  
  #### 👦👧 Junior
  ```txt
    Bahn 1
    Bahn 2 Elias Lastname  2007 Swim-Team 02:24,19
    Bahn 3 Francesco Lastname  2008 Swim-Team 02:22,53
    Bahn 4 Maximilian Lastname  2006 Swim-Team 02:21,48
    Bahn 5 Luis Lastname  2008 Swim-Team 02:22,13
    Bahn 6 Marcell Lastname  2008 Swim-Team 02:22,94
    Bahn 7
    Bahn 8 Jona Willi Schächer  2007 Swim-Team 02:25,13
  ```
  #### 👵🧓 Master
  ```txt
  Bahn 1 Linda Lastname  1983/AK 35 Swim-Team 01:15,00
  Bahn 2 Danae Lastname  1989/AK 30 Swim-Team 01:19,00
  Bahn 3 Birte Lastname  1989/AK 30 Swim-Team 01:20,00
  Bahn 4 Karin Lastname  1995/AK 25 Swim-Team 01:06,10
  Bahn 5 Vanessa Lastname  1997/AK 25 Swim-Team 01:14,96
  Bahn 6 Antonia Lastname  2001/AK 20 Swim-Team 1873  01:19,37
  Bahn 7 Sarah Lastname  2002/AK 20 Swim-Team 1873  01:26,93
  Bahn 8
  ```    
  
</details>


## 👀 How to use

### Input:
`rs_pdf_extract.exe -h`
```sh
PDF to CSV converter 0.1.0
Asepsis
Converts a PDF to a CSV file

USAGE:
    rs_pdf_extract.exe [OPTIONS]

OPTIONS:
    -f, --file <FILE>        Sets the file to use
    -h, --help               Print help information
    -o, --output <OUTPUT>    Sets the output filename
    -v, --verein <VEREIN>    Sets the verein to use
    -V, --version            Print version information

```

`rs_pdf_extract.exe -f 220514-ME-Darmstadt.pdf -v "SVS Griesheim" -o dame.csv`


### Ouput:
`output_name.csv`

### Source:
https://hsv-sued.de/wp-content/uploads/2022/05/220514-ME-Darmstadt.pdf


## 📄 Table of Contents / Example

Below you can see an example output from the programm.
`ZZ` is the short name for Zwischenzeit.

|WK|Uhrzeit|Lauf|Bahn|Name|Jahrgang|Verein|Zeit|ZZ|ZZ|ZZ|ZZ|ZZ|ZZ|ZZ|ZZ|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|100m Freistil|09:14|3|2|Schwimmer Name|2000|SVS Griesheim|01:43,94||||||||

---

## Liability
This programm is only for educational purposes and is not intended to be used in any production environment.