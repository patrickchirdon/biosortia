Mass Spectroscopy Peaks to Properties Prediction

Overview of Phase 0  of a Clinical Trial
	Phase 0 of a clinical trial before animal testing is a combination of Autodock Vina or Rosetta docking with protein structures from Alphafold, Meta, or RCSB. Quantitative Structure Activity Relationship (QSAR) modeling  using machine learning, typically in rdkit or scikitlearn or keras, screens molecules for inhibition or activation using chembl or pubchem databases typically prior to protein ligand docking.  QSAR modeling uses chembl or pubchem databases, using inhibitory IC50 or activation data collected from experiments. Molecules can be generated from chemical scaffolds, keeping the core scaffold the same and modifying only the R groups, using Data Warrior.  Data Warrior stores chemical data and can screen for basic physical or toxicity properties, as well as providing a visualization for datasets.  Molecules are represented in SMILES format.  In addition to QSAR modeling, the SMILES molecules can be filtered for substructures called SMARTS.  SMARTS are useful for rule based models in organic chemistry. Rule based models are the traditional alternative to machine learning based approaches.  Structural alerts are the smallest possible substructure within a molecule having a biological activity and can be found in the literature or from databases like ochem.eu.  However, sometimes the chemical structure is not known.  In these cases, software like MSNovelist can guess the structures from mass spectroscopy data.  
ADMET Screening
	As an initial first screen, software libraries screen for adsorption, distribution, metabolism, and excretion properties (ADMET) using online sources like SwissADME or ADMETlab2.0.  Toxicity modeling is done with QSAR modeling in rdkit or using models like Tox21 from Deepchem.  Although some might argue that predicting accurately how compounds travel through the body is equivalent to the feat of landing someone on Mars, in silico screens are useful for predicting which compounds are not suitable for preclinical testing.  Many compounds are not able to cross the blood brain barrier, are not transported well in the blood, distributed to various compartments of the body, or are unable to pass through the stomach or intestines.  The liver metabolizes these compounds and they are often not able to reach the target site. Predicting how compounds are metabolized in the liver by cytochromes prior to experiments is often useful, as is predicting transport with plasma proteins, volume of distribution, intestinal absorption, GI absorption, and half life, or renal clearance.  Ideally, after in silico screening the goal is to have all the possible conformations of a scaffold generated with all the adsorption, metabolism, excretion, and toxicity data predicted for each compound with bioactivity scores and protein ligand binding energy scores so that the compounds can be prioritized.  Bad compounds never leave the computer, potentially saving costly experiments and time.  Prior to phases 1-3 of a clinical study, a preclinical study is necessary to assess toxicity and other properties of the best compounds.  This can be done at labs like Charles River or using animal models.  Phases 1-3 of a clinical study assess safety and efficacy of a drug.  These are performed at hospital systems by contract research organizations such as Trialspark, etc that match academic labs and compounds to pharmaceutical companies.  There is a high failure rate of clinical trials and in many cases the trials cost almost a billion dollars and 10 years to complete. 
	
The Role of Small Chemical Companies

	 However, this does not mean that small academic labs and companies should be discouraged from researching new drugs.  There are only 2000 FDA approved drugs on the market.  There’s also 55,000 FDA regulated dietary supplements.  Companies must apply for FDA registration of dietary supplements prior to testing and for insurance.  The compounds must be manufactured in certified facilities and labeled.  It’s worth noting that it is considerably easier to get a dietary supplement to market than it is to get a drug to market.  Probiotics and compounds from ‘safe’ sources are commonly patented and sold at health food stores.  These can be tested at companies like Creative Biolabs. For example, the U.S. PTO would allow someone to patent a compound or a set of compounds sharing a common chemical scaffold derived from chili peppers for 20 years for a condition like baldness because chili peppers are known to be safe.  These compounds can be licensed out to larger pharmaceutical companies for profit and royalties, often like Biosortia Microbiotics does.  Biosortia isolated compounds derived from algae and the microbiome and characterized them using mass spectroscopy.  Seaweed is a natural source of probiotics, and likely source of numerous drugs and nanoparticles (which can be harvested from algae for improving drug delivery, solubility, and distribution if compounds need to be coated after failing in trial), including antioxidants like asthataxicin and omega 3’s.  Small companies like Biosortia will likely provide raw materials to larger pharmaceutical companies, but it is also possible for smaller pharmaceutical companies to contribute to orphan drug research for rare diseases with financial costs covered under the orphan drug act.  Small companies can provide the computational know-how, raw materials, and  partner with clinical trials and larger pharmaceutical companies to get drugs to market and play an integral part in the drug discovery process. 
	Biosortia, like many companies, did not know the structures of their compounds and had only mass spectroscopy data.  The mass spectroscopy data could be converted to chemical structures using MSNovelist in order to perform protein ligand docking. We also wanted to predict chemical properties for adsorption, distribution, metabolism, and excretion. Rather than using SMILES for QSAR models, we went directly from mass spectroscopy peaks to properties with high accuracy.  The assay data could come from Chembl or Pubchem.  However, most of our ADME model data came from the popular adsorption, metabolism, excretion, and transport prediction software named ADMETlab2.0.  We wanted to note that going directly from mass spectroscopy peaks is under-published, with only one company Enveda Bio publishing Ms2Prop at the time of writing.  




