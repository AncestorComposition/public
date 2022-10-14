Estimate the ancestor composition of your genome using DNA match segment data and information about common ancestors.

### FAQ
1.   How does this notebook preserve my privacy?
    *   The CSV files that you upload are stored in a temporary private Google Colab workspace and are not available to others.
    *   The data is anonymized (all names removed) before a solver API is called to estimate your ancestral composition.
    *   This Colab notebook with your ancestral composition will be private to you unless you share it with others.
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

