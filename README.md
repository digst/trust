# trust
Her opdaterer vi (DIGST) den fællesoffentlige referencearkitektur for brugerstyring.

Vi har hente teksten fra https://arkitektur.digst.dk/sites/default/files/123_referencearkitektur_for_brugerstyring_pdfa.pdf
og placereret den i /old/

Den aktuelle arbejdsversion findes i roden og starter i index.md

Hvis der er brug for arbejde med flere fremtidige version, brancher vi, men anvender altid master branch til kommunikation.

Vi anvender pandoc til at lave word versioner når vi har brug det. Senere måske bikeshed til at producerer det færdige produkt.

`curl https://api.csswg.org/bikeshed/ -F file=@index.md -F force=1 > index.html`

*eller*

`https://api.csswg.org/bikeshed/``
