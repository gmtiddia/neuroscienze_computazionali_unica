---
permalink: /software/
title: "Software"
author_profile: false
---

## NEST GPU

**NEST GPU** è un simulatore di reti neurali spiking ad alte prestazioni, scritto in C++/CUDA e 
pensato per sfruttare le GPU NVIDIA. Permette di simulare modelli di larga scala, fino a 
reti corticali multi-area con milioni di neuroni e miliardi di sinapsi, in tempi molto inferiori
rispetto alle simulazioni su CPU, sia su singola GPU sia su cluster multi-GPU tramite MPI.

### Caratteristiche principali

- Simulazione di reti di grandi dimensioni su GPU, con costruzione della rete
  direttamente sul device
- Scalabilità su più GPU e più nodi con MPI
- Interfaccia Python con sintassi vicina a quella di [NEST](https://www.nest-simulator.org/),
  per facilitare la migrazione dei modelli esistenti
- Modelli di neuroni, sinapsi e dispositivi di stimolazione/registrazione
- Software open source, rilasciato con licenza GPL-2.0

### Risorse

- **Codice sorgente:** [github.com/nest-gpu/nest-gpu](https://github.com/nest-gpu/nest-gpu)
- **Documentazione:** [nest-gpu.readthedocs.io](https://nest-gpu.readthedocs.io)
- **Esempi e benchmark:** [github.com/nest-gpu/nest-gpu/python/examples](https://github.com/nest/nest-gpu/tree/main/python/examples)

### Il nostro contributo e la collaborazione

Il gruppo di Cagliari è capofila nello sviluppo della libreria, e tuttora si occupa sia
di implementazione di nuove feature nel codice di simulazione, ma anche delle procedure
di validazione rispetto alla versione CPU e del benchmarking.

Lo sviluppo è inquadrato in una collaborazione internazionale, che vede l'istituto [IAS-6](https://www.fz-juelich.de/en/ias/ias-6) del
Centro di Ricerca di Jülich, l'Università del Sussex e la Sezione di Roma dell'INFN, con particolare riferimento al 
[Gruppo APE](https://apegate.roma1.infn.it/).