About
logS 

The logarithm of aqueous solubility value. The first step in the drug absorption process is the disintegration of the tablet or capsule, followed by the dissolution of the active drug. Low solubility is detrimental to good and complete oral absorption, and early measurement of this property is of great importance in drug discovery. Results interpretation: The predicted solubility of a compound is given as the logarithm of the molar concentration (log mol/L). Compounds in the range from -4 to 0.5 log mol/L will be considered proper. 

logP 

The logarithm of the n-octanol/water distribution coefficient. log P possess a leading position with considerable impact on both membrane permeability and hydrophobic binding to macromolecules, including the target receptor as well as other proteins like plasma proteins, transporters, or metabolizing enzymes. Results interpretation: The predicted logP of a compound is given as the logarithm of the molar concentration (log mol/L). Compounds in the range from 0 to 3 log mol/L will be considered proper. logD7.4 

The logarithm of the n-octanol/water distribution coefficients at pH=7.4. To exert a therapeutic effect, one drug must enter the blood circulation and then reach the site of action. Thus, an eligible drug usually needs to keep a balance between lipophilicity and hydrophilicity to dissolve in the body fluid and penetrate the biomembrane effectively. Therefore, it is important to estimate the n-octanol/water distribution coefficients at physiological pH (logD7.4) values for candidate compounds in the early stage of drug discovery. Results interpretation: The predicted logD7.4 of a compound is given as the logarithm of the molar concentration (log mol/L). Compounds in the range from 1 to 3 log mol/L will be considered proper. 

QED 

A measure of drug-likeness based on the concept of desirability. QED is calculated by integrating the outputs of the desirability functions based on eight drug-likeness related properties, including MW, log P, NHBA, NHBD, PSA, Nrotb, the number of aromatic rings (NAr), and the number of alerts for undesirable functional groups. Here, average descriptor weights were used in the calculation of QED. The QED score is calculated by taking the geometric mean of the individual desirability functions, given by QED=exp⁡(1n∑i=1nln⁡di)QED=exp(n1​∑i=1n​lndi​), where di indicates the dthdesirability function and n = 8 is the number of drug-likeness related properties. Results interpretation: The mean QED is 0.67 for the attractive compounds, 0.49 for the unattractive compounds and 0.34 for the unattractive compounds considered too complex. Empirical decision: > 0.67: excellent; ≤ 0.67: poor 

Fsp3 

Fsp3, the number of sp3 hybridized carbons/total carbon count, is used to determine the carbon saturation of molecules and characterize the complexity of the spatial structure of molecules. It has been demonstrated that the increased saturation measured by Fsp3 and the number of chiral centers in the molecule increase the clinical success rate, which might be related to the increased solubility, or the fact that the enhanced 3D features allow small molecules to occupy more target space. Results interpretation: Fsp3 ≥ 0.42 is considered a suitable value. Empirical decision: ≥ 0.42：excellent; ＜0.42: poor 

NPscore The Natural Product-likeness score is a useful measure which can help to guide the design of new molecules toward interesting regions of chemical space which have been identified as “bioactive regions” by natural evolution. The calculation consists of molecule fragmentation, table lookup, and summation of fragment contributions. Results interpretation: The calculated score is typically in the range from −5 to 5. The higher the score is, the higher the probability is that the molecule is a NP. 

Lipinski Rule 

Content: MW≤500; logP≤5; Hacc≤10; Hdon≤5 Results interpretation: If two properties are out of range, a poor absorption or permeability is possible, one is acceptable. Empirical decision: < 2 violations：excellent ；≥2 violations: poor 

PAINS 

Pan Assay Interference Compounds (PAINS) is one of the most famous frequent hitters filters, which comprises 480 substructures derived from the analysis of FHs determined by six target-based HTS assay. By application of these filters, it is easier to screen false positive hits and to flag suspicious compounds in screening databases. One of the most authoritative medicine magazines Journal of Medicinal Chemistry even requires authors to provide the screening results with the PAINS alerts of active compounds when submitting manuscripts. Results interpretation: If the number of alerts is not zero, the users could check the substructures by the DETIAL button. 

Chelator Rule 

Chelating compounds. There are 55 substructures in this endpoint. 

Caco-2 Permeability 

Before an oral drug reaches the systemic circulation, it must pass through intestinal cell membranes via passive diffusion, carrier-mediated uptake or active transport processes. The human colon adenocarcinoma cell lines (Caco-2), as an alternative approach for the human intestinal epithelium, has been commonly used to estimate in vivo drug permeability due to their morphological and functional similarities. Thus, Caco-2 cell permeability has also been an important index for an eligible candidate drug compound. Results interpretation: The predicted Caco-2 permeability of a given compound is given as the log cm/s. A compound is considered to have a proper Cao-2 permeability if it has predicted value >-5.15log cm/s. Empirical decision: > -5.15: excellent (green); otherwise: poor (red) 

T1/2 

