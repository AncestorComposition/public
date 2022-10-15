Estimate the ancestor composition of your genome using DNA match segment data and information about common ancestors.


#### Detailed Directions
1.  Open the notebook Ancestor_Composition_Solver in Google colab.
2. Download matching segment data CSV files from [23andMe](https://www.23andme.com/), [MyHeritage](https://www.myheritage.com/), and/or [FamilyTree DNA](https://www.familytreedna.com/).
3.   For some of your matches (at least 25 - 300 individuals, for best results), identify the most recent common ancestor or ancestral couple that you share with the match.  This can be done using MyHeritage "Theory of Relativity", Ancestry "ThruLines", FamilyTree DNA, or 23AndMe "Family Tree".  Record this information in a "Common Ancestor" CSV file with five columns and a header row:
    1)   "Match Name", a column for which each row contains the names of a matching individual as it appears in a matching segment CSV file.
    2)  "Male Ancestor Name".  Each row of this column contains the name of the most recent male ancestor that you share with the matching individual.
    3)  "Male Ancestor #", the [ahnentafel number](https://en.wikipedia.org/wiki/Ahnentafel) of the common male ancestor.
    4) "Female Ancestor Name".  Each row of this column contains the name of the most recent female ancestor that you share with the matching individual.
    5) "Female Ancestor #", the ahnentafel number of the common female ancestor.
5. Click on the folder icon in Google Colab to expand the "Files" pane.
 6. Click the "Upload to session storage" button which will appear in the upper left of Google Colab to upload CSV files for match shared segments (from MyHeritage, FamilyTree DNA, and/or 23andMe) and the CSV file (from Step 4) with common ancestor information for some of your matches.
7. Run the Ancestor Composition Solver.  The results will be displayed in:
    * An ideogram showing which regions of your chromosomes were inherited from specific ancestors.
   *  A fan chart showing the percentage of your genome inherited from ancestors in each generation.
8. You may export the results to a CSV file.

### FAQ
1.   How does this notebook preserve my privacy?
      * The CSV files that you upload are stored in a temporary private Google Colab workspace and are not available to others.   
      * The data is anonymized (all names removed) before a solver API is called to estimate your ancestral composition.
      * This Colab notebook with your ancestral composition will be private to you unless you share it with others.
2.   How does the solver work?
       *   The solver assigns DNA segments to ancestors in a way that is:
            * **Self-consistent**.  Segments from one ancestor may overlap with segments from another ancestor only if the two ancestors are on the same line.
            * **Maximally consistent with common ancestor matches**.  The solver assigns segments to ancestors in a way that it is 100% consistent with the maximum possible number of common ancestor matches. It is generally not possible to be consistent with all common ancestor matches, due to phasing errors, false positives, and DNA shared from multiple lines.
            * **Supported by a large percentage of other match data**.  Ancestor segments from a match with an unknown common ancestor are used to expand the set of ancestor segments in a way that is self-consistent and fully consistent with known common ancestor matches.

3. How has the solver been validated?
    * Limited validation testing has shown that the results of the solver:
        * Are self-consistent.
        * Are maximally-consistent with common ancestor matches.
        * Are supported by a large percentage of other match data.
        * Predict a number of crossovers on the maternal and paternal lines that are within typical ranges, if sufficient common ancestor data is provided.
        * Predict inheritance percentages for grandparents and great-grandparents that are within typical ranges, if sufficient common ancestor data is provided.
    * Please note that the results can only be as accurate as the provided common ancestor information.

4. Who is the developer?
    * Joshua Isom is a professional data scientist with an MS in Computer Science and a PhD in Chemical Engineering.  He is also a family history enthusiast.

5. Questions or problems running this notebook?
     * Please send an email to info@ancestorcomposition.com

### License
Copyright 2022 by Joshua David Isom

This notebook is licensed for personal, noncommercial use under the folllowing terms:
https://creativecommons.org/licenses/by-nc-nd/4.0/

The API called by this notebook may be used only for personal, noncommercial use.

Inquiries for commercial licenses may be sent to info@ancestorcomposition.com.

