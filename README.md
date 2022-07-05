# QiskitのQAOAを利用して、組み合わせ最適化問題を解く

qiskit-communityによるオリジナルのページは以下です。  
https://qiskit.org/textbook/ja/ch-applications/qaoa.html

修正したものは以下です。  
https://github.com/yoshioka1128/qaoa.ipynb/blob/master/qaoa.ipynb

本家にプルリクを出しているところです(以下参照)。  
https://github.com/qiskit-community/qiskit-textbook/pull/1448

修正点の概要は以下です。  
## Changes made
In the last equations in section [5.2](https://qiskit.org/textbook/ja/ch-applications/qaoa.html#5.2-最適な試行状態のパラメーター-), the right hand side of f<sub>A</sub>, f<sub>B</sub>, and F<sub>1</sub> are incorrect.
Results that rely on this are also incorrect.

The modified formulas are as follows:  
<img width="524" alt="eqfAfB" src="https://user-images.githubusercontent.com/88071178/176978002-b2deb7f8-3cf0-4d7b-b057-ea26dfebb0c1.png">
<img width="545" alt="eqF1" src="https://user-images.githubusercontent.com/88071178/176978007-95be6ffe-0c0d-46dc-92ae-a89576af8621.png">  
According to the above F1, the maximal expectation value obtained by grid search is improved from 3.431 to 3.927.

## Justification
The modification improves the calculation results.
The maximal expectation value obtained by grid search is improved from 3.431 to 3.927.
The simulated mean value M1_sampled is improved from 3.29 to 3.93.
These analytical expressions and calculated results were verified by two independent calculations, a numerical state vector calculation and a quantum circuit calculation.

The results of probability have been improved as follows:

### before the correction  
<img width="530" alt="before_probbit" src="https://user-images.githubusercontent.com/88071178/176978089-2d29660f-c50d-40d9-a136-647f3c1c0ddc.png">
<img width="521" alt="before_probcost" src="https://user-images.githubusercontent.com/88071178/176978098-fcde461f-ebeb-492f-b66f-262cbdb672f9.png">  

The simulated mean value is 3.29.

### after the correction  
<img width="530" alt="after_probbit" src="https://user-images.githubusercontent.com/88071178/176978107-58307d00-531f-42c4-985c-3258a1b5219f.png">
<img width="521" alt="after_probcost" src="https://user-images.githubusercontent.com/88071178/176978123-0319d62b-47d1-4b32-a449-2a2d0c74ae6f.png">  

The simulated mean value is improved from 3.29 to 3.93 (exact: 4.00).