The half-life of a drug is a hybrid concept that involves clearance and volume of distribution, and it is arguably more appropriate to have reliable estimates of these two properties instead. Result interpretation: Molecules with T1/2 > 3 were classified as T1/2 - (Category 0), while molecules with T1/2 ≤ 3 were classified as T1/2 + (Category 1). The output value is the probability of being T1/2+, within the range of 0 to 1. Empirical decision: 0-0.3: excellent; 0.3-0.7: medium; 0.7-1.0(++): poor 

96 hour fathead minnow LC50 (concentration of the test chemical in water in mg/L that causes 50% of fathead minnow to die after 96 hours). The unit of LC50FM is −log10[(mg/L)/(1000*MW)]. LC50DM 

48 hour Daphnia magna LC50 (concentration of the test chemical in water in mg/L that causes 50% of Daphnia magna to die after 48 hours). The unit of LC50DM is −log10[(mg/L)/(1000*MW)]. NR-AR 
Tox 21
H-HT 

The human hepatotoxicity. Drug induced liver injury is of great concern for patient safety and a major cause for drug withdrawal from the market. Adverse hepatic effects in clinical trials often lead to a late and costly termination of drug development programs. Result interpretation: Category 0: H-HT negative(-); Category 1: H-HT positive(+). The output value is the probability of being toxic, within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

IGC50 Androgen receptor (AR), a nuclear hormone receptor, plays a critical role in AR-dependent prostate cancer and other androgen related diseases. Endocrine disrupting chemicals (EDCs) and their interactions with steroid hormone receptors like AR may cause disruption of normal endocrine function as well as interfere with metabolic homeostasis, reproduction, developmental and behavioral functions. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being AR agonists, within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

NR-AR-LBD Androgen receptor (AR), a nuclear hormone receptor, plays a critical role in AR-dependent prostate cancer and other androgen related diseases. Endocrine disrupting chemicals (EDCs) and their interactions with steroid hormone receptors like AR may cause disruption of normal endocrine function as well as interfere with metabolic homeostasis, reproduction, developmental and behavioral functions. Result interpretation: Category 1: actives ; Category 0: inactives. Molecules that labeled 1 in this bioassay may bind to the LBD of androgen receptor. The output value is the probability of being actives, within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

NR-AhR The Aryl hydrocarbon Receptor (AhR), a member of the family of basic helix-loop-helix transcription factors, is crucial to adaptive responses to environmental changes. AhR mediates cellular responses to environmental pollutants such as aromatic hydrocarbons through induction of phase I and II enzymes but also interacts with other nuclear receptor signaling pathways. Result interpretation: Category 1: actives ; Category 0: inactives. Molecules that labeled 1 may activate the aryl hydrocarbon receptor signaling pathway. The output value is the probability of being actives, within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

NR-Aromatase Endocrine disrupting chemicals (EDCs) interfere with the biosynthesis and normal functions of steroid hormones including estrogen and androgen in the body. Aromatase catalyzes the conversion of androgen to estrogen and plays a key role in maintaining the androgen and estrogen balance in many of the EDC-sensitive organs. Result interpretation: Category 1: actives ; Category 0: inactives. Molecules that labeled 1 are regarded as aromatase inhibitors that could affect the balance between androgen and estrogen. The output value is the probability of being actives, within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

NR-ER Estrogen receptor (ER), a nuclear hormone receptor, plays an important role in development, metabolic homeostasis and reproduction. Endocrine disrupting chemicals (EDCs) and their interactions with steroid hormone receptors like ER causes disruption of normal endocrine function. Therefore, it is important to understand the effect of environmental chemicals on the ER signaling pathway. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

NR-ER-LBD Estrogen receptor (ER), a nuclear hormone receptor, plays an important role in development, metabolic homeostasis and reproduction. Two subtypes of ER, ER-alpha and ER-beta have similar expression patterns with some uniqueness in both types. Endocrine disrupting chemicals (EDCs) and their interactions with steroid hormone receptors like ER causes disruption of normal endocrine function. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

NR-PPAR-gamma The peroxisome proliferator-activated receptors (PPARs) are lipid-activated transcription factors of the nuclear receptor superfamily with three distinct subtypes namely PPAR alpha, PPAR delta (also called PPAR beta) and PPAR gamma (PPARg). All these subtypes heterodimerize with Retinoid X receptor (RXR) and these heterodimers regulate transcription of various genes. PPAR-gamma receptor (glitazone receptor) is involved in the regulation of glucose and lipid metabolism. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

SR-ARE Oxidative stress has been implicated in the pathogenesis of a variety of diseases ranging from cancer to neurodegeneration. The antioxidant response element (ARE) signaling pathway plays an important role in the amelioration of oxidative stress. The CellSensor ARE-bla HepG2 cell line (Invitrogen) can be used for analyzing the Nrf2/antioxidant response signaling pathway. Nrf2 (NF-E2-related factor 2) and Nrf1 are transcription factors that bind to AREs and activate these genes. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

SR-ATAD5 ATPase family AAA domain-containing protein 5. As cancer cells divide rapidly and during every cell division they need to duplicate their genome by DNA replication. The failure to do so results in the cancer cell death. Based on this concept, many chemotherapeutic agents were developed but have limitations such as low efficacy and severe side effects etc. Enhanced Level of Genome Instability Gene 1 (ELG1; human ATAD5) protein levels increase in response to various types of DNA damage. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

