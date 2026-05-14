# Fortune 250 — ATS vendor buckets

Which Applicant Tracking System hosts each company's job postings. This sizes
the discovery/integration work and confirms the Workday-first wedge.

**Method:** 5 parallel research agents, careers-page URL inspection. Source list
is `fortune-250.md` (Fortune 500 2025 ranking, top 250).

**Confidence caveat:** agents could not fetch raw page source (WebFetch was
blocked), so determinations come from careers-page URLs and search snippets.
High = clear vendor URL signature (e.g. `myworkdayjobs.com`). Medium = strong
inference. Low = best guess, needs a manual verification pass.

## Summary

| ATS Vendor | Count | % of 250 |
|---|---|---|
| **Workday** | **127** | **51%** |
| Custom / Unknown | 23 | 9% |
| Oracle Cloud Recruiting (Fusion) | 22 | 9% |
| SAP SuccessFactors | 21 | 8% |
| Phenom People | 12 | 5% |
| iCIMS | 13 | 5% |
| Oracle Taleo (legacy) | 11 | 4% |
| Eightfold | 8 | 3% |
| SmartRecruiters | 6 | 2% |
| IBM Kenexa BrassRing | 3 | 1% |
| Avature | 2 | 1% |
| Greenhouse | 2 | 1% |
| **Total** | **250** | |

**Headline:** Workday is 51% of the Fortune 250 — more than the next five
vendors combined. The v1 Workday wedge covers over half the target list with
one integration, and reuses the workday-autofill-agent extension as the
submission layer.

**Two numbers that move the real total:**
- *Oracle, combined:* Taleo (11) + Fusion Cloud Recruiting (22) = 33. They are
  genuinely different products needing different integrations — kept separate
  here — but if a future Oracle integration handles both, that's the #2 bucket.
- *Effective Workday is likely higher than 127.* Phenom People (12) and Avature
  (2) are front-end / candidate-experience layers that frequently sit on top of
  another ATS — often Workday — at the actual apply step. Several Phenom rows
  (UnitedHealth, State Farm, Freddie Mac, Lincoln National, Tenet) were flagged
  as probable Workday-underneath. A verification pass could push Workday past 135.

---

## Workday — 127

