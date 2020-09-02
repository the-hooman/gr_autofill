.. _operations: 

Use-case view
=============

Use case diagram
----------------

.. figure:: /images/use-case.png


Use case specification
----------------------

===================== ============================================================================================================================
 UC ID and Name:      UC-501 Creating a new document with text hints
===================== ============================================================================================================================
*Created by:*         Liudmyla Kolesnyk       *Date created:*        29.01.2020
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Primary Actor:        User
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Trigger:              Clicking the “New” icon to create a new document
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Description:          While typing in the text, text suggestions appear to complete the sentences
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Preconditions:        1. User is logged in to the site
                      2. A new file has been created
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Postconditions:       1. To select the suggested text, User presses Tab button
                      2. A tooltip below the text shows the number of suggestions per document
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Normal flow:          1. User clicks on the “New” icon
                      #. a dialog window appears with the options of a document template
                      #. user is prompted to select either “Enable suggestion” or “Disable suggestion”
                      #. upon selected “Enable suggestion” option, other options of text formatting are enabled:
                         #. “Select doc type” with the drop-down of: Letter, Report, Article, Ad
                         #. Formal tone / Informal tone
                      #. proceed to document creation in the new window with the selected business rules
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Alternative flows:    * Upon selecting “Disable suggestion” option, proceed to regular document creation flow without text hint feature
                      * If the “Enable suggestion” option is selected, and nothing is changed in the “Select doc type” and Formal tone / Informal tone, proceed to create a document with the default options of doc type & tone.
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Exceptions:           The feature is not to be enacted upon new document creation when the 'Disable suggestion option is selected
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Priority:             Should be implemented after the main feature for Text Analysis & Suggestions is ready
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Frequency of use:     Each time the feature is enabled in a new document
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Business rules:       1. The feature is available for all the users with “American English” selected in the Language Preference in the Account → Customize settings
                      2. The feature is activated upon selected option “Enable suggestion”
                      3. “Select doc type” provides the drop-down of formats linked to the types of documents: 
                         * Letter
                         * Report
                         * Article
                         * Ad
                      4. Formal tone / Informal tone option activates tone format per templates of either tone option
                      5. Suggested text to be shown in the background in grey color as per specification for the text hint feature
--------------------- ----------------------------------------------------------------------------------------------------------------------------
Assumptions:          * The feature is available for Grammarly’s registered users, works by given business rules and for American English language only.
                      * The feature cannot be forcefully turned off for users with the indicated Language Preference.        
===================== ============================================================================================================================


User story
----------

============ ========================================================
 User Story: Creating a new document with text hints
============ ========================================================
------------ --------------------------------------------------------
**As a**     User
**I want**   to complete sentences with the suggested text
**So that**  to avoid typing commonly used phrases
------------ --------------------------------------------------------
*Acceptance Criteria*
--------------------------------------------------------------------- 
**Given**    I have logged in on the site
**and**      I click on the “New” icon
**and**      the dialog window appears
------------ --------------------------------------------------------
**When**     I select “Enable suggestion”
**and**      choose one of the suggested doc types
**and**      select either of suggested tones
------------ --------------------------------------------------------
**Then**     a new document is created in the new window
**while**    typing
**and**      text hint appear                      
============ ========================================================

