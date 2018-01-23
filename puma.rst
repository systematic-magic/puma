===========================
PubMed Checking Tool (PuMa)
===========================

PubMed Checking Tool (PuMa) is designed to simplify and speed up checking of the articles for PubMed (AOP) process.


It should be noted that the tool is not a "push the button - check everything for me" solution. It is a set of checks and interfaces which make review process easier. Every attempt is made to identify and highlight article issues/errors, but due to the fact that every vendor codes article pages a bit differently (sometimes very differently), certain issues/errors can slip through the cracks.

Therefore, we encourage you to make quick manual checks while relying on the tool. Tool will identify 99% of "correct" cases by highlighting this or that page element in green. It will also attempt to identify issues/errors and most likely will succeed in it in 70-80% of cases. The rest 20-30% should be checked by you manually.


.. NOTE::
	
	If you find isses/errors which were not picked up by PuMa, please report such cases together with PII number to Alex via email.

Download
--------

You can download CheeTah `here`_.


Interface
---------
You can use CheeTah to navigate to pii HTML page directly. No more copy/paste in the URL of other article and clicking on "HTML". You just need to paste pii in "Enter PII here" field and press "Go".

If "Open in the same tab" flag is active then CheeTah will open article in the same tab. Otherwise, it will open it in a new tab.

If you open pii pages using CheeTah, then you may like to run the check automatically when the page is loaded. To do that you can activate "Run check automatically" flag before pressing on "Go" button.

If you prefer running check manually, then deactivate "Run check automatically" flag and use "Run" button to launch the check.

If you need to get back to the "normal" (before-the-check) page view, click on "Refresh" button in Chrome.


Functionality
-------------

1. Article Title
================

**What PuMa does:**
	PuMa checks spelling and underlines (red dashed line) suspicious words.

**What PuMa does not do:**
	PuMa does not check whether there are words in italics in the tite. 
	It does not check correct case of scientific terms.


2. Author List
==============

**What PuMa does:**
	PuMa checks the validity of author names (see standards for more detail).
	If name is valid, tool highlights it is green. Otherwise - in amber.

**What PuMa does not do:**
	There is no special check to verify the separators. However, as a side effect of name check, it can highlight all non-comliant separators in amber.



2. Affiliations and Author Notes
================================

**What PuMa does:**
	PuMa checks spelling and underlines (red dashed line) suspicious words.

	PuMa matches author affiliation numbers with affiliation texts. It highlights all found matches in green. Mismatches are highlighted in amber.

	PuMa highlighs in amber authors having no affiliation numbers.
	PuMa shows error message (in amber) if any of the following issues found: author names without affiliation  numbers, wrong order of affiliation text numbers, affiliation number in wrong format and texts without affiliation numbers

**What PuMa does not do:***
	PuMa does not check affiliation text for validity (elements, separators, 2 affliation texts in one line etc)

3. Correspondence to:
=====================

**What PuMa does:**
	PuMa tries to match name(s) of author(s) in "Correspondence to:" section with list of authors in front matter. 
	If tool finds matching names, it **underlines** found pair(s) in green, otherwise it highlights only "Corresponding to" name in amber.


**What PuMa does not do:***
	PuMa does not check validity of email address.
	
	PuMa does not check format of correspondence line format (separators, correct spelling of "email" etc).

4. Keywords
===========

**What PuMa does:**
	PuMa checks whether allowed separator is used (, or ;).

	PuMa checks number of keywords.
	If number equals or is smaller than 5, it injects a message in green - "number of keywords is OK".
	Otherwise, it injects error message trying to provide details about the issue.

	PuMa also checks whether article has "Special Section" keywords (in this case it caters for 5 words + special sections words)

**What PuMa does not do:***
	PuMa does not check the case or spelling of keywords.

5. Abbreviations
================
**What PuMa does:**
	PuMa checks whether allowed separators are used (: or , with ;).

	PuMa checks whether number of keywords is smaller or equal to 5.

	If checks are successful, it injects - "number of abbreviations is OK" message in green.
	Otherwise it injects en error message in amber to the page.


**What PuMa does not do:***
	PuMa does not check the case or spelling of abbreviations.