The v1 target bucket. Medium-confidence rows verified 2026-05-14 (see JOURNAL).

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 2 | Walmart | walmart.wd5.myworkdayjobs.com/WalmartExternal | High |
| 6 | CVS Health | cvshealth.wd1.myworkdayjobs.com/en-US/CVS_Health_Careers | High |
| 7 | McKesson | mckesson.wd3.myworkdayjobs.com/External_Careers | High |
| 10 | Cencora | myhrabc.wd5.myworkdayjobs.com/Global | High |
| 13 | Cigna | cigna.wd5.myworkdayjobs.com/cignacareers | High |
| 14 | Cardinal Health | cardinalhealth.wd1.myworkdayjobs.com/EXT | High |
| 15 | Elevance Health | elevancehealth.wd1.myworkdayjobs.com/ANT | High |
| 18 | Chevron | chevron.wd5.myworkdayjobs.com/jobs | High |
| 19 | General Motors | generalmotors.wd5.myworkdayjobs.com/Careers_GM | High |
| 20 | Nvidia | nvidia.wd5.myworkdayjobs.com/NVIDIAExternalCareerSite | High |
| 21 | Centene | centene.wd5.myworkdayjobs.com/Centene_External | High |
| 23 | Home Depot | homedepot.wd5.myworkdayjobs.com/CareerDepot | High |
| 25 | Fannie Mae | fanniemae.wd1.myworkdayjobs.com/FannieMaeCareers | High |
| 27 | Verizon | verizon.wd12.myworkdayjobs.com/verizon-careers | High |
| 28 | Marathon Petroleum | mpc.wd1.myworkdayjobs.com/MPCCareers | High |
| 29 | Phillips 66 | careers.phillips66.com — suspected SAP SuccessFactors (`/go/` paths), UNVERIFIED | Low |
| 31 | Humana | humana.wd5.myworkdayjobs.com/Humana_External_Career_Site | High |
| 32 | AT&T | att.wd1.myworkdayjobs.com/ATTGeneral | High |
| 33 | Comcast | comcast.wd5.myworkdayjobs.com/Comcast_Careers | High |
| 37 | Target | target.wd5.myworkdayjobs.com/targetcareers | High |
| 38 | Dell Technologies | dell.wd1.myworkdayjobs.com/External | High |
| 39 | Bank of America | ghr.wd1.myworkdayjobs.com/Lateral-US | High |
| 41 | Walt Disney | disney.wd5.myworkdayjobs.com/disneycareer | High |
| 43 | Johnson & Johnson | jj.wd5.myworkdayjobs.com/JJ | High |
| 44 | UPS | hcmportal.wd5.myworkdayjobs.com/Search | High |
| 45 | FedEx | fedex.wd1.myworkdayjobs.com/FXE-LAC_External_Career_Site | High |
| 46 | RTX (Raytheon) | globalhr.wd5.myworkdayjobs.com/REC_RTX_Ext_Gateway | High |
| 48 | Procter & Gamble | pg.wd5.myworkdayjobs.com/1000 | High |
| 49 | Lowe's | lowes.wd5.myworkdayjobs.com/LWS_External_CS | High |
| 51 | Sysco | sysco.wd5.myworkdayjobs.com/syscocareers | High |
| 53 | Boeing | boeing.wd1.myworkdayjobs.com/EXTERNAL_CAREERS | High |
| 55 | Wells Fargo | wd1.myworkdaysite.com/recruiting/wf/WellsFargoJobs | High |
| 56 | Citi | citi.wd5.myworkdayjobs.com/2 | High |
| 61 | Allstate | allstate.wd5.myworkdayjobs.com/allstate_careers | High |
| 64 | Caterpillar | cat.wd5.myworkdayjobs.com/CaterpillarCareers | High |
| 67 | Pfizer | pfizer.wd1.myworkdayjobs.com/PfizerCareers | High |
| 70 | ConocoPhillips | conocophillips.wd1.myworkdayjobs.com/External | High |
| 72 | TD Synnex | synnex.wd5.myworkdayjobs.com/tdsynnexcareers | High |
| 74 | Broadcom | broadcom.wd1.myworkdayjobs.com/External_Career | High |
| 76 | Eli Lilly | lilly.wd5.myworkdayjobs.com/LLY | High |
| 77 | TJX Companies | tjx.wd1.myworkdayjobs.com/TJX_EXTERNAL | High |
| 78 | Nationwide | nationwide.wd1.myworkdayjobs.com/Nationwide_Career | High |
| 80 | Cisco Systems | cisco.wd5.myworkdayjobs.com/Cisco_Careers | High |
| 81 | Prudential Financial | pru.wd5.myworkdayjobs.com/Careers | High |
| 83 | HP | hp.wd5.myworkdayjobs.com/ExternalCareerSite | High |
| 85 | Tyson Foods | tysonfoods.wd5.myworkdayjobs.com/TSN | High |
| 87 | Intel | intel.wd1.myworkdayjobs.com/External | High |
| 90 | Ingram Micro | ingrammicro.wd5.myworkdayjobs.com/IngramMicro | High |
| 93 | USAA | usaa.wd1.myworkdayjobs.com/USAAJOBSWD | High |
| 94 | Travelers | travelers.wd5.myworkdayjobs.com/External | High |
| 95 | Bristol-Myers Squibb | bristolmyerssquibb.wd5.myworkdayjobs.com/BMS | High |
| 96 | Coca-Cola | coke.wd1.myworkdayjobs.com/coca-cola-careers | High |
| 97 | TIAA | tiaa.wd1.myworkdayjobs.com/Search | High |
| 99 | Nike | nike.wd1.myworkdayjobs.com/nke | High |
| 101 | Qualcomm | qualcomm.wd12.myworkdayjobs.com/en-US/External | High |
| 102 | General Electric (Aerospace) | geaerospace.wd5.myworkdayjobs.com/GE_ExternalSite | High |
| 103 | Abbott Laboratories | abbott.wd5.myworkdayjobs.com/en-US/abbottcareers | High |
| 106 | MassMutual | massmutual.wd1.myworkdayjobs.com/MMAscendCareers | High |
| 110 | Northwestern Mutual | northwesternmutual.wd5.myworkdayjobs.com/CORPORATE-CAREERS | High |
| 111 | Northrop Grumman | ngc.wd1.myworkdayjobs.com/Northrop_Grumman_External_Site | High |
| 112 | Dow | dow.wd1.myworkdayjobs.com/ExternalCareers | High |
| 114 | Salesforce | salesforce.wd12.myworkdayjobs.com/External_Career_Site | High |
| 119 | US Foods | usfoods.wd1.myworkdayjobs.com/usfoodscareersExternal | High |
| 120 | Warner Bros. Discovery | warnerbros.wd5.myworkdayjobs.com/global | High |
| 121 | GE Vernova | gevernova.wd5.myworkdayjobs.com/Vernova_ExternalSite | High |
| 122 | World Kinect | wfscorp.wd5.myworkdayjobs.com/wfscareers | High |
| 123 | Mondelez International | mdlz.wd3.myworkdayjobs.com/External | High |
| 124 | Lithia Motors | lithia.wd5.myworkdayjobs.com/LithiaCareers | High |
| 125 | Micron Technology | micron.wd1.myworkdayjobs.com/External | High |
| 127 | Amgen | amgen.wd1.myworkdayjobs.com/Careers | High |
| 128 | Lennar | lennar.wd1.myworkdayjobs.com/Lennar_Jobs | High |
| 129 | Hewlett Packard Enterprise | hpe.wd5.myworkdayjobs.com/Jobsathpe | High |
| 134 | PayPal | paypal.wd1.myworkdayjobs.com/jobs | High |
| 138 | Oneok | oneok.wd1.myworkdayjobs.com/ONEOK | High |
| 139 | Mastercard | mastercard.wd1.myworkdayjobs.com/CorporateCareers | High |
| 140 | Duke Energy | dukeenergy.wd1.myworkdayjobs.com/Search | High |
| 141 | Ferguson Enterprises | ferguson.wd1.myworkdayjobs.com/Ferguson_Experienced | High |
| 143 | Jabil | jabil.wd5.myworkdayjobs.com/Jabil_Careers | High |
| 145 | PBF Energy | pbfenergy.wd1.myworkdayjobs.com/PBF | High |
| 147 | Arrow Electronics | arrow.wd1.myworkdayjobs.com/AC | High |
| 148 | Gilead Sciences | gilead.wd1.myworkdayjobs.com/gileadcareers | High |
| 150 | Capital One | capitalone.wd12.myworkdayjobs.com/Capital_One | High |
| 152 | Applied Materials | amat.wd1.myworkdayjobs.com/External | High |
| 153 | CarMax | carmax.wd1.myworkdayjobs.com/External | High |
| 154 | AutoNation | autonation.wd5.myworkdayjobs.com/Careers | High |
| 155 | The Hartford | thehartford.wd5.myworkdayjobs.com/Careers_External | High |
| 156 | Baker Hughes | bakerhughes.wd5.myworkdayjobs.com/BakerHughes | High |
| 157 | Southwest Airlines | swa.wd1.myworkdayjobs.com/external | High |
| 158 | Apollo Global Management | athene.wd5.myworkdayjobs.com/Apollo_Careers | High |
| 160 | American International Group (AIG) | aig.wd1.myworkdayjobs.com/aig | High |
| 162 | Occidental Petroleum | oxy.wd5.myworkdayjobs.com/Corporate | High |
| 163 | Marsh & McLennan | mmc.wd1.myworkdayjobs.com/careers | High |
| 167 | U.S. Bancorp | usbank.wd1.myworkdayjobs.com/US_Bank_Careers | High |
| 169 | Jones Lang LaSalle (JLL) | jll.wd1.myworkdayjobs.com/jllcareers | High |
| 170 | Kraft Heinz | heinz.wd1.myworkdayjobs.com/KraftHeinz_Careers | High |
| 173 | 3M | 3m.wd1.myworkdayjobs.com/Search | High |
| 176 | Live Nation Entertainment | livenation.wd1.myworkdayjobs.com/LNExternalSite | High |
| 178 | Stryker | stryker.wd1.myworkdayjobs.com/StrykerCareers | High |
| 181 | Danaher | danaher.wd1.myworkdayjobs.com/DanaherJobs | High |
| 182 | Genuine Parts Company | genpt.wd1.myworkdayjobs.com/Careers | High |
| 184 | Adobe | adobe.wd5.myworkdayjobs.com/external_experienced | High |
| 189 | BlackRock | blackrock.wd1.myworkdayjobs.com/BlackRock_Professional | High |
| 193 | Avnet | avnet.wd1.myworkdayjobs.com/External | High |
| 194 | Reinsurance Group of America | rgare.wd1.myworkdayjobs.com/Careers | High |
| 195 | KKR | kkr.wd5.myworkdayjobs.com/External_Career | High |
| 197 | CDW | cdw.wd5.myworkdayjobs.com/Careers | High |
| 198 | Carrier Global | carrier.wd5.myworkdayjobs.com/jobs | High |
| 200 | Becton Dickinson | bdx.wd1.myworkdayjobs.com/EXTERNAL_CAREER_SITE_USA | High |
| 201 | PNC Financial Services | pnc.wd5.myworkdayjobs.com/External | High |
| 204 | American Family Insurance | amfam.wd1.myworkdayjobs.com/Careers | High |
| 205 | American Electric Power | aep.wd1.myworkdayjobs.com/AEPCareerSite | High |
| 206 | BJ's Wholesale Club | bjswholesaleclub.wd1.myworkdayjobs.com/BJsCareers | High |
| 207 | Fiserv | fiserv.wd5.myworkdayjobs.com/EXT | High |
| 213 | GE HealthCare Technologies | gehc.wd5.myworkdayjobs.com/GEHC_ExternalSite | High |
| 218 | Kimberly-Clark | kimberlyclark.wd1.myworkdayjobs.com/GLOBAL | High |
| 224 | Dollar Tree | dollartree.wd5.myworkdayjobs.com/dollartreeus | High |
| 226 | Cleveland-Cliffs | aksteel.wd1.myworkdayjobs.com/careers | High |
| 227 | Ameriprise Financial | ameriprise.wd5.myworkdayjobs.com/Ameriprise | High |
| 230 | Corebridge Financial | corebridgefinancial.wd1.myworkdayjobs.com/CorebridgeFinancial | High |
| 231 | Goodyear Tire & Rubber | goodyear.wd1.myworkdayjobs.com/GoodyearCareers | High |
| 232 | Truist Financial | truist.wd1.myworkdayjobs.com/Careers | High |
| 233 | Loews | loewscorp.wd1.myworkdayjobs.com/loewscorp | High |
| 243 | PulteGroup | pultegroup.wd1.myworkdayjobs.com/PGI | High |
| 244 | Discover Financial Services | discover.wd5.myworkdayjobs.com/Discover | High |
| 246 | O'Reilly Automotive | oreillyauto.wd1.myworkdayjobs.com/oreilly | High |
| 248 | Leidos | leidos.wd5.myworkdayjobs.com/External | High |
| 249 | MGM Resorts International | mgmresorts.wd5.myworkdayjobs.com/MGMCareers | High |

