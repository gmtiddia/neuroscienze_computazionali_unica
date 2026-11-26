---
title: 'Articolo sulla simulazione di modelli spiking con NeuronGPU'
date: 2021-02-17
permalink: /posts/2021/02/neurongpu-paper/
tags:
  - publication
---

Articolo pubblicato!
======

È appena stato pubblicato [un articolo](https://doi.org/10.3389/fncom.2021.627620) sulle simulazioni di reti neurali spiking a densità di connessioni naturale utilizzando NeuronGPU, un simulatore di reti neurali spiking che sfrutta le GPU.

Interamente sviluppato all'Università di Cagliari, e con una collaborazione con il gruppo APE della Sezione di Roma dell'INFN, il simulatore attualmente è in grado di effettuare simulazioni su singole GPU NVIDIA.

Tra gli altri modelli implementati, è stato implementato sul simulatore il modello del [mircocircuito corticale](https://doi.org/10.1093/cercor/bhs358), che rappresenta $1 \text{mm}^2$ di corteccia cerebrale, con opportuna struttura stratificata e circa $90000$ neuroni e $3\cdot 10^8$ connessioni.

Il codice del simulatore NeuronGPU è stato poi reso disponibile online. Presenta diverse similitudini con il codice del simulatore CPU NEST.
