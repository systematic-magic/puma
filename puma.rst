===========================
PubMed Checking Tool (PuMa)
===========================

PubMed Checking Tool (PuMa) is designed to simplify and speed up checking of the articles for PubMed (AOP) process.


It should be noted that the tool is not a "push the button - check everything for me" solution. It is a set of checks and interfaces which make review process easier. Every attempt is made to identify and highlight article issues/errors, but due to the fact that every vendor codes article pages a bit differently (sometimes very differently), certain issues/errors can slip through the cracks.

Therefore, we encourage you to make quick manual checks while relying on the tool. Tool will identify 99% of "correct" cases by highlighting this or that page element in green. It will also attempt to identify issues/errors and most likely will succeed in it in 70-80% of cases. The rest 20-30% should be checked by you manually.


If you have been working with PMC corrections tool - CheeTah, you probably will find lots of checks to be similar. However, note that a few changes have been made to CheeTah checks (mostly in checks output). 

Also, we have added Tabs interface - new concept which allows to gather all elements of the check together on one tab and analyse them there. Please have a look at Headers, Figures and Tables checks below for more detail about Tabs.

.. NOTE::
	
	If you find isses/errors which were not picked up by PuMa, please report such cases together with PII number to Alex via email.

Download
--------

You can download PuMa `here`_.	


Interface
---------

PuMa tool interface is depicted below.

.. image:: /_static/puma_interface.png
   :scale: 50%
   :alt: PuMa Interface


You can use PuMa to navigate to pii HTML page directly. No more copy/paste in the URL of other article and clicking on "HTML". You just need to paste pii in "Enter PII here" field and press "Go".

If "Open in the same tab" flag is active then PuMa will open article in the same tab. Otherwise, it will open it in a new tab.

If you open pii pages using PuMa, then you may like to run the check automatically when the page is loaded. To do that you can activate "Run check automatically" flag before pressing on "Go" button.

If you prefer running check manually, then deactivate "Run check automatically" flag and use "Run" button to launch the check.

If you need to get back to the "normal" (before-the-check) page view, click on "Refresh" button in Chrome.


Functionality
-------------

1. Article Title
================

PuMa checks:
	PuMa checks spelling and underlines (red dashed line) suspicious words.

PuMa does not check:
	PuMa does not check whether there are words in italics in the tite. 
	It does not check correct case of scientific terms.


2. Author List
==============

PuMa checks:
	PuMa checks the validity of author names (see standards for more detail).
		
		If name is valid, tool highlights it is green. 
		Otherwise - in amber.

PuMa does not check:
	There is no special check to verify the separators.


3. Affiliations and Author Notes
================================

PuMa checks:
	PuMa checks spelling and underlines (red dashed line) suspicious words.

	PuMa matches author affiliation numbers with affiliation texts. 

		It highlights all found matches in green. 
		Mismatches are highlighted in amber.

	PuMa highlighs in amber authors having no affiliation numbers.
	PuMa shows error message (in amber) if any of the following issues found: author names without affiliation  numbers, wrong order of affiliation text numbers, affiliation number in wrong format and texts without affiliation numbers.

	.. image:: /_static/puma_affiliation_errors.png
	   :scale: 50%
	   :alt: PuMa Interface

PuMa does not check:
	PuMa does not check affiliation text for validity (elements, separators, 2 affliation texts in one line etc)

4. Correspondence to:
=====================

PuMa checks:
	PuMa tries to match name(s) of author(s) in "Correspondence to:" section with a list of authors in front matter. 
	
		If tool finds matching names, it **underlines** found pair(s) in green, otherwise it highlights only "Corresponding to" name in amber.

	.. image:: /_static/puma_correspondence_to.png
	   :scale: 50%
	   :alt: PuMa Interface

PuMa does not check:
	PuMa does not check validity of email address.
	PuMa does not check format of correspondence line format (separators, correct spelling of "email" etc).

5. Keywords
===========