## Oracle Cloud Recruiting (Fusion) — 22

Distinct product from Taleo. The `*.oraclecloud.com/hcmUI/CandidateExperience`
URL pattern.

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 16 | Ford Motor | efds.fa.em5.oraclecloud.com/.../CX_1/jobs | High |
| 22 | JPMorgan Chase | jpmc.fa.oraclecloud.com/.../CX_1001/requisitions | High |
| 26 | Kroger | krogerfamilycareers.com/en/sites/CX_2001/requisitions | High |
| 52 | Albertsons | eofd.fa.us6.oraclecloud.com/.../CX_1001/jobs | High |
| 71 | Oracle | eeho.fa.us2.oraclecloud.com/.../jobsearch/jobs | High |
| 82 | Goldman Sachs | hdpc.fa.us2.oraclecloud.com/.../LateralHiring | High |
| 107 | Molina Healthcare | apply.molinahealthcare.com/.../CX_1 | High |
| 113 | Honeywell | ibqbjb.fa.ocs.oraclecloud.com/.../Honeywell/jobs | High |
| 132 | Cummins | fa-espx-saasfaprod1.fa.ocs.oraclecloud.com/.../CX_1/jobs | High |
| 133 | GuideWell Mutual Holding | fa-etum-saasfaprod1.fa.ocs.oraclecloud.com/.../floridablue | High |
| 149 | Southern Company | emje.fa.us6.oraclecloud.com/.../SouthernCompanyJobs/jobs | High |
| 171 | Marriott International | careers.marriott.com | High |
| 174 | Waste Management | emcm.fa.us2.oraclecloud.com/.../WMCareers | High |
| 185 | Sherwin-Williams | ejhp.fa.us6.oraclecloud.com/.../CX_2/jobs | High |
| 187 | WESCO International | eklm.fa.us2.oraclecloud.com/.../CX/requisitions | High |
| 190 | Macy's | ebwh.fa.us2.oraclecloud.com/.../CX_1001/jobs | High |
| 212 | Tenet Healthcare | eodr.fa.us2.oraclecloud.com/.../CX_1001 | Medium |
| 217 | Bank of New York Mellon | eofe.fa.us2.oraclecloud.com/.../CX_1001/jobs | High |
| 222 | AutoZone | egud.fa.us2.oraclecloud.com/.../CX_1/jobs | High |
| 225 | Cheniere Energy | hcgi.fa.us2.oraclecloud.com/.../CX_2 | High |
| 237 | Emerson Electric | hdjq.fa.us2.oraclecloud.com/.../CX_1 | High |
| 250 | Texas Instruments | edbz.fa.us2.oraclecloud.com/.../CX/jobs | High |

