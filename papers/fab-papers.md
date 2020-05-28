# Notes on fabrication/architecture papers

 <!-- toc -->

### [CMOS architecture for a spin-based quantum computer - M. Veldhorst](https://www.nature.com/articles/s41467-017-01905-6.pdf)

A paper discussing the how a CMOS architecture for spin-$$1/2$$ qubits might be scaled.  Single qubit gates are implemented using microwave cavity, two qubit gates via exchange interactions and read out by gate based dispersive readout. They suggest how transistor based control circuit with charge storage electrodes could be used to operate a dense and scalable two dimensional qubit system. 

In classical computing Silicon based CMOS integrated circuits (ICs) have scaled to billions of transistors. A key architectural aspect of IC is the parallel addressing through word line and bit line, facilitating  rapid read and write operations on large 2D arrays of bits. Unfortunately, this cannot be applied directly to qubit arrays. As the tolerance levels are small so each qubit must be individually tunable. 

This paper develops an architecture which allows for parallel addressing of silicon spin qubits, while solving the tunability issue through 'floating memory gate electrodes' that can be routinely reset, similar to dynamic random access memory. Their architecture requires $$\mathcal{O}(\sqrt{N})$$ lines for $$N $$ qubits. 
---