SR-HSE Heat shock factor response element. Various chemicals, environmental and physiological stress conditions may lead to the activation of heat shock response/ unfolded protein response (HSR/UPR). There are three heat shock transcription factors (HSFs) (HSF-1, -2, and -4) mediating transcriptional regulation of the human HSR. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

SR-MMP Mitochondrial membrane potential (MMP), one of the parameters for mitochondrial function, is generated by mitochondrial electron transport chain that creates an electrochemical gradient by a series of redox reactions. This gradient drives the synthesis of ATP, a crucial molecule for various cellular processes. Measuring MMP in living cells is commonly used to assess the effect of chemicals on mitochondrial function; decreases in MMP can be detected using lipophilic cationic fluorescent dyes. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

SR-p53 p53, a tumor suppressor protein, is activated following cellular insult, including DNA damage and other cellular stresses. The activation of p53 regulates cell fate by inducing DNA repair, cell cycle arrest, apoptosis, or cellular senescence. The activation of p53, therefore, is a good indicator of DNA damage and other cellular stresses. Result interpretation: Category 1: actives ; Category 0: inactives. The output value is the probability of being actives within the range of 0 to 1. Empirical decision: 0-0.3: excellent (green); 0.3-0.7: medium (yellow); 0.7-1.0(++): poor (red) 

Agrawal A, Johnson S L, Jacobsen J A, et al. Chelator fragment libraries for targeting metalloproteinases[J]. ChemMedChem, 2010, 5(2): 195-9. 

Ertl P, Roggo S, Schuffenhauer A. Natural product-likeness score and its application for prioritization of compound libraries[J]. J Chem Inf Model, 2008, 48(1): 68-74. 




----------------------------------------------
Results

https://www.slideshare.net/PatrickChirdon1/biosortia2proppptx?fbclid=IwAR26psj1zzyKpBClr-FbtDCS4pg0tfsc613hVGixxt84aE5jcVqgz9NyPT8



library--https://hmdb.ca/metabolites?utf8=%E2%9C%93&quantified=1&blood=1&urine=1&saliva=1&csf=1&feces=1&sweat=1&breast_milk=1&bile=1&amniotic_fluid=1&other_fluids=1&microbial=1&filter=true

i was able to get an r2 of one for caco permeability, half life, log S, logD, bioconcentration, lc50fm, lc50dm, fsp3, and igc50 on test data excluded from training. https://pubs.acs.org/doi/10.1021/acs.est.2c02536

for solubility lasso lars had r^2 of 1, lasso r^2 of 1, and elastic r^2 of 1 on test data.
bioavailability-- lasso lars had a r^2 of 1 on test data, lasso r^2 of 1, and elastic r^2 of 1.
for fraction of sp3 hybridized carbons (a measure of selectivity of binding)-- lasso lars had a r^2 of 1 on training data (first model for lasso lars to work), lasso r^2 of 1, and elastic r^2 of 1.
alogp and psa with an r^2 of 1 on test data. 
mglur5 (autism target), hsp90a (neuroinflammatory target, charcot marie tooth disease), calpain 1 (covid 19 target), aphid mortality model. r^2 of 1 with elastic, lasso, and lasso_lars models

DeepChem Tox21

https://github.com/patrickchirdon/tox21_toxicity_prediction

train_scores: {'mean-roc_auc_score': 0.9437261510314645}

 test_scores: {'mean-roc_auc_score': 0.7088654555374828}

on the QED test data set--
Mean absolute error: 0.14206431066163
Mean squared error: 0.84021645902190
Root mean squared error: 0.91663

Test set of CNS compounds vs non CNS compounds it was not trained on r^2 of .78 for logP and .84 for PSA for CNS compounds.  The non CNS compounds had a r^2 of .97 for PSA.  non CNS compounds had a logP r^2 of 1.  


ms2prop had an r2 of .73 on the independent test set across all the QED properties, we have an r2 of 88%


https://stackabuse.com/linear-regression-in-python-with-scikit-learn/



RESOURCES

https://www.rosettacommons.org/

https://openmolecules.org/datawarrior/

https://pubchem.ncbi.nlm.nih.gov//edit3/index.html

https://www.chemdiv.com/catalog/complete-list-of-compounds-libraries/?https://www.chemdiv.com/complete-list-of-compounds-libraries/&gclid=EAIaIQobChMIh4OokPKN_QIVVAetBh075gGEEAAYAyAAEgJlPvD_BwE

https://sciencesolutions.wiley.com/solutions/technique/gc-ms/mass-spectra-of-flavors-and-fragrances-of-natural-and-synthetic-compounds-3rd-edition/

https://admetmesh.scbdd.com/

Databases-- 
https://www.nature.com/articles/s41592-022-01685-y?utm_source=nmeth_etoc&utm_medium=email&utm_campaign=toc_41592_20_2&utm_content=20230211

GNPS library--
https://ccms-ucsd.github.io/GNPSDocumentation/gnpslibraries/

https://ec.europa.eu/food/plant/pesticides/eu-pesticides-database/start/screen/active-substances

https://cbirt.net/meta-ai-releases-esm-metagenomic-atlas-a-repository-of-over-600-million-predicted-protein-structures/

https://comptox.epa.gov/genra/

