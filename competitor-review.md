# State of the Art: Competitor Review Notes

*Adaptive Exam Portal app · CI6600 · research notes started 18 Oct 2026*

> These are **research notes**, not report text. Check each claim yourself: open the tools, take screenshots, and read the linked sources. Then write the report chapter **in your own words** with proper citations. Items marked **(check)** still need confirming.

---

## 1. Comparison table

| Tool | Type | Adapts to student ability? | How it adapts | Explains results to student? | Lecturer can use it for their own module? | Mobile | Cost |
|---|---|---|---|---|---|---|---|
| **Moodle Quiz** | LMS quiz | ❌ No | "Adaptive mode" only allows **multiple attempts at the same question**. It does not choose questions by ability | Per-question feedback | ✅ Yes | ✅ Moodle app (check) | Free / open source |
| **Google Forms (quiz)** | Form / quiz | ❌ No (rule-based only) | "Go to section based on answer" branching, set up by hand | Basic score and feedback | ✅ Yes | ✅ Web | Free |
| **Kahoot!** | Game quiz | ❌ No | Self-study "Learn" mode repeats missed questions. No ability-based selection described | Score only | ✅ Yes | ✅ App | Free + paid tiers |
| **Quizlet** | Flashcards / study | ⚠️ Partly (check) | "Learn" mode personalises *revision*, not *assessment* (check how) | Progress only | ⚠️ Study tool, not exams | ✅ App | Free + paid |
| **GRE General Test** | High-stakes exam | ⚠️ Section-level | The **second section** is chosen based on performance in the first (multistage testing) | Score report | ❌ Closed, one exam | ❌ Test centre / at-home on a computer | Paid per test |
| **Duolingo English Test** | High-stakes exam | ✅ Yes, item-level | Items get harder or easier with performance; scored with **IRT** | Scores + subscores | ❌ Closed, one exam | ❌ Computer required (check) | Paid per test |
| **Concerto** (Cambridge Psychometrics Centre) | Open-source assessment platform | ✅ Yes | IRT-based CATs, built on the **R** language | Textual and graphical feedback (configurable) | ⚠️ Possible, but needs R and psychometric skills, plus self-hosting | Web | Free (academic and commercial) |
| **TAO** | Open-source assessment platform | ✅ Via add-ons | Integrates **third-party CAT engines** through the IMS CAT standard | Depends on setup | ⚠️ Aimed at organisations with technical teams | Web | Community edition free; Premium/Enterprise paid |
| **catR / mirtCAT** (R packages) | Research libraries | ✅ Yes | Full CAT algorithms (item selection, ability estimation, stopping rules) | ❌ Not an app | ❌ Researchers / programmers only | ❌ | Free |

---

## 2. The gap this project fills

Existing tools fall into three groups:

1. **Everyday quiz tools** (Moodle, Google Forms, Kahoot, Quizlet). Easy for lecturers to use, but **not adaptive**: everyone gets a fixed set of questions or hand-made branches.
2. **Commercial adaptive exams** (GRE, Duolingo English Test). Genuinely adaptive and IRT-based, but **closed, paid and built for one exam**. A lecturer can't use them for their own module.
3. **Open-source adaptive platforms and libraries** (Concerto, TAO, catR, mirtCAT). Powerful, but they need **programming or psychometrics expertise** and self-hosting. They're also not designed mobile-first.

> **Gap (draft, rewrite in your own words):** There's no tool that gives an ordinary lecturer *item-level adaptive testing* on a *mobile-first* app with *explainable results* and *automatic question-quality analytics*, without needing statistics or programming knowledge.

**How this project responds:**
- Item-level IRT adaptive engine (like DET, unlike Moodle and Kahoot)
- Usable by non-experts (unlike Concerto, TAO and the R packages)
- Mobile-first, with a web version too
- Explainable results for students
- Teacher dashboard that flags poor questions
- Self-calibrating item parameters from response data
- Evaluated with simulation: *as accurate with fewer questions?*

---

## 3. Hands-on tasks for you (Week 6)

- [ ] Create a free Moodle quiz (e.g. on MoodleCloud or a demo site) and try "Adaptive mode". Screenshot it.
- [ ] Make a Google Forms quiz with "go to section based on answer". Screenshot it.
- [ ] Try Kahoot self-study and Quizlet Learn mode. Note what (if anything) adapts.
- [ ] Take the free DET practice test, and note how question difficulty changes.
- [ ] Look at the Concerto demo/docs and note what skills a lecturer would need.
- [ ] Search the App Store and Google Play for "adaptive test" / "adaptive quiz" apps, and add any close competitors to the table.
- [ ] Write 2–3 sentences per tool **in your own words**: strengths, weaknesses, and what your project does differently.

---

## 4. Academic reading list (for the literature part)

Check full details in the Kingston library and use the referencing style Kingston requires.

**Core IRT / CAT theory**
- Lord, F.M. (1980) *Applications of Item Response Theory to Practical Testing Problems*. Hillsdale, NJ: Lawrence Erlbaum.
- Embretson, S.E. and Reise, S.P. (2000) *Item Response Theory for Psychologists*. Mahwah, NJ: Lawrence Erlbaum.
- Wainer, H. (ed.) (2000) *Computerized Adaptive Testing: A Primer*. 2nd edn. Mahwah, NJ: Lawrence Erlbaum.
- van der Linden, W.J. and Glas, C.A.W. (eds.) (2010) *Elements of Adaptive Testing*. New York: Springer.

**Software and implementations**
- Magis, D. and Raîche, G. (2012) 'Random generation of response patterns under computerized adaptive testing with the R package catR', *Journal of Statistical Software*, 48(8).
- Magis, D. and Barrada, J.R. (2017) 'Computerized adaptive testing with R: recent updates of the package catR', *Journal of Statistical Software*, 76 (Code Snippet 1).
- Chalmers, R.P. (2016) 'Generating adaptive and non-adaptive test interfaces for multidimensional item response theory applications', *Journal of Statistical Software*, 71(5).

**Real-world adaptive test**
- Settles, B., LaFlair, G.T. and Hagiwara, M. (2020) 'Machine learning-driven language assessment', *Transactions of the Association for Computational Linguistics*, 8.

**Search terms for more papers** (Google Scholar / Kingston library)
- "computerized adaptive testing" efficiency fixed-length comparison
- "maximum Fisher information" item selection
- "item exposure control" Sympson-Hetter
- "cold start" item calibration adaptive testing
- "mobile assessment" OR "m-learning" assessment validity
- fairness / "differential item functioning"
- accessibility online assessment

---

## 5. Sources used for these notes

- Moodle Docs: Question behaviours. https://docs.moodle.org/en/Question_behaviours
- Google Forms branching (Alice Keeler). https://alicekeeler.com/2016/04/12/forms-branching/
- Kahoot support: self-study modes. https://support.kahoot.com/hc/en-us/articles/31566898896029
- ETS: Understanding GRE scores. https://www.ets.org/gre/test-takers/general-test/scores/understand-scores.html
- Duolingo English Test blog: How is the DET scored? https://blog.englishtest.duolingo.com/how-is-the-duolingo-english-test-scored/
- Settles et al. (2020), TACL. https://aclweb.org/anthology/2020.tacl-1.17.pdf
- Psychometrics Centre: Concerto. https://www.psychometrics.cam.ac.uk/newconcerto
- TAO Data Sheet. https://www.taotesting.com/wp-content/uploads/2019/04/TAO_Data_Sheet.pdf
- catR (JSS 2017). https://www.jstatsoft.org/article/view/v076c01
- mirtCAT (JSS 2016). https://jstatsoft.org/article/view/v071i05
