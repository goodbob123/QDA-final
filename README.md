## usage:
1. compile qsyn
2. ./qsyn
3. qcir unitary-decompose <input_filename> <output_filename>

* input file格式
    * 如final_testcase/0
    * 先input矩陣大小n,再input欲輸入之矩陣,矩陣element格式為(x,y).每個element對應一個複數,x為實部,y為虛部.
    * unitary-decompose 預設的 qbit 順序是 Q = q[0], q[1] ... q[N], 和 qiskit 是不一樣的
        ＊ e.g. input file的第三行是 |011>, 代表q[0], q[1]為1，q[2]為0
* output為.qasm檔

## checker:
1. you should prepare two files, one is the input matrix, another is the origin circuit
2. In ./dofile, change "./final_testcase/example.txt" to the path of your input matrix, and "./final_testcase/example.qasm" to the path of your origin circuit
3. run "./qsyn -f ./dofile". If the circuit are equivalent, you would get diagonal matrix.
* notice that if you directly use qsyn to get the input matrix for decompose, since assumption for the qubit order is differ, you would get wrong result