## SAP SuccessFactors — 21

The `successfactors.com/careers` or Career Site Builder (`/go/`, `/job/`) URL
patterns.

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 9 | Exxon Mobil | career4.successfactors.com/careers?company=exxonmobilP | High |
| 68 | New York Life Insurance | jobs.newyorklife.com | Medium |
| 86 | American Airlines | jobs.aa.com | Medium |
| 136 | Nucor | jobs.nucor.com | Medium |
| 144 | NRG Energy | careers.nrgenergy.com | High |
| 146 | Paccar | jobs.paccar.com | High |
| 151 | Paramount Global | careers.paramount.com | High |
| 161 | HF Sinclair | careers.hfsinclair.com | High |
| 164 | NextEra Energy | jobs.nexteraenergy.com | High |
| 175 | PG&E | jobs.pge.com | High |
| 177 | Union Pacific | up.jobs | High |
| 179 | International Paper | jobs.internationalpaper.com | High |
| 186 | Lear | jobs.lear.com | High |
| 196 | Halliburton | careers.halliburton.com | High |
| 203 | Newmont | newmont.jobs2web.com | Medium |
| 214 | Altria | careers.altria.com/jobs | Medium |
| 215 | Colgate-Palmolive | jobs.colgate.com | Medium |
| 228 | Aramark | career4.successfactors.com/careers?company=ARAMARKPROD | High |
| 229 | Lincoln National (Lincoln Financial) | jobs.lincolnfinancial.com | High |
| 239 | W.W. Grainger | career8.successfactors.com/careers?company=Grainger | High |
| 240 | Aflac | careers.aflac.com | Medium |

