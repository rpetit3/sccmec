sccmec - A tool for typing SCCmec cassettes in assemblies

# sccmec

`sccmec` is a tool for typing SCCmec cassettes in assemblies. It was designed to be easy to
use. Unlike its predecessor, [staphopia-sccmec](https://github.com/staphopia/staphopia-sccmec),
`sccmec` is much simpler to maintain and update. This is because of [camlhmp](https://github.com/rpetit3/camlhmp)
which allows a organization to be defined in a YAML file.

## Contributing

If you would like to become a curator for `sccmec`, please let me know! This could be in the
form of adding new SCCmec types, updating existing ones, or adjusting thresholds. I'm open
to any and all suggestions!

## Supported SCCmec Types

The following SCCmec types are supported by `sccmec`.

| Type | Citation |
|------|----------|
| I    | [Katayama et al. 2000](https://doi.org/10.1128/aac.44.6.1549-1555.2000) |
| II   | [Katayama et al. 2000](https://doi.org/10.1128/aac.44.6.1549-1555.2000), [Ito et al. 2001](https://doi.org/10.1128%2FAAC.45.5.1323-1336.2001) |
| III  | [Katayama et al. 2000](https://doi.org/10.1128/aac.44.6.1549-1555.2000) |
| IV   | [Ma et al. 2002](https://doi.org/10.1128%2FAAC.46.4.1147-1152.2002) |
| V    | [Ito et al. 2004](https://doi.org/10.1128/aac.48.7.2637-2651.2004) |
| VI   | [Oliveira et al. 2006](https://doi.org/10.1128%2FAAC.00629-06) |
| VII  | [Berglund et al. 2008](https://doi.org/10.1128%2FAAC.00087-08) |
| VIII | [Zhang et al. 2009](https://doi.org/10.1128%2FAAC.01118-08) |
| IX   | [Li et al. 2011](https://doi.org/10.1128%2FAAC.01475-10) |
| X    | [Li et al. 2011](https://doi.org/10.1128%2FAAC.01475-10) |
| XI   | [García-Álvarez et al. 2011](https://doi.org/10.1128/aac.01692-15) |
| XII  | [Wu et al. 2015](https://doi.org/10.1128/JCM.39.2.607-612.2001) |
| XIII | [Baig et al. 2018](https://doi.org/10.1016/j.meegid.2018.03.013) |
| XIV  | [Urushibara et al. 2020](https://doi.org/10.1093/jac/dkz406) |
| XV   | [Wang et al. 2022](https://doi.org/10.1093/jac/dkab500) |

## Installation

You can install `sccmec` using `conda`:

```bash
conda create -n sccmec -c conda-forge -c bioconda sccmec
conda activate sccmec
sccmec --help
```

__Note:__ `sccmec` is just a wrapper around [camlhmp-blast](https://github.com/rpetit3/camlhmp?tab=readme-ov-file#camlhmp-blast)
with the defaults for `--yaml` and `--targets` already set. Please don't let this confuse you
when you see all the camels!

## Usage

```bash
 Usage: camlhmp-blast [OPTIONS]                                                                                                  

 🐪 camlhmp-blast 🐪 - Classify assemblies with a camlhmp schema using BLAST                                                     

╭─ Options ───────────────────────────────────────────────────────────────────────────────────╮
│    --version       -V           Show the version and exit.                                  │
│ *  --input         -i  TEXT     Input file in FASTA format to classify [required]           │
│ *  --yaml          -y  TEXT     YAML file documenting the targets and types                 |
|                                   [default: bin/../data/sccmec.yaml] [required]             │
│ *  --targets       -t  TEXT     Query targets in FASTA format                               |
|                                   [default: bin/../data/sccmec.fasta] [required]            │
│    --outdir        -o  PATH     Directory to write output [default: ./]                     │
│    --prefix        -p  TEXT     Prefix to use for output files [default: camlhmp]           │
│    --min-pident        INTEGER  Minimum percent identity to count a hit [default: 95]       │
│    --min-coverage      INTEGER  Minimum percent coverage to count a hit [default: 95]       │
│    --force                      Overwrite existing reports                                  │
│    --verbose                    Increase the verbosity of output                            │
│    --silent                     Only critical errors will be printed                        │
│    --help                       Show this message and exit.                                 │
╰─────────────────────────────────────────────────────────────────────────────────────────────╯
```

As mentioned above, `sccmec` is just a wrapper around `camlhmp-blast`. Except, please note that
the `--yaml` and `--targets` options are already set to the SCCmec defaults. This means you only
need to provide the `--input` option with your assembly file.

### Example Usage

Here's an example of how to use `sccmec` using an assembly file (both uncompressed and GZip
compressed are supported):

```bash
sccmec --input tests/fasta/type-Va-AB121219.fasta.gz --prefix type-v --force
Running camlhmp with following parameters:
    --input tests/fasta/type-Va-AB121219.fasta.gz
    --yaml bin/../data/sccmec.yaml
    --targets bin/../data/sccmec.fasta
    --outdir ./
    --prefix type-v
    --min-pident 95
    --min-coverage 95

Starting camlhmp for SCCmec Typing...
Running blastn...
Processing hits...
Final Results...
                                     SCCmec Typing                                     
┏━━━━━━━━┳━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━━┳━━━━━━━━━┓
┃ sample ┃ type ┃ targets                                ┃ schema ┃ version ┃ comment ┃
┡━━━━━━━━╇━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━━╇━━━━━━━━━┩
│ type-v │ V    │ ccrC1,IS431,IS431_1,IS431_2,mecA,mecR1 │ sccmec │ 1.0.0   │         │
└────────┴──────┴────────────────────────────────────────┴────────┴─────────┴─────────┘
Writing outputs...
Final predicted type written to ./type-v.tsv
Results against each type written to ./type-v.details.tsv
blastn results written to ./type-v.blastn.tsv
```

If needed you could adjust the `--min-pident` and `--min-coverage` options to be more or less
depending on your needs.

Once the tool has completed, you will find three output files in the current directory which
described below.

### Output Files

`camlhmp-blast` will generate three output files:

| File Name              | Description                                     |
|------------------------|-------------------------------------------------|
| `{PREFIX}.tsv`         | A tab-delimited file with the predicted type    |
| `{PREFIX}.blast.tsv`   | A tab-delimited file of all blast hits          |
| `{PREFIX}.details.tsv` | A tab-delimited file with details for each type |

#### Example {PREFIX}.tsv

```tsv
sample	type	targets	schema	version	comment
saureus	V	ccrC1,IS431,IS431_1,IS431_2,mecA,mecR1	sccmec	1.0.0	
```

| Column  | Description                                      |
|---------|--------------------------------------------------|
| sample  | The sample name as determined by `--prefix`      |
| type    | The predicted type                               |
| targets | The targets for the given type that had a hit    |
| schema  | The schema used to determine the type            |
| version | The version of the schema used                   |
| comment | A small comment about the result                 |

#### Example {PREFIX}.blast.tsv

```tsv
qseqid	sseqid	pident	qcovs	qlen	slen	length	nident	mismatch	gapopen	qstart	qend	sstart	send	evalue	bitscore
ccrC1	AB121219.1	100.000	100	1623	28612	1623	1623	0	0	1	1623	16132	17754	0.0	2998
IS431_1	AB121219.1	100.000	100	791	28612	791	791	0	0	1	791	8221	9011	0.0	1461
IS431_1	AB121219.1	99.704	100	675	28612	675	673	2	0	1	675	2693	3367	0.0	1236
IS431_1	AB121219.1	98.519	100	675	28612	675	665	10	0	1	675	8951	8277	0.0	1192
...
```

This is the standard BLAST output with `-outfmt 6`

#### Example {PREFIX}.details.tsv

```tsv
sample	type	status	targets	missing	schema	version	comment
type-v	I	False	IS431,mecA,mecR1	ccrA1,ccrB1,IS1272	sccmec	1.0.0	
type-v	II	False	IS431,mecA,mecR1	ccrA2,ccrB2,mecI	sccmec	1.0.0	
type-v	III	False	IS431,mecA,mecR1	ccrA3,ccrB3,mecI	sccmec	1.0.0	
type-v	IV	False	IS431,mecA,mecR1	ccrA2,ccrB2,IS1272	sccmec	1.0.0	
type-v	V	True	ccrC1,IS431_1,mecA,mecR1,IS431_2		sccmec	1.0.0	
type-v	VI	False	IS431,mecA,mecR1	ccrA4,ccrB4,IS1272	sccmec	1.0.0	
type-v	VII	False	ccrC1,IS431_1,mecA,mecR1,IS431_2	IS12960D	sccmec	1.0.0	
type-v	VIII	False	IS431,mecA,mecR1	ccrA4,ccrB4,mecI	sccmec	1.0.0	Excluded target ccrC1 found, failing type VIII
type-v	IX	False	IS431_1,mecA,mecR1,IS431_2	ccrA1,ccrB1	sccmec	1.0.0	
type-v	X	False	IS431_1,mecA,mecR1,IS431_2	ccrA1,ccrB6	sccmec	1.0.0	
type-v	XI	False	mecA,mecR1	ccrA1,ccrB3,blaZ,mecI	sccmec	1.0.0	
type-v	XII	False	IS431_1,mecA,mecR1,IS431_2	ccrC2	sccmec	1.0.0	
type-v	XIII	False	IS431,mecA,mecR1	ccrC2,mecI	sccmec	1.0.0	
type-v	XIV	False	ccrC1,IS431,mecA,mecR1	mecI	sccmec	1.0.0	
type-v	XV	False	IS431,mecA,mecR1	ccrA1,ccrB6,mecI	sccmec	1.0.0	
```

This file provides a detailed view of the results. The columns are:

| Column  | Description                                        |
|---------|----------------------------------------------------|
| sample  | The sample name as determined by `--prefix`        |
| type    | The predicted type                                 |
| status  | The status of the type (True if failed)            |
| targets | The targets for the given type that had a match    |
| missing | The targets for the given type that were not found |
| schema  | The schema used to determine the type              |
| version | The version of the schema used                     |
| comment | A small comment about the result                   |

## Citations

If you use `sccmec` in your research, please cite the following:

* __[camlgmp](https://github.com/rpetit3/camlhmp)__  
🐪Classification through yAML Heuristic Mapping Protocol 🐪  
Petit III RA [camlhmp: Classification through yAML Heuristic Mapping Protocol](https://github.com/rpetit3/camlhmp) (GitHub)

* __[BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi)__  
Basic Local Alignment Search Tool  
*Camacho C, Coulouris G, Avagyan V, Ma N, Papadopoulos J, Bealer K, Madden TL [BLAST+: architecture and applications](http://dx.doi.org/10.1186/1471-2105-10-421). BMC Bioinformatics 10, 421 (2009)*  

## Naming

I considered thinking of a fun name for this tool, but sometimes it's best to get straight
to the point! So, here we are with `sccmec`.

## License

I'm not a lawyer and MIT has always been my go-to license. So, MIT it is!

## Curators

- [Robert A. Petit III](https://www.robertpetit.com)