https://www.metaboanalyst.ca/MetaboAnalyst/ModuleView.xhtml

https://ipb-halle.github.io/MetFrag/projects/metfragweb/

https://hmdb.ca/spectra/ms_ms/search

https://pubchem.ncbi.nlm.nih.gov/

https://www.ebi.ac.uk/chembl/

https://ochem.eu/home/show.do

https://alphafold.ebi.ac.uk/

https://www.rcsb.org/

https://cfmid.wishartlab.com/predict

https://massbank.eu/MassBank/Search

http://www.swissadme.ch

https://deepchem.io/

https://biolynceus.net/lot-125-higher-yields-less-water-less-fertilizer/


------------------------------------------------

dietary supplements-- https://www.liebertpub.com/doi/10.1089/aivt.2018.0020

intersting startups in this space seed probiotics
-------------------------------------------------
QED Calculation-- QED is lipinski + medicinal chemistry rules and aromatic ring count
https://github.com/kevinid/molecule_generator/blob/master/rdkit_contrib/qed.py
https://bioinformaticsreview.com/20220803/how-to-calculate-drug-likeness-using-rdkit/
https://sharifsuliman1.medium.com/understanding-drug-likeness-filters-with-rdkit-and-exploring-the-withdrawn-database-ebd6b8b2921e
PSA is a commonly used medicinal chemistry metric for the optimization of a drug's ability to permeate cells. Molecules with a polar surface area of greater than 140 angstroms squared (Å2) tend to be poor at permeating cell membranes.[1]

for CNS compounds, moderately polar (PSA<79 Å2) and relatively lipophilic (log P from +0.4 to +6.0) molecules have a high probability to access the CNS.
https://pubmed.ncbi.nlm.nih.gov/12036371/
https://en.wikipedia.org/wiki/Octanol-water_partition_coefficient
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2628535/
https://pubmed.ncbi.nlm.nih.gov/12036371/

rotatable bonds also influence oral bioavailability according to the article above. octanol-water partition coefficient (ALOGP, a measure of solubility) and psa/polar surface area (cell permeability)

source of the SMARTS structures used by the QED algorithm-- https://application.wiley-vch.de/contents/jc_2452/2008/f700139_s.pdf
**To do-- look these up on mass bank.

https://pubmed.ncbi.nlm.nih.gov/22270643/

https://pubs.acs.org/doi/10.1021/jm301008n
https://pubs.acs.org/doi/10.1021/jm301008n

https://www.linkedin.com/dms/D5606AQGeryI_9cl_7Q/messaging-attachmentFile/0/1674513398949?m=AQL5KPz_EwQh3wAAAYXkrUq6wHaqMwgb4_G7ydlgu24zKcy_ik-93L9tHg&ne=1&v=beta&t=rOhzAL2fx-vmgZ9IzqNa6rk23IVgdBAGTrDQYQ4DOpU

https://www.linkedin.com/dms/D5606AQFnA5phyhh1Ww/messaging-attachmentFile/0/1674513446947?m=AQKAk--8d5TVggAAAYXkqQqA2dyAomZLVYOzG3h_wiVQ-KwhL3dijfbD6A&ne=1&v=beta&t=pVNO2cO_uWBbVDN99Hb1f8fRDkP851UyoTmTdAnB5tE

https://www.linkedin.com/dms/D5606AQHFP0qB8dGvrA/messaging-attachmentFile/0/1674513472574?m=AQLnPQbbdt3KKwAAAYXkqQqE-3nS5yJDHoF_O_MTtnzO49CJczmmmJSm5A&ne=1&v=beta&t=web29rjIYFypV9EACZhoXk23w3sanlzH2ULN355LwVQ



-------------------------------------------------

Transformers--
chapter 1-- attention is all you need
https://books.google.com/books?id=Cr0YEAAAQBAJ&printsec=frontcover#v=onepage&q&f=false

https://github.com/jadore801120/attention-is-all-you-need-pytorch

mass genie-- 
'Our transformer encoder, written in PyTorch, is composed of 12 transformer encoder layers plus 12 transformer decoder layers. The output dimensionality of all the sub-layers, as well as the embedding layers in both encoder and decoder, was set to 1024. Besides this, each Multi-Head attention layer of our transformer model was formed of 16 attention heads in total. We used dropout [89] heavily; its value for the complete transformer model was set to 20%. Lastly, the dimensionality of the feed-forward layer present inside all of the transformer encoder and decoder layers, and applied to every position individually, was set at 4096.'

https://metabolomics.blog/2021/07/msnovelist/

in an evaluation with 3,863 MS2 spectra from the Global Natural Product Social Molecular Networking site, MSNovelist predicted 25% of structures correctly on first rank, retrieved 45% of structures overall and reproduced 61% of correct database annotations, without having ever seen the structure in the training phase. Similarly, for the CASMI 2016 challenge, MSNovelist correctly predicted 26% and retrieved 57% of structures, recovering 64% of correct database annotations.

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8699281/


https://github.com/ashishpatel26/Treasure-of-Transformers

https://huggingface.co/blog/how-to-train

