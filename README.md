# riscv_ctb_challenges

Challenge lvl3 - exposing bugs

1. ori inst result mismatch
core   0: 0xffffffff80000648 (0x1bf6ea13) ori     s4, a3, 447 --> spike trace snippet
3 0x80000648 (0x1bf6ea13) x20 0x3c6d75ff --> spike
3 0x80000648 (0x1bf6ea13) x20 0x3c6d75cf --> RTL model

2. or inst result mismatch
core   0: 0xffffffff8000072c (0x00a26233) or      tp, tp, a0 --> spike trace snippet
3 0x8000072c (0x00a26233) x 4 0x1840c7b6  --> spike
3 0x8000072c (0x00a26233) x 4 0x1840c7a6  --> model