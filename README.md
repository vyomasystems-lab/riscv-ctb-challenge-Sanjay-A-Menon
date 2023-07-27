# riscv_ctb_challenges

## Challenge lvl1 - logical

Fixed the test file by fixing the operands associated with some instructions. Fixed test.S file can be found.

## Challenge lvl1 - loop

Added code to the test.S file for the program to end gracefully after looping exactly 3 times. See fixed test.S

## Challenge lvl1 - illegal

Added fixes to the handler to complete the test instead of looping over the same illegal inst. See fixed test.S

## Challenge lvl2 - instructions

Fixed the bug in the test generation by removing rv64m insts from the yaml

## Challenge lvl2 - exceptions

Wrote a small assmebly routine to create an illegal instruction exception exactly 10 times and a routine to handle them. An override to the existing handler was done by overrding the existing handler with my custom handler and then restored at a later point. Changes should be found in the associated yaml file.

Note :- While running the test, sometimes an anomalous illegal inst exception causing fcsr read was seen to occur. The test generated do not account for this anomaly, hence may observe the exception count to be 11 instead of 10 in some cases.

## Challenge lvl3 - exposing bugs

### ori inst result mismatch

```
core   0: 0xffffffff80000648 (0x1bf6ea13) ori     s4, a3, 447 --> spike trace snippet
3 0x80000648 (0x1bf6ea13) x20 0x3c6d75ff --> spike
3 0x80000648 (0x1bf6ea13) x20 0x3c6d75cf --> RTL model
```

### or inst result mismatch

```
core   0: 0xffffffff8000072c (0x00a26233) or      tp, tp, a0 --> spike trace snippet
3 0x8000072c (0x00a26233) x 4 0x1840c7b6  --> spike
3 0x8000072c (0x00a26233) x 4 0x1840c7a6  --> model
```

## Challenge lvl3 - coverage

Look at README file in challenge_level3/riscv_dv_coverage/
