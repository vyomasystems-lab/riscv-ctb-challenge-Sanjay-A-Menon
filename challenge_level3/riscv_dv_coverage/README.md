# RISCV-DV

Test generation using riscv-dv
```
run --target rv32i --test riscv_cov_test --testlist testlist.yaml --simulator pyflow
cov --dir out_*/ --simulator=pyflow --enable_visualization
```

Coverage related information is obtained in the below link:
https://github.com/chipsalliance/riscv-dv/tree/master/pygen/pygen_src

# Challenge
The challenge is to fix the tool problem in generating coverage and make rv32i ISA coverage 100%

The report submitted here does not seem to have 100% coverage due to some limitations of the tool with the pyflow test generator and coverage generation tool. \
These limitation can be found in the github issues below:-

https://github.com/chipsalliance/riscv-dv/issues/898 \
https://github.com/chipsalliance/riscv-dv/issues/928 \
https://github.com/chipsalliance/riscv-dv/issues/781

A KeyError failure was also found when running coverage while running over tests generate with hazard test scenarios. \
Hence 100% coverage was not found achievable with the current tool version.

# Coverage Report

```
Output of Coverage for riscv_cov_test
Groups Coverage Summary
Total groups in report: 147
+---------+----------+-----------------------------+
|  SCORE  |  WEIGHT  |            NAME             |
+=========+==========+=============================+
| 21.875  |    1     |          opcode_cg          |
+---------+----------+-----------------------------+
|  31.25  |    1     |          csrrw_cg           |
+---------+----------+-----------------------------+
|   80    |    1     |        rv32i_misc_cg        |
+---------+----------+-----------------------------+
|   50    |    1     |      mepc_alignment_cg      |
+---------+----------+-----------------------------+
|  87.5   |    1     |           beq_cg            |
+---------+----------+-----------------------------+
| 74.2188 |    1     |           jal_cg            |
+---------+----------+-----------------------------+
|   75    |    1     |           lui_cg            |
+---------+----------+-----------------------------+
| 89.2857 |    1     |           addi_cg           |
+---------+----------+-----------------------------+
|   75    |    1     |          auipc_cg           |
+---------+----------+-----------------------------+
|  81.25  |    1     |           ori_cg            |
+---------+----------+-----------------------------+
| 90.625  |    1     |           add_cg            |
+---------+----------+-----------------------------+
| 90.625  |    1     |           sub_cg            |
+---------+----------+-----------------------------+
| 90.625  |    1     |           sra_cg            |
+---------+----------+-----------------------------+
|  81.25  |    1     |           andi_cg           |
+---------+----------+-----------------------------+
|   85    |    1     |           srli_cg           |
+---------+----------+-----------------------------+
| 86.1111 |    1     |           and_cg            |
+---------+----------+-----------------------------+
| 90.625  |    1     |           srl_cg            |
+---------+----------+-----------------------------+
| 90.625  |    1     |           sll_cg            |
+---------+----------+-----------------------------+
| 86.1111 |    1     |           xor_cg            |
+---------+----------+-----------------------------+
| 86.1111 |    1     |            or_cg            |
+---------+----------+-----------------------------+
| 90.625  |    1     |           sltu_cg           |
+---------+----------+-----------------------------+
| 89.2857 |    1     |          sltiu_cg           |
+---------+----------+-----------------------------+
|  81.25  |    1     |           xori_cg           |
+---------+----------+-----------------------------+
| 89.2857 |    1     |           slti_cg           |
+---------+----------+-----------------------------+
|   85    |    1     |           srai_cg           |
+---------+----------+-----------------------------+
| 90.625  |    1     |           slt_cg            |
+---------+----------+-----------------------------+
|   85    |    1     |           slli_cg           |
+---------+----------+-----------------------------+
```
