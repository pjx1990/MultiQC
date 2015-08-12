# MultiQC
MultiQC is a tool to aggregate bioinformatics results across many samples into
a single report.

It is written in Python and contains modules for a number of common tools.
Currently, these include [FastQC](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/),
[FastQ Screen](http://www.bioinformatics.babraham.ac.uk/projects/fastq_screen/)
and [Trim Galore!](http://www.bioinformatics.babraham.ac.uk/projects/trim_galore/)
(more to come soon - please suggest any ideas as a new
[issue](https://github.com/ewels/MultiQC/issues)).

## Installation

Either [download](https://github.com/ewels/MultiQC/archive/master.zip) or clone
this repository to your computer:
```
git clone https://github.com/ewels/MultiQC.git
```

Install the MultiQC python package:
```
cd MultiQC
python setup.py develop
```

Add the following line to your `~/.bashrc` or `~/.bash_profile` so that you can run MultiQC anywhere:
```
export PATH="/path/to/MultiQC/scripts:$PATH"
```

## Usage

In the terminal, go to your analysis directory and run `multiqc .` - that's it!
```
cd my_analysis
multiqc .
```

A reports is generated in `multiqc_report/multiqc_report.html` by default
(use the `-o` flag to change this). A zip file of the report is also created
to facilitate easy transfer / sharing.

For more detailed instructions, run `multiqc -h`:

```
multiqc -h
usage: multiqc [-h] [-i TITLE] [-t TEMPLATE] [-o OUTPUT_DIR]
               [-m [MODULE [MODULE ...]]] [-f] [-l LEVEL] [-v]
               <analysis directory>

MultiQC is a tool to create an aggregate report summarising the results of
bioinformatics analyses across numerous samples. To run, supply with a
directory to scan for analysis results. To run here, use 'multiqc .'

positional arguments:
  <analysis directory>  Directory with analysis results to parse. Use '.' for
                        current working directory.

optional arguments:
  -h, --help            show this help message and exit
  -i TITLE, --title TITLE
                        Report title
  -t TEMPLATE, --template TEMPLATE
                        Report template to use. Choose from: default
  -o OUTPUT_DIR, --output_dir OUTPUT_DIR
                        Output directory. Default: multiqc_report
  -m [MODULE [MODULE ...]], --module [MODULE [MODULE ...]]
                        Use only these modules. Choose from: fastqc
  -f, --force           Overwrite any existing reports
  -l LEVEL, --logging LEVEL
                        Level of logging to be printed to the console. Choose
                        from 'DEBUG', 'INFO', 'WARNING', 'ERROR', 'CRITICAL'
  -v, --version         Print the version of the program and exit
```
