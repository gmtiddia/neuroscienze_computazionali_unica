---
title: "Articolo sull'introduzione in NEST GPU della costruzione della rete direttamente su GPU"
date: 2023-08-24
permalink: /posts/2023/08/netconstr-paper/
tags:
  - publication
  - simulation technology
---

Articolo pubblicato!
======

È appena stato pubblicato [un articolo](https://doi.org/10.3390/app13179598) in cui viene implementato un metodo di costruzione di reti neurali spiking a runtime direttamente su singole GPU. 

In particolare, l'implementazione è stata effettuata su NEST GPU, garantendo un miglioramento nel tempo di costruzione della rete di più di un ordine di grandezza rispetto alla versione precedente del simulatore. Ora, i tempi di costruzione sono in linea con la versione CPU e con altri simulatori GPU, con il vantaggio di avere la fase di costruzione direttamente al runtime, ovvero senza la necessità di dover compilare il codice.