## Phenom People — 12

Front-end / candidate-experience layer; often sits on top of another ATS at the
apply step. Verify the apply-step backend before treating as a single bucket.

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 3 | UnitedHealth | careers.unitedhealthgroup.com/search-jobs | Medium |
| 34 | State Farm | jobs.statefarm.com/main/jobs | High |
| 35 | Freddie Mac | careers.freddiemac.com/us/en/search-results | High |
| 42 | PepsiCo | pepsicojobs.com/main | Medium |
| 47 | Progressive | careers.progressive.com/search/jobs | Medium |
| 65 | Merck | jobs.merck.com/us/en/search-results | Medium |
| 79 | United Airlines | careers.united.com/us/en | High |
| 104 | Thermo Fisher Scientific | jobs.thermofisher.com/global/en | High |
| 118 | CHS Inc. | jobs.chsinc.com/search-jobs | Low |
| 137 | United Natural Foods | jobs.unfi.com/jobs | Low |
| 211 | Cognizant Technology Solutions | careers.cognizant.com/global-en/jobs | Medium |
| 235 | Global Partners | careers.globalp.com/us/en/home | Medium |

## iCIMS — 13

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 30 | StoneX | careers-stonex.icims.com/jobs/intro | Medium |
| 84 | Charter Communications | careers-charter.icims.com | High |
| 89 | General Dynamics | careers-gdeb.icims.com | Medium |
| 108 | Dollar General | jobs-dollargeneral.icims.com | High |
| 135 | Advanced Micro Devices (AMD) | careers-amd.icims.com/jobs | High |
| 159 | Quanta Services | careers-quanta.icims.com | High |
| 172 | Constellation Energy | careers-constellationenergy.icims.com | High |
| 180 | Exelon | careers-exeloncorp.icims.com | High |
| 188 | Charles Schwab | career-schwab.icims.com/jobs/intro | High |
| 192 | Group 1 Automotive | careers-group1auto.icims.com | High |
| 220 | Intuit | globalcareers-intuit.icims.com | High |
| 223 | General Mills | ussalaried-generalmills.icims.com/jobs/intro | High |
| 242 | Steel Dynamics | careers-steeldynamics.icims.com | High |

