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

	PuMa checks whether number of abbreviation pairs is smaller or equal to 5.

	If checks are successful, it injects - "number of abbreviations is OK" message in green.
	Otherwise it injects en error message in amber to the page.


**What PuMa does not do:***
	PuMa does not check the case or spelling of abbreviations.

6. Received, Accepted, Published dates
======================================

**What PuMa does:**
	PuMa checks the spelling and validates the dates.
	If date is correct, it marks it in green. Otherwise it highlights it in amber.

	PuMA checks whether Received date is smaller than Accepted date and Accepted date is smaller than Published date.
	If everything is correct, dates are marked in green. Otherwise in amber.


6. Callouts vs references
=========================

**What PuMa does:**
	PuMa tries to match callouts with references.
	If there is a full match, the tool injects a message that number of missing callouts and references equals to zero.
	Otherwise, it injects a message with numbers of missed callouts and/or references.

	PuMa checks the format of callouts. If callout is not compliant with PubMed standards, it injects an error message - "Found (
	formatting) errors in callouts:" and specifies problem callouts.


7. Headers
==========
Headers is a check which appears in Tabs by default. Headers check is a table with all headers in the article.
That table contains headers in the same format and case, as presented in the article itself.


**What PuMa does:**
	PuMa checks each header against PubMed standards: format, position among other headers, mandatory/optional header, spelling.
	
	If check is successful, then green tick is placed in front of the corresponding header.
	
	If check is not successful, the red cross mark is placed in front of the corresponding header and error message is injected in "Problem description, if found" column.
	
	There can be situations (generally when we are checking subheaders), when PuMa requires your attention and input to make a decision whether header is OK or not. In such cases it puts amber exclamation mark in front of the header. You need to validate each such header manually.

	PuMa checks whether all mandatory headers are present in the paper (in accordance with PubMed standards).

	If all mandatory headers are present, then it injects the following message below the table: "Missing mandatory headings: None".

	If there are missing headers, then it injects a table with missed mandatory headers below the "check table".


**What PuMa does not do:**
	PuMa does not check the validity of subheaders. This task should be done manually.


7. Figures
==========

Since "figures" code of article page is not standardised and greatly varies from vendor to vendor, "Figures check" is presented as interface, which speeds up and simplifies manual checking. 

**What PuMa does:**



