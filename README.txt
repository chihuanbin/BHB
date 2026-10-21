Data and code for Public Radial-Velocity Selection Alters the Transverse-Speed Distribution of LAMOST-selected Metal-poor BHB Candidates
Version 1.0.0; prepared 19 October 2026. DOI not yet assigned; no publication performed.
Creators: Huanbin Chi and Qianzhi Ma.

PURPOSE AND SCIENTIFIC SCOPE
This is a data/code archive supporting the current revised manuscript, not an article
publication. The canonical result directory is workspace/minimal_revision_20261019/analysis/.
metadata/CURRENT_RESULT_INDEX.json enumerates current branch results. Older input paths
retain their names for execution compatibility; their date does not make them the current
statistical result. No reviewer reports, response letters, redlines, author private answers,
cover letters, credentials, downloaded journal PDFs or older complete manuscripts are included.

Frozen population: 206 unique physical Gaia sources, historical recorded RV adoption 120/86.
The 86 recorded negatives are UNKNOWN for globally complete historical availability.
Median speed: 67.5 vs 169.3 km/s. Both original-partition repaired p=0.0106/0.0088 and
source-ID reference p=0.6759/0.6429 are preserved with their full 10,000-draw nulls.
The former is a source-driven sensitivity after earlier results were known, not a new
preregistered confirmation. Results support conditional-association evidence with partition
sensitivity, not partition-invariant significance. Weights assess internal reconstruction.
All three paired absolute-error-improvement intervals include zero in the recorded branch.

LAYOUT
workspace/minimal_revision_20261019/analysis/: current full numerical results and fit ledgers.
workspace/minimal_revision_20261019/source_data/: source/product audits and support tables.
figure_source_data/: exact source tables copied from the current manuscript figure project.
figures/: 15 PDF figures, plus SVG copies of the three revised composites.
workspace/bhb_revision_evidence_v2/src/: immutable core and vendored zero-point implementation.
workspace/bhb_revision_evidence_v2/data/: original derived inputs and public query captures.
workspace/bhb_revision_evidence_v2/outputs/shared_engine/: six full speed draw banks and
generator support arrays, rather than a second conflicting set of branch p values.
workspace/bhb_revision_evidence_v2/checkpoints/: 5,000 bootstrap index/fold records and
600 compact simulations (1800 complete 499-score method results). Conditional simulation
draw/uniform arrays are omitted to reduce size; the frozen source and SeedSequence specify
their regeneration. metadata/SIMULATION_CHECKPOINTS.json records full-original hashes,
derived hashes and retained keys. No reduction is made to real-data conditional draw banks.
workspace/manuscript/universe_submission_lock/build/supplement_bundle/data/: the five
frozen original input tables, including the 3583-row parent. This path is an input location.
workspace/data/ and workspace/output/: earlier input catalogue stages/public survey captures.
upstream/MSFA_Net_Data.zip: attributed upstream dataset, separately identified by its DOI.
metadata/: current result index, protocol, sources, table inventory, field dictionary,
figure mapping, references, scoped rights, and source-to-package hash provenance.

REPRODUCE AFTER UNZIPPING (run from this directory)
1. File integrity, standard Python only:
   python verify_release.py
2. Saved-array arithmetic and all source/bootstrap/simulation identities, no fitting/network:
   python replay_results.py
3. Create an environment using environment/environment.yml, or install the pinned packages
   in a Python 3.13.5 environment: python -m pip install -r environment/requirements.txt
4. Refit the reference point and the first 10 null draws per generator into a NEW directory:
   python refit_analysis.py --branch paper_raw --null-count 10 --output ../refit_source_id
5. Refit the original fixed partition sensitivity:
   python refit_analysis.py --partition original --null-count 10 --output ../refit_original
6. For all 10,000 draws per generator, use --null-count 10000. Other --branch values:
   paper_zpt, dr12_scoped_raw, dr12_general_raw, domain_raw. Original partition is defined
   only for paper_raw. A 10-draw prefix is a software smoke test, never the full-budget p value.
7. Rebuild the three revised main composites into a NEW directory:
   python render_main_figures.py --output ../rebuilt_main_figures
The three standalone scripts create new outputs; the frozen result tables are not replaced.
Observed/null score deviations under a different numerical environment must be disclosed.
Full bootstrap and simulation algorithms are in the immutable historical engine source
workspace/bhb_revision_evidence_v2/scripts/run_shared_engine.py. This historical entrypoint
writes its workspace outputs if executed directly; use a separate copied workspace for
such expensive recomputation. It predates the 19 October zero-point and original-partition
updates. Use refit_analysis.py and CURRENT_RESULT_INDEX.json for current observed/CRT results.
Full-pipeline statistical fitting has NOT been rerun merely to create this archive.

DEFINITIONS AND LIMITS
R_paper is recorded adoption, not proof that every public survey was exhaustively searched.
paper_zpt changes source-specific parallax, speed and log distance together on the same parent.
dr12_scoped_raw admits parameter-product RVs (135/71); dr12_general_raw also admits general
MRS products (150/56). These scopes are not interchangeable or pure release-only changes.
domain_raw is a 200-source SLAM parameter-grid sensitivity (117/83), not validated BHB purity.
DR12 query captures are from 2026-10-13. There is no new exhaustive current live survey scan.
18 first-ever observation histories and historical negative completeness remain UNKNOWN.
The fixed solar vector (11.1,245.0,7.25) km/s is an illustrative coordinate sensitivity;
its total-V literature source is undocumented. Independent classification purity and a
validated expanded-parent extinction/distance/coverage contract remain unavailable.
See metadata/DATA_DICTIONARY.txt and SOURCES.csv before reusing catalogue sentinel values.

RIGHTS AND CITATION
Author-created data, figures and documentation: CC BY 4.0. Author-created software: MIT.
Third-party catalogue values and vendored code retain source terms; read LICENSE.txt,
THIRD_PARTY_NOTICES.txt and metadata/RIGHTS_SCOPE.csv. These scopes override any blanket
interpretation of the repository's license badges. Upstream DOI 10.5281/zenodo.20390763
belongs to MSFA-Net. Add only the new archive's actually assigned VERSION DOI to the
outward CITATION.cff after reserving it; a local placeholder is not a registered DOI.
The public citation is Chi, H. & Ma, Q. (publication year), title above, version 1.0.0,
Zenodo, assigned version DOI. Development repository: https://github.com/chihuanbin/BHB.
