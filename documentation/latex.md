# Latex



## Bibliography and references

Manipulating references using `biblatex` with `backend=biber`. 



### Removing selective fields

Often when using the Mendeley Web Importer on published journals it also imports the relative arXiv link and arXiv IDs. However it is not commonly accepted to see both the journal and the arXiv ID fields in the bibliography of a particular text. Below is example code of how to solve this issue by pasting it in the preable of your main.tex file:



```tex	
\DeclareSourcemap{
    \maps[datatype=bibtex]{
        \map{
            \step[fieldsource=journal, final] % if contains 'journal' field, stop
            \step[fieldsource=eprint, null] % delete field
            \step[fieldset=eprinttype, null] % delete field
            \step[fieldset=arxivId, null] % delete field
            \step[fieldset=archivePrefix, null] % delete field
            \step[fieldsource=arxiv, null] % delete field
            \step[fieldsource=arxivID, null] % delete field
            \step[fieldset=archiveprefix, null] % delete field
            \step[fieldset=arxivid, null] % delete field
            \step[fieldset=eprint, null] % delete field
            }
        }
}

```



[Brandon]
