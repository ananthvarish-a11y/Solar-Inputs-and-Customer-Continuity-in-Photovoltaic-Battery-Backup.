README - IEEE Access reproducibility files
25 September 2026

PAPER
Solar Inputs and Customer Continuity in Photovoltaic Battery Backup
Varish Ananth, corresponding author: ananthvarish@gmail.com

UPLOAD AND PURPOSE
The complete file Mercer_IEEE_Access_Submission_Reproducibility_v002_2026-09-25.zip
was uploaded as one ZIP, as reported by the author. Its folders should stay
together when downloaded and extracted. There is no need to upload its
individual files separately. This standalone guide accompanies that ZIP;
the ZIP also contains a detailed README and a checksum manifest.

WHAT YOU WILL FIND AFTER EXTRACTION
- editable_source/: current manuscript v029 as a PDF and editable LaTeX,
  bibliography, figures, IEEE template files and build instructions.
- scientific_supplement/: current supplement v022 as PDF and editable text,
  including 28 tables.
- reproduction/: analysis scripts, retained input datasets, source
  provenance, saved outputs and scientific component instructions.
- verification/: a fresh clean-extraction reporting check.
- IEEE_Submission_Reproducibility_Manifest_v002_2026-09-25.json: a file list
  with byte sizes and SHA-256 checksums.

The ZIP is about 25.1 MB compressed and contains 315 files. The retained
datasets include EAGLE-I county source rows, event/reference selections,
county geometry, solar series for 2014-2022 and the reserve,
representative-profile, county and timing inputs used in the paper.

QUICK START
1. Download the complete ZIP and extract it into a new writable folder.
   Do not try to run the scripts while they are still inside the ZIP.
2. Open a terminal in the extracted reproduction/ folder.
3. Use Python 3.12.14 if possible. Install the recorded numerical packages:
      python -m pip install -r IEEE_Reproduction_Requirements_v004_2026-09-20.txt
   The recorded versions are NumPy 2.3.5 and pandas 3.0.1.
4. Run the shortest reproducibility check:
      python -B IEEE_Reproduce_v004_2026-09-20.py --mode reporting --version v901
   If v901 has already been used, replace it with another unused vNNN
   token: the v must be followed by exactly three digits.

EXPECTED OUTPUT OF THE QUICK CHECK
The program should print a small JSON message with "status": "PASS".
It writes:
   reproduction/replay_audit/
     IEEE_Reproduction_reporting_v901_2026-09-20.json
That receipt should also say "status": "PASS". It records 168 verified
base-file hashes and 50 reporting comparisons. The checked package
passed this reporting route from a clean extraction on 25 September
2026. The date 2026-09-20 in generated names identifies the script's
release convention; it is not the date on which you run it.

OTHER NUMERICAL ROUTES
Use a different unused token for every run:
   python -B IEEE_Reproduce_v004_2026-09-20.py --mode benchmark --version v902
   python -B IEEE_Reproduce_v004_2026-09-20.py --mode reserve --version v903
   python -B IEEE_Reproduce_v004_2026-09-20.py --mode representative --version v904
   python -B IEEE_Reproduce_v004_2026-09-20.py --mode county --version v905

Each route writes a PASS/failure receipt named
replay_audit/IEEE_Reproduction_<mode>_<token>_2026-09-20.json.
Computational routes also write a .log file in replay_audit/.
Benchmark writes new CSVs under benchmark/replay_<token>_2026-09-20/.
Reserve writes a Portable_Replay_Comparison JSON in its reproduction
component. Representative writes a Representative_Portable_Comparison
JSON under representative_profile/. County writes replay folders under
county_identification/ and county_cohort/cohort/. For the exact scope
and comparison rules of each route, read
reproduction/IEEE_Reproduction_README_v004_2026-09-20.md.

OPTIONAL PAPER BUILD
The current matching manuscript PDF is already in editable_source/.
To rebuild it, follow
editable_source/IEEE_Editable_Source_README_v012_2026-09-24.md.
That route requires a suitable TeX Live installation and uses the
included class, figures and font resources. It does not rerun the
scientific analyses.

THINGS TO NOTE
- Keep all extracted relative paths intact and work in a writable copy.
  Outputs use new filenames; the scripts refuse reused version tokens.
- Running the scientific code does not call an API or download data.
  Installing Python packages may require internet access.
- Some scientific component filenames say CJSJ because the IEEE study
  builds on that numerical lineage; the current paper is the IEEE
  manuscript v029 and supplement v022.
- A PASS verifies internal calculations and archived file identities
  for that route. It does not establish the accuracy of original
  observations or actual household identities. The quick reporting
  route does not rerun every dispatch or every uncertainty analysis.
- Dataset source and license information is in the component READMEs
  and provenance files. The county MCC source is attributed there
  under CC BY 4.0; other data retain their original terms.
- SHA-256 of the uploaded ZIP:
  cdb59141b7488792ddf14e13b203e1e1e6ca76eed52080c33b2d86801fe0d2d3
  The outer manifest can be used to check individual extracted files.

This guide describes the local files and the author's reported whole-ZIP
upload. The submission portal and uploaded copy were not independently
inspected here.