https://medium.com/@august.allen_51342/transforming-natural-product-drug-discovery-machine-learning-for-high-fidelity-chemical-property-94da4cd8ca73
MS2prop paper
https://www.biorxiv.org/content/10.1101/2022.10.09.511482v2.full

https://www.nature.com/articles/s41592-022-01486-3


--------------------------------------------------------------------------------------------------------
pesticides

see company called Biolynceus

https://www.uky.edu/Ag/Entomology/PSEP/6environment.html

soil adsorbability index
https://www.linkedin.com/dms/D5606AQEgcWcLR_yhFg/messaging-attachmentFile/0/1674504979609?m=AQK5bavmYsSpvwAAAYXkrUq66YbktsJuyGBvBvoll0ApvRsXKvn7hpi73A&ne=1&v=beta&t=CjfffuOksOUyLZcVi4I_AwXQ4G3EerqDSSTAbbmMR7g

leach indexes
https://www.linkedin.com/dms/D5606AQEhQUv25jx_eA/messaging-attachmentFile/0/1674509768012?m=AQI0u7yWMwK2OwAAAYXkrUrC7bSEnBAHY71Z1A5kQCgM81wjpk8cDHHciw&ne=1&v=beta&t=QvkX8bDxF-egUE5_pz5i_hkGyOT4LXa0325eBtVz4UE
https://www.linkedin.com/dms/D5606AQFkxSg1WZatqA/messaging-attachmentFile/0/1674509799625?m=AQL9miSKBIcreAAAAYXkrUq94h9EBtXcge5Vh8eyy4m4ReJsBNZkPu0k0g&ne=1&v=beta&t=iJZ7VNQX8VGbvd2IifErn1Y71oL3nR3MUd2Ntr_4foM

soil sorption index coefficient
https://www.linkedin.com/dms/D5606AQFIQK8Zma1nQg/messaging-attachmentFile/0/1674513719308?m=AQIuJhEupjf3fgAAAYXkqQqGMyUDx8SU8r54Dwa4xX7vPkZSBNbEjemC7g&ne=1&v=beta&t=oVnDAxFRH8iCRUX0e9JRsDVZncKyVLzSuEDn2SCwt5c


----------------------------------------------------------------------------------------------------------
binding affinity
https://www.linkedin.com/dms/D5606AQHUpCK33-KUOg/messaging-attachmentFile/0/1674515181359?m=AQIMPcGes0W9sQAAAYXkqQqBhPDT8InzBgGRM70cRxoPdc2RqQkculIFQg&ne=1&v=beta&t=6AegRZrUODouanZ4JIFxm4OrALCbdHZHukjqM8az_qw
https://www.linkedin.com/dms/D5606AQFmoEPphHlyvQ/messaging-attachmentFile/0/1674515187920?m=AQKF8Xh3-Y72SAAAAYXkqQp-OiETjLkYF9l85xTcB-jJ9Mb2aw0XeTUZpw&ne=1&v=beta&t=zJzQ9AmFOQId7JZy4iJeTYYQBbTaiD4pF9sGwcr4Rtg


--------------------------------------------------------------------------------------------------------

ADME--

https://admetmesh.scbdd.com/service/evaluation/index
https://www.google.com/books/edition/Lipid_Nanoparticles_Production_Character/bOVhBAAAQBAJ?hl=en&gbpv=1&dq=lipid+nanoparticles+production+characterization+stability&printsec=frontcover
https://academic.oup.com/nar/article/49/W1/W5/6249611
https://academic.oup.com/nar/article/45/W1/W356/3791213
https://aip.scitation.org/doi/pdf/10.1063/1.4937259

https://chemistry-europe.onlinelibrary.wiley.com/doi/full/10.1002/cmdc.201600182
https://pubs.acs.org/doi/abs/10.1021/ci500467k
https://pubmed.ncbi.nlm.nih.gov/19827778/
https://pubmed.ncbi.nlm.nih.gov/15857122/
https://www.nature.com/articles/srep42717

The Egan rule considers good bioavailability for compounds with 0 ≥ tPSA ≤ 132 Å2 and -1≥ logP ≤ 6 [15]. The Bayer Oral Physchem Score is computed using a Bayer in house system to flag chemical compounds and it takes values between 0 and 10.

cns vs non-cns

https://www.linkedin.com/dms/D5606AQHxRiRfXgfXIg/messaging-attachmentFile/0/1674515816273?m=AQKLDYOhLmHeGgAAAYXkqQp-2A0Ne_VAmVmP4CXrliVNj4k6oZVtU2DJGg&ne=1&v=beta&t=v2iPj_uDSoxHaD_yL6Tue_e6uFSaAe7y4PQ9k4McWDc

--------------------------------------
Compounds of interest---
1. Ulvan -- 
https://www.jpost.com/health-and-wellness/could-seaweed-save-humanity-from-covid-19-687775
https://onlinelibrary.wiley.com/doi/epdf/10.1002/adma.202206367
Ulvan is a plastic similar to PEI.  It's useful for covid 19 and for agriculture viruses.
https://www.newscientist.com/article/2341170-battery-made-using-seaweed-still-works-after-charging-1000-times/?utm_medium=social&utm_campaign=echobox&utm_source=Facebook#Echobox=1665398953
https://www.sciencedirect.com/science/article/pii/S2211926418308373