PuMa checks:
	PuMa checks whether allowed separator is used (, or ;).

	PuMa checks number of keywords.
		
		If number equals or is smaller than 5, it injects a message in green - "number of keywords is OK".
		Otherwise, it injects error message trying to provide details about the issue.

	PuMa also checks whether article has "Special Section" keywords (in this case it caters for 5 words + special sections words)

PuMa does not check:
	PuMa does not check the case or spelling of keywords.

6. Abbreviations
================

PuMa checks:
	PuMa checks whether allowed separators are used (: or , with ;).

	PuMa checks whether number of abbreviation pairs is smaller or equal to 5.

		If checks are successful, it injects - "number of abbreviations is OK" message in green.
		Otherwise it injects en error message in amber to the page.


	.. image:: /_static/puma_abbreviations_green.png
	   :scale: 50%
	   :alt: PuMa Interface

	.. image:: /_static/puma_abbreviations_amber.png
	   :scale: 50%
	   :alt: PuMa Interface

PuMa does not check:
	PuMa does not check the case or spelling of abbreviations.

7. Received, Accepted, Published dates
======================================

PuMa checks:
	PuMa checks the spelling and validates the dates.
		
		If date is correct, it marks it in green. 
		Otherwise it highlights it in amber.

	PuMA checks whether Received date is smaller than Accepted date and Accepted date is smaller than Published date.
		
		If everything is correct, dates are marked in green. 
		Otherwise in amber.


8. Callouts vs references
=========================

PuMa checks:
	PuMa tries to match callouts with references.
		
		If there is a full match, the tool injects a message that number of missing callouts and references equals to zero.
		Otherwise, it injects a message with numbers of missed callouts and/or references.

	PuMa checks the format of callouts. 
		
		If callout is not compliant with PubMed standards, it injects an error message - "Found (formatting) errors in callouts:" and specifies problem callouts.


9. Headers
==========
Headers check is a default Tab. Headers check is a table which contains all article headers.
That table contains headers in the same format and case, as presented in the article itself.


PuMa checks:
	PuMa checks each header against PubMed standards: format, position among other headers, mandatory/optional header, spelling.
	
		If check is successful, then green tick is placed in front of the corresponding header.
		If check is not successful, the red cross mark is placed in front of the corresponding header and error message is injected in "Problem description, if found" column.
	
	There can be situations (generally when we are checking subheaders), when PuMa requires your attention and input to make a decision whether header is OK or not. In such cases it puts amber exclamation mark in front of the header. You need to validate each such header manually.

	PuMa checks whether all mandatory headers are present in the paper (in accordance with PubMed standards).

		If all mandatory headers are present, then it injects the following message below the table: "Missing mandatory headings: None".
		If there are missing headers, then it injects a table with missed mandatory headers below the "check table".


PuMa does not check:
	PuMa does not check the validity of subheaders. This task should be done manually.


10. Figures
===========

Since "figures" code of article page is not standardised and greatly varies from vendor to vendor, "Figures check" is presented as interface, which speeds up and simplifies manual checking. 

TO RUN FIGURES CHECK, CLICK ON FIGURES TAB.

PuMa checks:
	PuMa tries to match Figure callouts with Figure IDs.

		If each Figure has at least one figure callout, then it injects the message that number of missing callouts and figures equals to zero.

		Otherwise, it injects a message with numbers of missed callouts and/or figures.

		Note: there are cases when figure callouts span a range (for example Figures 1-3). In this case if there is no callout for Figure 2, then this check will inject an error message that callout for table 2 is missing. Please keep in mind such cases when checking missed callouts.


	PuMa groups together figure and corresponding callouts on a "tile". So you can check both figure and callouts agains PuMa standards. It also shows all text lines where word "figure" was found (so that you can check whether that "figure" word is part of incorrectly formatted callout).


PuMa does not check:
	It does not do any of the Figues checks except for matching callouts with Figure IDs.

11. Tables
===========
Since "tables" code of article page is not standardised and greatly varies from vendor to vendor, "tables check" is presented as interface, which speeds up and simplifies manual checking. 

