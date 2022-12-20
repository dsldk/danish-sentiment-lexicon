# danish-sentiment-lexicon

DDS: The Danish Sentiment Lexicon


DDS (“Det Danske Sentimentleksikon” - ‘The Danish Sentiment Lexicon’) is a comprehensive sentiment lexicon for Danish based on two dictionaries, “Den Danske Begrebsordbog” (DDB, The Danish Thesaurus) and “Den Danske Ordbog” (DDO, The Danish Dictionary), and compiled by use of lexicographic methods.


The dataset was compiled by
Sanni Nimb, Sussi Olsen, Thomas Troelsgård
 version 0.2
 2022-12-20

 License: CC-BY-SA 4.0 International <https://creativecommons.org/licenses/by-sa/4.0/>


If you use this dataset or derivatives of it, please refer to the publishers: Det Danske Sprog- og Litteraturselskab (DSL, Society for Danish Language and Literature) and Center for Sprogteknologi, Københavns Universitet (CST, Centre for Language Technology, University of Copenhagen)


----------------------------------------------------------------------------------------------


The DDS dataset presents a negative or positive polarity value of 14.008 Danish headwords from DDO. The headword is the entry and the word forms (full forms, text forms) of it are presented as a list:


Format, filename 2_headword_headword_polarity:
<headword>tab<homograph number>tab<part of speech>tab<DDO headword ID>tab<polarity label headword>tab<list of word forms>




<polarity label headword> = "-5" (maximum degree negative)|"-4" (very high degree negative)|"-3" (high degree negative) |"-2" (degree negative) | "-1" (low degree negative) | "1" (low degree positive)| "2" (degree positive)|"3" (high degree positive)|"4" (very high degree positive)| "5" (maximum degree positive)


<homograph number> = NONE (no homographs) | "1" | "2" | "3" | "4" | "5"


<part of speech>=  | "adj." | "sb." | "sb. pl." | "vb." |“adv."|”udråbsord”|”sidsteled”|”egennavn”|”fork.”|”førsteled”|”konj.”|”lydord”|”pron.”|”præfiks”


<list of forms> = conjugated forms of the headword, separated by “;”, example:konflikt;konflikten;konfliktens;konflikter;konflikterne;konflikternes;konflikters;konflikts


Statistics


Part of speech: 7.904 sb.,  3.916 adj., 1.924 vb., 90 udråbsord, 77 adv., 57 sb.pl., 1 sidsteled (-narkoman), 3 egennavn (Pærekøbing, Udkantsdanmark, Waterloo), 3 fork. (dir., dr., m.v.h.), 14 førsteled, 6 lydord, 2 pron. (nada, nul)), 1 konj. (jamen))


14.007 headwords assigned either the polarity value 1,2, 3,4,5, -1,-2,-3,-4 or -5.


 3048 headwords  have the value "1"
 1690 headwords have the value "2"
 407 headwords have the value "3"
98 headwords have the value "4"
81 headwords have the value "5"
 3835 headwords have the value "-1"
 3694 headwords have the value "-2"
 961 headwords have the value "-3"
161 headwords have the value "-4"
33 headwords have the value "-5"

62 %  of the headwords have a negative polarity (-1, -2, -3, -4 or -5)
38 %  of the headwords have a positive polarity (1, 2, 3, 4 or 5)


12 % of the headwords have a very high polarity degree (either 3, 4, 5, -3, -4, -5).


Method


The DDS dataset assigns polarity value to 14.007 headwords. It was compiled in the following way:


Step 1: Extraction of lexical data from DDO and DDB: Approx. ¼ of the 888 sections in the thesaurus DDB were selected as either negative or positive sections based on the section title. E.g. the section with the title “Vrede” (‘Anger’) was estimated to contain negative words, and the section with the title “Medfølelse” (‘compassion’) was estimated to contain positive words, Also thesaurus sections which were estimated to contain either negative or positive words, or both, were included. Words in DDB are linked at sense level to the DDO dictionary, and via the links all the DDO-senses (from single headwords, not MWU’s) represented in the selected DDB sections were extracted for annotation. Furthermore the lexical data to be annotated was supplemented with not already included DDO senses labeled ‘derogatory’. The total inout data to be annotated consisted of 19,000 unique senses.


