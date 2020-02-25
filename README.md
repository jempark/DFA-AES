# Differential Fault Analysis of AES 
## Overview
Implement differential fault analysis (DFA) attack of one-block AES encryption.

## Details
Implement a differential fault analysis attack on AES encryption in software. 

This will consist of two parts:
1. on-line (fault injection) phase and off-line (fault analysis) phase. The first phase is to simulate fault injections to obtain faulty outputs. You have to write your simulator based on the AES files to simulate fault injection on a selected intermediate state, defined by the fault model. From the fault injection simulation, you obtain a pair of faculty ciphertext (F) and correct ciphertext (C), with the same plaintext input under fault injection and normal execution, respectively. The second phase is to analyze the collected pairs of ciphertexts C, F to retrieve the AES encryption key. Note that you can refer to the aes.c file and utilize the MixColumns function in your analysis code to simulate the fault propagation through MixColumns to generate thes output differential.

2. *Fault model*: The fault type is random fault, and the location is a known byte position (i.e., the row and column indices are both known) of the input state of 9th round MixColumns operation. Your goal is to recover the corresponding 4-byte subkey. One {C,F} pair may not give you the unique result (subkey value and fault value), and you need to produce multiple {C,F} pairs by changing the plaintext input while keeping the same fault injection (the fault ∆ is the same). Analyze how many encryption output pairs are needed to find the entire 4-byte subkey, and how the key candidate space is screened with more encryption pairs analyzed. Print this statistics as your analysis code runs.