## Oracle Taleo (legacy) — 11

Distinct product from Oracle Cloud Recruiting. The `*.taleo.net/careersection`
URL pattern.

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 36 | Valero Energy | valero.taleo.net/careersection/2/jobsearch.ftl | High |
| 54 | Energy Transfer | energytransfer.referrals.selectminds.com | High |
| 57 | HCA Healthcare | hca.taleo.net/careersection/0hca/jobsearch.ftl | High |
| 63 | American Express | axp.taleo.net/careersection/rp/jobsearch.ftl | High |
| 88 | Enterprise Products Partners | epco.taleo.net/careersection/alljobs/jobsearch.ftl | High |
| 126 | Starbucks | starbucks.taleo.net/careersection/1000222/jobsearch.ftl | High |
| 130 | D.R. Horton | drhorton.taleo.net/careersection/2/jobsearch.ftl | High |
| 199 | Ross Stores | rossstores.taleo.net/careersection/rstrcs1.1/jobview.ftl | High |
| 202 | L3Harris Technologies | l3com.taleo.net/careersection/l3_ext_us/jobsearch.ftl | High |
| 241 | ManpowerGroup | manpower.taleo.net/careersection/mgsrpo/moresearch.ftl | High |
| 247 | Targa Resources | targaresources.referrals.selectminds.com | Medium |

## Eightfold — 8

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 60 | Morgan Stanley | morganstanley.eightfold.ai/careers | High |
| 91 | Liberty Mutual Insurance | libertymutual.eightfold.ai/careers | High |
| 100 | Deere & Company | careers.deere.com/careers | Medium |
| 105 | Netflix | explore.jobs.netflix.net/careers | High |
| 168 | Freeport-McMoRan | talent.fmjobs.com/careers | Medium |
| 219 | Lam Research | opportunities.lamresearch.com | High |
| 221 | Boston Scientific | bostonscientific.eightfold.ai/careers | High |
| 245 | Corteva | corteva.eightfold.ai/careers | High |

## SmartRecruiters — 6

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 75 | AbbVie | careers.smartrecruiters.com/AbbVie | High |
| 115 | Visa | careers.smartrecruiters.com/visa | High |
| 165 | McDonald's | careers.smartrecruiters.com/mcdonaldscorporation | High |
| 166 | Booking Holdings | careers.smartrecruiters.com/Bookingcom1 | High |
| 183 | Block (Square) | careers.smartrecruiters.com/Square | High |
| 238 | Asbury Automotive Group | careers.smartrecruiters.com/AsburyAutomotiveGroup | High |

## IBM Kenexa BrassRing — 3

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 58 | Lockheed Martin | sjobs.brassring.com (partnerid=25037) | High |
| 62 | IBM | krb-sjobs.brassring.com (partnerid=26059) | High |
| 69 | Performance Food Group | sjobs.brassring.com (partnerid=26350) | High |