Step 2:  Annotation: The polarity values -1 (negative), 1 (positive) or 0 (neutral polarity) were assigned manually to all the extracted  DDO senses (listed in groups as they appear in the sections in the thesaurus DDB, some of them appearing in more than one sections. The senses were annotated by only one annotator (two persons half of the data each). In order to ensure interannotator agreement, the senses of 400 headwords which were represented in the sentiment lexicon AFINN (Nielsen, F. Å. (2018). Danish resources https://bit.ly/2NDHcbW (Section 4.8 Sentiment analysis)), were initially double annotated. The interannotator agreement (AFINN included) was 97 %.


Step 3: Upgrading of polarity values: The assigned values -1 and 1 were afterwards upgraded manually to -2 or -3, respectively 2 or 3 by one annotator based on the study of near-synonym groups in DDB where at least one of the words had a stronger value than 1 or -1 in AFINN. Validation: Approx. 25 % of the upgraded values were validated by the second annotator.


Step 4: Removal of irrelevant or disturbing senses: A) Headwords of which all annotated senses had the value 0, were removed from the dataset. B) Rare, historic, or technical/domain specific DDO senses with the value 0 were removed from the dataset, based on information in DDO. All other senses with the value 0 were kept on the list.


Step 5: Direct inclusion of a part of the annotated data: The result of the annotation process was a dataset consisting of 17.833 senses (of 14.444 headwords) with polarity values. The dataset did not include all DDO senses of the headwords, however the missing DDO-senses were likely to be neutral senses since they were not part of any of the polarity DDB sections, nor labelled ‘derogatory’ in DDO. Headwords of which all the senses annotated in the dataset had the same value (negative, neutral and/or positive as well a degree of negativity or positivity), were directly included in the final dataset.


Step 6: Extra annotation of diverging data: Opposite to this, headwords of which the annotated senses diverged w.r.t. polarity (negative, neutral and/or positive as well a degree of negativity or positivity) were studied and annotated a second time in order to assign a polarity value at headword level.  The assignment of polarity value at headword level was based on studies of the sense descriptions in DDO, on corpus studies of the words, but also on subjective judgements taking into consideration the neutral DDO-senses which were not part of the annotated data. In this process, A) headwords with a common neutral sense and a rare polarity sense were removed from the dataset. B) Headwords with two opposite polarity senses which were both estimated to be frequent were removed from the dataset (e.g. frelst, sej, skarp, overlegen, glat). And 3) homographs having diverging polarity values were removed from the dataset if they were both frequent words in Danish. A total of 595 headwords were in this way removed from the sense annotated dataset due to diverging polarity values of their senses or homographs. The remaining headwords were included in the final dataset.


The result was 13.859 headwords assigned either the polarity value 1,2,3,-1,-2, or -3. This constituted the first version of the lexicon which was released in June 2021.

In December 2022 the second version was released. Approx. 20 lemmas causing mistakes have been removed and approx 170 new lemmas have been added. The degree values have been extended with 4 and 5, assigned to approx. 400 lemmas based on information in DDO

There is a many-to-many relationship between headwords and text word forms.This means that a text word form may have more than one sentiment label attached to it if a certain word form is connected to more than one headword. For example, the text word form /fred/ will correspond to the noun "fred..1" (‘peace; quiteness etc.’) as well as the verb "frede..1" (‘to protect etc.’), with polarity labels "2" and "1", respectively.


The dataset includes fullforms of the headwords (corresponding to the text word forms) on the basis of the conjugational information on the headwords in DDO. It also includes rare (or non-existing) full forms such as the imperative form /a/of the verb /ae/, the superlative form /ufredeligst/ of the adjective /ufredelig/ and the form /mavesurts/ singular, genitive case, neuter  of the adjective /mavesur/
