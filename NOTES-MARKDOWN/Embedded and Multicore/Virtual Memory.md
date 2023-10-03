Possiamo tenere le parti attive dei processi nella main memory e quelle inattive nello storage secondario.


## Swap space

Spazio nello storage secondario dedito ad ospitare le parti di processi in idle.



## Pages

Blocchi di dati e istruzioni, attivamente in uso o meno. Possono essere piazzati nella main memory o nello swap space.


## Page table

Tabella che traduce i virtual addresses in physical addresses.
Questa tabella è totalmente associativa(non ci sono restrizioni su dove si trovano le entry).

### Translation-lookaside buffer

Cache per la page table, essenzialmente. Qui vengono registrate le page posizioni delle page più usate.

We use hash to search for shit.