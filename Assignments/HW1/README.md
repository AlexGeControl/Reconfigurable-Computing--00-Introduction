# ECE636 Reconfigurable Computing

## HW1 Field Programmable Gate Arrays

---

### EX1 Relationship between Minimum I and Cluster Size N & LUT Size K
**Based on the experiments described in the Betz and Ahmed papers, what can you summarize about I for a given N if K=4? 
What happens if the value of K is changed?**

**ANS**: In order to use at least 98% of the LUTs inside the cluster, for given cluster of N BLEs and each BLE of LUT of size K, 
the minimum number of inputs I is determined through simulation with *logic optimization, technology mapping and logic placement* as follows:


    I = (K / 2) * (N + 1)
    
 
This agrees very well with previous results for K = 4, that is, the minimum I should be 2 * N + 2, which is (4 / 2) * (N + 1).

---

### EX2 Area Cost Composition
**Where are most of the transistors located in the FPGA, in the logic or in the interconnect? 
Explain why Fc should be less for larger cluster sizes.**

**ANS**: Most of the transistors are located in the interconnect. 

Input to larger cluster can be shared through multiplexer. Besides, reduced input size can make the whole circuit faster by reducing critical path delay.

---

### EX3 Area Cost Calculation
**Using the transistor area estimation approaches used in class for a multiplexer, lookup table, and flip flop determine exactly how transistors that make up a single logic cluster are allocated for N = 6, I = 12. 
Include equations to determine this area for the LUTs, flip flops, and LUT input multiplexers using parameters such as N, K, and I. 
Use the equations to determine the count for the logic block. Show your numerical results in a table and explain each equation in a few sentences.**

---

### EX4 Area Cost of Feedback
**How would the above equations be changed if the BLE outputs did not feed back into the input multiplexers? 
Calculate the modified transistor count for the logic block based on these modified equations.**

---

### EX5 Input Multiplexer Size
**How many transistors are needed to implement I logic cluster input multiplexers and associated programming bits as a function of I, Fc and W?**

---

### EX6 Embedded Memory Block Size
**Based on our discussion in class, how many transistors are needed to build a 2K×8 memory block without input or output flip flops? 
Based on your area analysis earlier (Q3), how many N = 6, I = 12 logic blocks (with feedback) are needed to fit the same transistor count. 
You can ignore the transistors in the address decoders for the memory block in your analysis.**

---

### EX7 FPGA and ASIC Tradeoffs
**Briefly describe some of the factors that lead to the area gap between FPGAs and ASICs for memory and multipliers. Is the inclusion of more multipliers and block memory bits per LUT in larger FPGAs likely to close the gap? Limit your answer to several paragraphs.**

**ANS** The main factor that leads to the area gap between FPGAs and ASICs is FPGAs require extra area to implement the additional circuit for intra BLE connection such as that between LUT and FF and inter BLE connection such as that for block interface and routing.

The inclusion of more hard blocks such as multipliers and block memory helps to close the gap because they are similar to ASIC implementation and both intra & inter element connections can be reduced.

---

### EX8 Interconnect Flip Flop
**Summarize the purpose and benefits of interconnect flip flops in several paragraphs. Is adding interconnect flip flops a good idea?**

---

### EX9 
**In your own words, summarize the results shown in the figure. What lesson do we learn from the results in this figure? Limit your answer to one paragraph.**

**ANS** The 20Kb block and no large memory block can match the efficiency of the 10Kb block with 144Kb memory. The single 40Kb architecture is less area efficient. That is the reason why Stratix V only provides a 20Kb embedded memory block.