2. Alginate nanoparticles coated with antibodies for tumors-- partner with freenome?
sodium alginate synthesis-- https://www.artmolds.com/sodium-alginate
https://doctorsnutrition.com/store/sodium-alginate-60-vegetable-capsules/
https://gut.bmj.com/content/66/Suppl_2/A140.2
sodium alginate acts as a chelator. diseases such as IBS and ME/chronic fatigue could maybe benefit from sodium alginate chelators.

https://www.science.org/doi/10.1126/science.abq6990?utm_campaign=SciMag&utm_medium=ownedSocial&utm_source=LinkedIn&cookieSet=1
https://www.freenome.com/
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6432598/

3.Gratzel cells
https://www.researchgate.net/publication/256549423_Brown_seaweed_pigment_as_a_dye_source_for_photoelectrochemical_solar_cells

4. omega 3

5. sunscreen

6. nanoparticles-- https://www.mdpi.com/2306-5354/7/4/129
https://www.sciencedirect.com/science/article/abs/pii/S1773224721004408
 https://royalsocietypublishing.org/doi/10.1098/rsos.171113
 https://journals.sagepub.com/doi/abs/10.1177/0958305X19882398?journalCode=eaea
 https://www.nature.com/articles/s44222-023-00038-4.epdf?sharing_token=Os_VKJmEtY4i1p8lTCVGxtRgN0jAjWel9jnR3ZoTv0ML8brRzKS0DXx7RKmwaKJMcxfuzGOGp7UGMu1fmE2HfRO86NCi2esT3SbH_XJsWa_L8wHDTe8U0mLNm6TdVz_o-R3-uMP4zLmBl6yzMoGqOkA6Ox7hSfg_bk34wEMH3uY%3D
 https://www.the-scientist.com/modus-operandi/drugs-hitch-a-ride-on-algae-for-targeted-delivery-70893
 
 https://www.azocleantech.com/article.aspx?ArticleID=647
 
 https://www.labroots.com/trending/technology/24701/ferroelectric-semiconductor-five-nanometers-thick-expand-artificial-intelligence-sensing-capabilitie-2?fbclid=IwAR1azawE10Dt9OQYYoUiaFNaPqeWjZADNpTssJV2B_OXCVXt8waMCHLQGbY
 
 https://www.pacelabs.com/life-sciences/gmp-clinical-trial-materials/solubility-bioavailability-enhancement/?utm_term=nanoparticles&utm_campaign=PLS+-+GMP&utm_source=adwords&utm_medium=ppc&hsa_acc=2195671737&hsa_cam=1614483490&hsa_grp=125240067312&hsa_ad=533130695500&hsa_src=g&hsa_tgt=kwd-338778542538&hsa_kw=nanoparticles&hsa_mt=p&hsa_net=adwords&hsa_ver=3&gclid=EAIaIQobChMI0OvZl5-t_QIV9G1vBB3-sQJUEAAYAiAAEgIsqPD_BwE
 

------------------------------------------------------------
papers of interest to pathology
https://www.newscientist.com/article/2355262-vagus-nerve-receptors-may-be-key-to-controlling-inflammation/

target prediction with pharmacophores
https://academic.oup.com/nar/article/45/W1/W356/3791213

 http://crdd.osdd.net/servers/avcpred/
 
 http://chembl.blogspot.com/2020/05/malaria-inhibitor-prediction-platform.html
 
 https://uantwerpen.vib.be/group/VincentTimmerman
 
 https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3120161/
 
 https://www.harringtondiscovery.org/
 
 https://molecular-cancer.biomedcentral.com/articles/10.1186/s12943-020-01291-6
 
 https://rupress.org/jcb/article/220/8/e202103090/212429/The-long-journey-to-bring-a-Myc-inhibitor-to-the
 
 https://time.com/6246864/reverse-aging-scientists-discover-milestone/
 
 https://www.nationalgeographic.com/magazine/science/article/zombie-cells-could-hold-the-secret-to-alzheimers-cure
 
 https://ashpublications.org/blood/article/128/22/4858/99356/Average-Monthly-Cost-of-Iron-Chelator-Treatment-in
 chelators-- sickle cell anemia, irritable bowel syndrome, ulcerative cholitis, bind heavy metals in places like great salt lake, polyphenols
 

--------------------------------------------------------------
potential partnerships--

https://www.calicolabs.com/

https://insilico.com/

https://www.envedabio.com/

https://www.energy.gov/osdbu/small-business-toolbox

https://www.trialspark.com/
----------------------------------------

TODO--- 
***** written reports with data that summarize methods and outcomes

models for binding

models for inhibition

models for solubility

lipinski rule of 5

GUI toolkit

full stack database

spinoff company with LANL? 

photographs of definitions from Molecular Descriptors for Chemoinformatics

calculate ROC curves for each of the models, plus F1

publish? https://arxiv.org/

----------------------------------------------

Funding--

https://www.energy.gov/osdbu/small-business-toolbox?fbclid=IwAR1Z992CVzQaUFgU7Hsem2B81RsVv-i_fLTBlWlWQRH5RIL86jkippMeppY

https://oig.hhs.gov/oei/reports/oei-09-00-00380.pdf

---------------------------------------------------------------