Note: table header in the test should be above the table itself. However, due to the page code issues, you will find table header below the table in the tables check. This is by design behaviour.

TO RUN TABLES CHECK, CLICK ON TABLES TAB.

PuMa checks:
	PuMa tries to match Table callouts with Table IDs.

		If each Table has at least one table callout, then it injects the message that number of missing callouts and tables equals to zero.

		Otherwise, it injects a message with numbers of missed callouts and/or tables.

		Note: there are cases when table callouts span a range (for example Tables 1-3). In this case if there is no callout for Figure 2, then this check will inject an error message that callout for table 2 is missing. Please keep in mind such cases when checking missed callouts.


	PuMa groups together table and corresponding callouts on a "tile". So you can check both figure and callouts agains PuMa standards. It also shows all text lines where word "table" was found (so that you can check whether that "table" word is part of incorrectly formatted callout).


PuMa does not check:
	It does not do any of the Table checks except for matching callouts with Table IDs.
	

12. Suppl. Materials
====================

TO RUN TABLES CHECK, CLICK ON TABLES TAB.

PuMa checks:
	PuMa puts all the lines containing "Supplementary" word on the tab. The idea is to have all callouts to supplementary materials on one tab, so that you can manually match them with supplementary files.

PuMa does not check:
	PuMa does not make any checks related to supplementary materials. All the checks should be done manually.



13. References
==============

PuMa checks:
	PuMa tries to find duplicate references. 

		If no duplicates are found, it injects the message "No duplicate references found" right below the "References" header.

		Otherwise, it injects a message with duplicate reference numbers.

	PuMa cheks Author list:

		If PuMa is able to find and validate all names of authors then it marks full author list in green.
		If PuMa finds an issue in author name(s) it marks that name(s) in amber.

		If PuMa is able to count names of authors and verify that that number is OK, then it marks **reference number** in green.
		If PuMa is not able to count names of authors, then it marks **reference number** in red.

	PuMa checks Citation data (in-house jourlans):

		PuMA checks "Citation Data" for in-house journals (Oncotarget, Aging, Genes and Cancer, Oncoscience)
		It tries to find in-house journal name and if PuMa finds it, it checks the format of citation data (year, volume, pages. DOI)

		If citation data format is OK and correct DOI is present, PuMa marks citation data in green.
		Otherwise it does not mark citation data in any color at all.

		Tool also tries to match names of in-house journals. For Oncotarget and Oncosience it ties to find "ocnotarget" and "ocnoscience".
		For Aging (Albany NY) it tries to find "aging" word. For Genes Cancer it tries to find "genes cancer, genescancer, genes&cancer, genes &cancer, genes& cancer, genes & cancer, genesandcancer, genesand cancer, genes andcancer, genes and cancer" words. The search for words is case insensitive.

		If any of those words are fond in reference, tool marks them in yellow.

		If you find words marked in yellow, pay close attention to the reference, as it can be incorrectly formatted reference for in-house journal.

	PuMa checks Citation data (all other journals):

		PuMa checks journal name (both full and abbreviated) to be written the same way as on PubMed site. 

			If journal is written incorrectly (or is not indexed by PubMed), then PuMa will make a suggestion regarding correct spelling. In this case journal title will be marked in dark yellow.

			If journal title was found on the PubMed, then PuMa will mark it in green.

		PuMa checks the format of citation data. 

			If one or more elements are not comliant with the standards, then PuMa will highlight such element(s) in amber.

			PuMA will mark all correct elements in green.

	PuMa marks all instances of [PII] and [Internet] in amber.

	
PuMa does not check:
	PuMa does not check books, report and websites references.

	PuMa does not check "Ahead of print" references (however, certain elements can be marked in green correctly as a side effect of other checks).

	PuMa does not check anything described in "References: General Checks" section of the PubMed standards (except for [PII] and [INTERNET]).

	PuMa does not check title of the article in the reference.


