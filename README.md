[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-908a85?logo=gitpod)](https://gitpod.io/#https://github.com/rpetit3/sccmec)

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

The following SCCmec subtypes are supported by `sccmec`.

| SubType | Citation |
|------|----------|
| Ia   | [Ito et al. 2001](https://doi.org/10.1128/AAC.45.5.1323-1336.2001) |
| Ib   | [Han et al. 2009](https://doi.org/10.1128/AAC.00772-08), [Oliveira et.al. 2006](https://doi.org/10.1093/jac/dkl208) |
| IIa  | [Katayama et al. 2000](https://doi.org/10.1128/aac.44.6.1549-1555.2000), [Ito et al. 2001](https://doi.org/10.1128/AAC.45.5.1323-1336.2001) |
| IIb  | [Hisata et al. 2005](https://doi.org/10.1128/JCM.43.7.3364-3372.2005) |
| IIc  | [Shore et al. 2005](https://doi.org/10.1128/AAC.49.5.2070-2083.2005) |
| IId  | [Kondp et al. 2007](https://doi.org/10.1128/AAC.00165-06) |
| IIe  | [Han et al. 2009](https://doi.org/10.1128/AAC.00772-08) |
| IVa  | [Ma et al. 2002](https://doi.org/10.1128/AAC.46.4.1147-1152.2002) |
| IVb  | [Ma et al. 2002](https://doi.org/10.1128/AAC.46.4.1147-1152.2002) |
| IVc  | [Ma et al. 2006](https://doi.org/10.1128/JCM.00985-06) |
| IVd  | [Ma et al. 2006](https://doi.org/10.1128/JCM.00985-06) |
| IVg  | [Kwon et al. 2005](https://doi.org/10.1093/jac/dki306) |
| IVh  | [Milheirico et al. 2007](https://doi.org/10.1093/jac/dkm112) |
| IVi  | [Berglund et al. 2009](https://doi.org/10.1093/jac/dkn435) |
| IVj  | [Berglund et al. 2009](https://doi.org/10.1093/jac/dkn435)  |
| IVk  | - |
| IVl  | [Iwao et al. 2012](https://doi.org/10.1007/s10156-012-0379-6) |
| IVm  | [Hosoya et al. 2014](https://doi.org/10.11150/kansenshogakuzasshi.88.840) |
| IVn  | - |
| Va   | [Ito et al. 2004](https://doi.org/10.1128/AAC.48.7.2637-2651.2004) |
| Vb   | [Hisata et al. 2011](https://doi.org/10.1007/s10156-011-0223-4) |
| Vc   | [Li et al. 2011](https://doi.org/10.1128/AAC.01475-10) |

## Installation

You can install `sccmec` using `conda`:

```bash
conda create -n sccmec -c conda-forge -c bioconda sccmec
conda activate sccmec
sccmec --help
```

__Note:__ `sccmec` is utilizes the API from [camlhmp](https://github.com/rpetit3/camlhmp)
with the defaults for `--yaml-targets`, `--yaml-regions`, `--regions` and `--targets`
already set. Please don't let this confuse you when you see all the camels!

## Usage

```bash
 Usage: sccmec [OPTIONS]

 sccmec - typing SCCmec cassettes in assemblies

╭─ Required Options ──────────────────────────────────────────────────────────────────────────────╮
│ *  --input         -i   TEXT  Input file in FASTA format to classify [required]                 │
│ *  --yaml-targets  -yt  TEXT  YAML file documenting the targets and types [required]            │
│ *  --yaml-regions  -yr  TEXT  YAML file documenting the regions and types [required]            │
│ *  --targets       -t   TEXT  Query targets in FASTA format [required]                          │
│ *  --regions       -r   TEXT  Query regions in FASTA format [required]                          │
╰─────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Filtering Options ─────────────────────────────────────────────────────────────────────────────╮
│ --min-targets-pident      INTEGER  Minimum percent identity of targets to count a hit           │
│                                    [default: 90]                                                │
│ --min-targets-coverage    INTEGER  Minimum percent coverage of targets to count a hit           │
│                                    [default: 80]                                                │
│ --min-regions-pident      INTEGER  Minimum percent identity of regions to count a hit           │
│                                    [default: 85]                                                │
│ --min-regions-coverage    INTEGER  Minimum percent coverage of regions to count a hit           │
│                                    [default: 83]                                                │
╰─────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Additional Options ────────────────────────────────────────────────────────────────────────────╮
│ --prefix   -p  TEXT  Prefix to use for output files [default: sccmec]                           │
│ --outdir   -o  PATH  Directory to write output [default: ./]                                    │
│ --force              Overwrite existing reports                                                 │
│ --verbose            Increase the verbosity of output                                           │
│ --silent             Only critical errors will be printed                                       │
│ --version            Print schema and camlhmp version                                           │
│ --help               Show this message and exit.                                                │
╰─────────────────────────────────────────────────────────────────────────────────────────────────╯
```

As mentioned above, `sccmec` utilizes the `camlhmp` API. Except, please note that the
`--yaml-targets`, `--yaml-regions`, `--regions` and `--targets` options are already set to
the SCCmec defaults. This means you only need to provide the `--input` option with your
assembly file.

### Example Usage

Here's an example of how to use `sccmec` using an assembly file (both uncompressed and GZip
compressed are supported):

```bash
sccmec --input tests/fasta/type-Va-AB121219.fasta.gz --prefix type-v

Running sccmec (via camlhmp) with following parameters:
    --input tests/fasta/type-Va-AB121219.fasta.gz
    --yaml-targets /home/rpetit3/repos/sccmec/data/sccmec-targets.yaml
    --yaml-regions /home/rpetit3/repos/sccmec/data/sccmec-regions.yaml
    --targets /home/rpetit3/repos/sccmec/data/sccmec-targets.fasta
    --regions /home/rpetit3/repos/sccmec/data/sccmec-regions.fasta
    --outdir ./
    --prefix type-v
    --min-targets-pident 90
    --min-targets-coverage 80
    --min-regions-pident 85
    --min-regions-coverage 83
Starting camlhmp for SCCmec Typing (targets)...
Running blastn...
Processing target hits...
Starting camlhmp for SCCmec Typing (regions)...
Running blastn...
Processing region hits...
Final Results...
                                           SCCmec Typing
┏━━━━━┳━━━━━┳━━━━━┳━━━━━┳━━━━━┳━━━━━┳━━━━━┳━━━━━┳━━━━━┳━━━━┳━━━━━┳━━━━┳━━━━━┳━━━━┳━━━━━┳━━━━┳━━━━━┓
┃ sa… ┃ ty… ┃ su… ┃ me… ┃ ta… ┃ re… ┃ co… ┃ hi… ┃ ta… ┃ t… ┃ re… ┃ r… ┃ ca… ┃ p… ┃ ta… ┃ r… ┃ co… ┃
┡━━━━━╇━━━━━╇━━━━━╇━━━━━╇━━━━━╇━━━━━╇━━━━━╇━━━━━╇━━━━━╇━━━━╇━━━━━╇━━━━╇━━━━━╇━━━━╇━━━━━╇━━━━╇━━━━━┩
│ ty… │ V   │ Va  │ +   │ cc… │ Va  │ 10… │ 12  │ sc… │ 1… │ sc… │ 1… │ 1.… │ m… │     │ C… │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ b… │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ on │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ 12 │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ h… │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ w… │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ o… │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ or │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ m… │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ o… │     │
│     │     │     │     │     │     │     │     │     │    │     │    │     │    │     │ h… │     │
└─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴────┴─────┴────┴─────┴────┴─────┴────┴─────┘
Final predicted type written to ./type-v.tsv
Target-based results against each type written to ./type-v.targets.details.tsv
Target-based blastn results written to ./type-v.targets.blastn.tsv
Region-based results against each type written to ./type-v.regions.details.tsv
Region-based blastn results written to ./type-v.regions.blastn.tsv
```

If needed, you could adjust the `--min-targets-pident`, `--min-targets-coverage`,
`--min-regions-pident` and/or `--min-regions-coverage` options to be more or less
depending on your needs. But please note the defaults are set to the recommended values.

Once the tool has completed, you will find five output files in the current directory which
described below.

### Output Files

`camlhmp-blast` will generate three output files:

| File Name                      | Description                                                             |
|--------------------------------|-------------------------------------------------------------------------|
| `{PREFIX}.tsv`                 | A tab-delimited file with the predicted type                            |
| `{PREFIX}.targets.blastn.tsv`   | A tab-delimited file of all target-specific blast hits                  |
| `{PREFIX}.targets.details.tsv` | A tab-delimited file with details for each type based on targets        |
| `{PREFIX}.regions.blastn.tsv`   | A tab-delimited file of all full cassette blast hits                    |
| `{PREFIX}.regions.details.tsv` | A tab-delimited file with details for each type based on full cassettes |

#### Example {PREFIX}.tsv

```tsv
sample	type	subtype	mecA	targets	regions	coverage	hits	target_schema	target_schema_version	region_schema	region_schema_version	camlhmp_version	params	target_comment	region_comment	comment
type-v	V	Va	+	ccrC1,IS431,IS431_1,IS431_2,mecA,mecR1	Va	100.00	12	sccmec_targets	1.2.0	sccmec_regions	1.2.0	1.0.1	min-targets-coverage=80;min-targets-pident=90;min-regions-coverage=83;min-regions-pident=85		Coverage based on 12 hits;There were one or more overlapping hits	
```

| Column                | Description                                                                  |
|-----------------------|------------------------------------------------------------------------------|
| sample                | The sample name as determined by `--prefix`                                  |
| type                  | The predicted type (based on targets and full cassettes)                     |
| subtype               | The predicted subtype (based on full cassettes)                              |
| mecA                  | The mecA gene status (+=present or -=absent or not a significant hit)        |
| targets               | The targets for the given type that had a hit                                |
| regions               | The regions for the given type that had a hit                                |
| coverage              | The coverage of the full cassette in the regions column                      |
| hits                  | The number of hits that made up the full cassette coverage                   |
| target_schema         | The schema used to determine the type based on targets                       |
| target_schema_version | The version of the schema used to determine the type based on targets        |
| region_schema         | The schema used to determine the type based on full cassettes                |
| region_schema_version | The version of the schema used to determine the type based on full cassettes |
| camlhmp_version       | The version of camlhmp used to determine the type                            |
| params                | The parameters used to determine the type                                    |
| target_comment        | A small comment about the target results                                     |
| region_comment        | A small comment about the region results                                     |
| comment               | A small comment about the final result                                       |

#### Example {PREFIX}.targets.blastn.tsv

```tsv
qseqid	sseqid	pident	qcovs	qlen	slen	length	nident	mismatch	gapopen	qstart	qend	sstart	send	evalue	bitscore
ccrC1	AB121219.1	100.000	100	1623	28612	1623	1623	0	0	1	1623	16132	17754	0.0	2998
ccrC1	AB121219.1	90.439	100	1677	28612	1684	1523	148	12	1	1677	16132	17809	0.0	2206
IS431_1	AB121219.1	100.000	100	791	28612	791	791	0	0	1	791	8221	9011	0.0	1461
IS431_1	AB121219.1	98.085	100	791	28612	731	717	14	0	1	731	3423	2693	0.0	1273
IS431_1	AB121219.1	99.704	100	675	28612	675	673	2	0	1	675	2693	3367	0.0	1236
...
```

This is the standard BLAST output with `-outfmt 6`

#### Example {PREFIX}.targets.details.tsv

```tsv
sample	type	status	targets	missing	schema	schema_version	camlhmp_version	params	comment
type-v	I	False	IS431,mecA,mecR1	ccrA1,ccrB1,IS1272	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	II	False	IS431,mecA,mecR1	ccrA2,ccrB2,mecI	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	III	False	IS431,mecA,mecR1	ccrA3,ccrB3,mecI	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	IV	False	IS431,mecA,mecR1	ccrA2,ccrB2,IS1272	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	V	True	ccrC1,IS431_1,mecA,mecR1,IS431_2		sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	VI	False	IS431,mecA,mecR1	ccrA4,ccrB4,IS1272	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	VII	False	ccrC1,IS431_1,mecA,mecR1,IS431_2	IS12960D	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	VIII	False	IS431,mecA,mecR1	ccrA4,ccrB4,mecI	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	Excluded target ccrC1 found, failing type VIII
type-v	IX	False	IS431_1,mecA,mecR1,IS431_2	ccrA1,ccrB1	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	X	False	IS431_1,mecA,mecR1,IS431_2	ccrA1,ccrB6	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	XI	False	mecA,mecR1	ccrA1,ccrB3,blaZ,mecI	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	XII	False	IS431_1,mecA,mecR1,IS431_2	ccrC2	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	XIII	False	IS431,mecA,mecR1	ccrC2,mecI	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	XIV	False	ccrC1,IS431,mecA,mecR1	mecI	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	
type-v	XV	False	IS431,mecA,mecR1	ccrA1,ccrB6,mecI	sccmec_targets	1.2.0	1.0.1	min-coverage=90;min-pident=80	

```

This file provides a detailed view of the results. The columns are:

| Column          | Description                                          |
|-----------------|------------------------------------------------------|
| sample          | The sample name as determined by `--prefix`          |
| type            | The type being tested                                |
| status          | The status of the type (True if failed)              |
| targets         | The targets for the given type that had a match      |
| missing         | The targets for the given type that were not found   |
| schema          | The schema used to determine the type                |
| schema_version  | The version of the schema used to determine the type |
| camlhmp_version | The version of camlhmp used to determine the type    |
| params          | The parameters used to determine the type            |
| comment         | A small comment about the result                     |

#### Example {PREFIX}.regions.blastn.tsv

```tsv
qseqid	sseqid	pident	qcovs	qlen	slen	length	nident	mismatch	gapopen	qstart	qend	sstart	send	evalue	bitscore
III	AB121219.1	99.371	25	68256	28612	4132	4106	26	0	24230	28361	8220	4089	0.0	7487
III	AB121219.1	86.738	25	68256	28612	5067	4395	628	42	59204	64248	17954	12910	0.0	5594
III	AB121219.1	94.259	25	68256	28612	3240	3054	172	11	44582	47815	22419	19188	0.0	4940
III	AB121219.1	98.421	25	68256	28612	1837	1808	25	4	27952	29787	4458	2625	0.0	3229
III	AB121219.1	99.494	25	68256	28612	791	787	3	1	34225	35015	3423	2634	0.0	1437
...
```

This is the standard BLAST output with `-outfmt 6`

#### Example {PREFIX}.regions.details.tsv

```tsv
sample	type	status	targets	missing	coverage	hits	schema	schema_version	camlhmp_version	params	comment
type-v	Ia	False		Ia	17.67	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	Ib	False		Ib	16.61	2	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 2 hits
type-v	IIa	False		IIa	11.85	11	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 11 hits;There were one or more overlapping hits
type-v	IIb	False		IIb	0.00	0	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	
type-v	IIc	False		IIc	17.39	4	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 4 hits;There were one or more overlapping hits
type-v	IId	False		IId	0.00	0	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	
type-v	IIe	False		IIe	1.54	1	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	
type-v	III	False		III	24.50	18	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 18 hits;There were one or more overlapping hits
type-v	IVa	False		IVa	29.35	13	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 13 hits;There were one or more overlapping hits
type-v	IVb	False		IVb	33.19	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	IVc	False		IVc	23.56	14	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 14 hits;There were one or more overlapping hits
type-v	IVd	False		IVd	7.78	1	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	
type-v	IVg	False		IVg	30.66	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	IVi	False		IVi	30.85	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	IVj	False		IVj	30.58	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	IVk	False		IVk	16.00	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	IVl	False		IVl	19.79	13	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 13 hits;There were one or more overlapping hits
type-v	IVm	False		IVm	25.73	14	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 14 hits;There were one or more overlapping hits
type-v	IVn	False		IVn	28.15	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	Va	True	Va		100.00	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	Vb	False		Vb	64.55	17	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 17 hits;There were one or more overlapping hits
type-v	Vc	False		Vc	50.14	17	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 17 hits;There were one or more overlapping hits
type-v	VI	False		VI	29.79	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	VII	False		VII	45.86	15	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 15 hits;There were one or more overlapping hits
type-v	VIII	False		VIII	16.95	9	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 9 hits;There were one or more overlapping hits
type-v	IX	False		IX	15.33	11	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 11 hits;There were one or more overlapping hits
type-v	X	False		X	13.68	16	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 16 hits;There were one or more overlapping hits
type-v	XI	False		XI	0.00	0	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	
type-v	XII	False		XII	19.37	15	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 15 hits;There were one or more overlapping hits
type-v	XIII	False		XIII	28.39	12	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 12 hits;There were one or more overlapping hits
type-v	XIV	False		XIV	14.50	16	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 16 hits;There were one or more overlapping hits
type-v	XV	False		XV	17.21	11	sccmec_regions	1.2.0	1.0.1	min-coverage=85;min-pident=83	Coverage based on 11 hits;There were one or more overlapping hits
```

This file provides a detailed view of the results. The columns are:

| Column          | Description                                                |
|-----------------|------------------------------------------------------------|
| sample          | The sample name as determined by `--prefix`                |
| type            | The type being tested                                      |
| status          | The status of the type (True if failed)                    |
| targets         | The targets for the given type that had a match            |
| missing         | The targets for the given type that were not found         |
| coverage        | The coverage of the full cassette                          |
| hits            | The number of hits that made up the full cassette coverage |
| schema          | The schema used to determine the type                      |
| schema_version  | The version of the schema used to determine the type       |
| camlhmp_version | The version of camlhmp used to determine the type          |
| params          | The parameters used to determine the type                  |
| comment         | A small comment about the result                           |

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

