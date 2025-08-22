# Counter - Clock Synchronous counter in Verilog

### First test:
In this test I have first ran the plain verilog testbench. Note each period is 10ns in this bench.

Compiler to translate the verilogs
```
iverilog -o count_up_output counter.v count_up_tb.v  
```
Run the systemverilog testbench and visualize
```
vvp count_up_output     
gtkwave dump.vcd    
```

Then we run the similar test with pycocotb and we also do assertion which let us not only verify visually but through exact expected values. Configuration of files are in make file so simply run `make`. Use the gtkwave command again to visualize.

### Second Test:
This second test was made by the HardwareTeam site to show we can make reset async to run concurrently while the clock is running. This async test is particularly interesting as I modified the initial test showing how this counter is also synchronous to the clock.

You will see in the image, the reset went high at 2ns but the counter didn't go 0 but in next clock rising edge. It is because the counter is sync with clocks rising edge.

[MIT](https://choosealicense.com/licenses/mit/)