Algae

https://www.frontiersin.org/articles/10.3389/fpls.2020.00279/full
https://www.newscientist.com/article/2314395-robot-made-of-magnetic-slime-could-grab-objects-inside-your-body/

-------------------------------------------------------------------

machine learning--
https://mml-book.github.io/book/mml-book.pdf
https://www.google.com/books/edition/Hands_On_Machine_Learning_with_Scikit_Le/HnetDwAAQBAJ?hl=en&gbpv=1&dq=hands+on+machine+learning&printsec=frontcover
chemoinformatics-- 

https://www.google.com/books/edition/Molecular_Descriptors_for_Chemoinformati/6Zp7Yrqzv8AC?hl=en&gbpv=1&dq=molecular+descriptors+for+chemoinformatics&printsec=frontcover

---------------------------------------

Methods

Lasso regression-- least absolute shrinkage and selection operation regression is a regularized version of linear regression.  It adds a regularization term to the cost function using the l1 norm of the weight vector.   An important characteristic of lasso regression is that it tends to completely eliminate the weights of the least important features (set them to 0).  Kasso regression automatically performs feature selection and outputs a sparse model.  

elastic- elastic net is a middle ground between ridge regression and lasso regression.  the regularization term is a simple mix of both ridge and lasso's regularization terms, and you can control the mix ratio r. when r=0, elastic net is equivalent o ridge regression, and when r=1, it is equivalent to lasso regression.  ridge regression is a good default to use, but if you suspect that only a few features are actually useful, you should prefer lasso or elastic since they tend to reduce the useless features' weights down to zero.  In general elastic is preferred over lasso since lasso may behave erratically when the number of features is greater than the number of training instances or when several features are strongly correlated.

How good is a regression?

statisticians have come up with a tool that’s easy to understand. It is called r^2. Typically, R square is looked at as a percentage value, and it can range from 0% to 100%. The higher it is,the greater the explanatory power of the regression model (the lower the weight of unexplained squares, the better the model).

https://medium.com/wwblog/evaluating-regression-models-using-rmse-and-r%C2%B2-42f77400efee

------------------------------------------

preclinical testing---https://www.criver.com/products-services/safety-assessment/toxicology-services?creative=595929445573&keyword=genetic%2520toxicity%2520testing&matchtype=p&network=g&device=m&gclid=EAIaIQobChMInMSEz8i9_QIVGTStBh3NggBJEAAYASAAEgIG4_D_BwE&region=3601

https://www.mpllaboratories.com/Services.aspx?action=list&TopServiceCategoryID=22&ServiceCategoryID=22&device=m&network=g&keyword=dietary%20supplement%20testing%20labs&matchtype=e&creative=607538834832&gclid=EAIaIQobChMIkrGptoe7_QIVbm5vBB03Rgq4EAAYASAAEgKMPPD_BwE

https://esha.com/genesis-rd-product-development-supplement-labeling-compliance/?creative=599882152229&matchtype=b&network=g&device=m&adposition=&keyword=dietary%20supplement%20formulation&utm_source=google&utm_medium=cpc&utm_campaign=genesis-supplements&gclid=EAIaIQobChMImtaO2Ia7_QIVaWxvBB1teADuEAAYBCAAEgI1wvD_BwE

https://phys.org/news/2022-03-medicines-3d-printed-seconds.html

https://www.aprecia.com/technology


https://www.nutracapusa.com/start-here/?utm_source=Google_Ads&gclid=Cj0KCQiAgOefBhDgARIsAMhqXA4oL8AzlYynVHqsfVHC3-_thaw1v7qAw9XA9idtfLwnCneOS7d2ZW8aAoA4EALw_wcB

   https://www.ipharmachine.com/?fbclid=IwAR3KmrU_GedXjEneinM65kHJGM6M6fgSqkyy0MyemvesmdIjZQJwlfWZmNo
   
   https://drive.google.com/file/d/1wPtcYAhPhc3xZDEM9DDyIrmx4nxWadJ6/view
   
   The PTO won't grant a patent on any new drug unless the applicant can show that not only is it useful in treating some condition, but also that it's relatively safe for its intended purpose.' put another way, the pto considers an unsafe drug useless.  Most drug patent applications won't be allowed unless the FDA has approved tests of the drug for efficacy and safety, but drugs that are generally recognized as safe, or are in a 'safe' chemical category with known safe drugs, don't need prior fda approval to be patentable.  for example, one inventor was able to patent the use of chili peppers to treat baldness since chilies were known to be safe.'
 


----------------------------
books
  https://books.google.com/books/about/Why_Digital_Transformations_Fail.html?id=L_T1uwEACAAJ
  
  https://www.linkedin.com/feed/update/urn:li:activity:7006165405937373184/?utm_source=share&utm_medium=member_desktop
  
  https://books.google.com/books/about/Why_Digital_Transformations_Fail.html?id=L_T1uwEACAAJ
  
  
  https://www.amazon.com/Deep-Learning-Life-Sciences-Microscopy/dp/1492039837
  
  Patent it Yourself NOLO
  ------------------------------------------
  tasty treats
  
  https://www.submariner-network.eu/recipe-for-a-veggie-burger-with-algae
  
   
   
  