## Avature — 2

Like Phenom, often a CRM/front-end layer over another ATS.

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 59 | MetLife | metlifecareers.com/en_US/ml/SearchJobs | Medium |
| 66 | Delta Air Lines | delta.avature.net/en_US/careers | High |

## Greenhouse — 2

| Rank | Company | Careers URL | Confidence |
|---|---|---|---|
| 131 | Coupang | boards.greenhouse.io/coupang | High |
| 234 | Carvana | carvana.com/careers/jobs | Medium |

## Custom / Unknown — 23

In-house builds, decentralized conglomerates, or vendors outside the signature
list (Cadient, ServiceNow, ADP Recruiting, SmartSearch, TTC Portals, IBM
BrassRing where it's the only vendor present, etc.).

| Rank | Company | Careers URL | Note |
|---|---|---|---|
| 1 | Amazon | amazon.jobs/en/search | In-house |
| 4 | Apple | jobs.apple.com/en-us/search | In-house |
| 5 | Alphabet (Google) | google.com/about/careers/applications/jobs/results | In-house |
| 8 | Berkshire Hathaway | berkshirehathaway.com | Decentralized — subsidiaries vary |
| 11 | Microsoft | careers.microsoft.com | In-house |
| 12 | Costco | cta.cadienttalent.com | Cadient Talent |
| 17 | Meta | metacareers.com/jobsearch | In-house |
| 24 | Walgreens | sjobs.brassring.com (partnerid=26336) | IBM BrassRing |
| 40 | Tesla | tesla.com/careers/search | In-house |
| 50 | Archer Daniels Midland | sjobs.brassring.com (partnerid=25416) | IBM BrassRing |
| 73 | Publix Super Markets | jobs.publix.com/jobs | Custom portal, no signature |
| 92 | Uber | uber.com/us/en/careers/list | In-house (Uber Freight uses Greenhouse) |
| 98 | Plains GP Holdings | plains.com/careers/job-postings | Custom portal, no signature |
| 109 | Best Buy | jobs.bestbuy.com/bby | ServiceNow |
| 116 | Philip Morris International | pmi.avature.net/en_US/ExternalCareers | Avature |
| 117 | CBRE Group | careers.cbre.com/en_US/careers/SearchJobs | Avature |
| 142 | Penske Automotive Group | pagjobs.com/jobs | ADP Recruiting |
| 191 | EOG Resources | jobs.smartsearchonline.com/eogresources | SmartSearch |
| 208 | Super Micro Computer | jobs.supermicro.com | No signature surfaced |
| 209 | Amphenol | amphenol.com/careers | Decentralized — 100+ business units |
| 210 | Automatic Data Processing (ADP) | jobs.adp.com/en | No signature surfaced |
| 216 | Parker-Hannifin | parkercareers.ttcportals.com/jobs/search | TTC Portals |
| 236 | Edison International | edisoncareers.com/job-search-results | No signature surfaced |

---

## Next steps

1. **Verification pass — done 2026-05-14.** 9 of 10 Workday-adjacent Medium
   rows resolved. Confirmed Workday: Bank of America, Nike, World Kinect,
   Cleveland-Cliffs, Discover, ConocoPhillips (upgraded Medium→High). Loews URL
   corrected to the corporate tenant (`loewscorp`, not the hotels subsidiary).
   Misbucketed and moved out of Workday: **AMD → iCIMS**, **Lincoln National →
   SAP SuccessFactors**. Workday count 129 → 127. **Still open: Phillips 66** —
   `careers.phillips66.com/go/...` paths suggest SAP SuccessFactors, but the
   direct page fetch was declined; left in the Workday bucket flagged Low/
   UNVERIFIED pending another check.
2. **Decide whether Phenom/Avature get verified into Workday** — could push the
   v1 bucket past 135.
3. **Confirm the Workday slice as the v1 discovery target** and design the
   discovery mechanism (Workday tenant job-search API vs. per-tenant crawling).
4. The workday-autofill-agent extension is the submission layer for this bucket.
