# VHDL Counter with Race Condition
This repository demonstrates a potential race condition in a simple VHDL counter and its solution.

## Bug Description
The original `buggy_counter.vhdl` code implements a counter using a signal `internal_count` and an output port `count`.  The assignment `count <= internal_count` is not synchronized with the clock edge. This means there's a race condition where the `count` port may show intermediate or incorrect values during the clock cycle where `internal_count` updates, especially at high clock frequencies.

## Solution
The `fixed_counter.vhdl` file presents a corrected version.  The output `count` is now assigned within the clocked process, ensuring synchronous updates and eliminating the race condition. This change guarantees that the output `count` is always an accurate reflection of the `internal_count` state.