# Pipelined OTTER 

## TODO 
### 1. Get everything instantiated, and in place
   - PROG_CNTR (program counter)
   - REG_FILE (register file)
   - ALU (arithmetic logic unit)
   - IMM_GEN (immediate generator)
   - CFA_GEN (control flow address generator)
   - RF_MUX
   - ALU_SRC_A
   - ALU_SRC_B
   - DUAL_PORT_MEM_64kB (instruction and data mem)
   - Pipeline Registers (FD/DE/EM/MW) 'implemented as structs'
### 2. Fix the decoder and any signal routing if you need 
 - Do you want PC_SEL in there? (for now don't add the branch/jump sections of your decoder) 
 - PC_EN?
 - RF_EN / REG_WRITE?
### 3. Test with a basic hazard-safe script 
 - just do add/load/store but space it out with nops so there's no hazards (3 for load/store, 2 for reg/imm)
### 4. Add forwarding support (the control unit) 
 - forward RS1/RS2 as needed (i made an algorithm for doing this) 
### 5. Test that basic AUIPC/LUI/REG/IMM/STORE/LOAD works with hazards 
 - should be easy once you make the control unit just don't put nops betwene instructions 
### 6. Add jumps/branches (do them in decode, use a static predictor) 
 - 
### 7. Test that JAL/JALR/BRANCH works
### 8. Add a dynamic branch predictor 
### 9. Add control unit support for all the stalling/flushing
### 10. Test that everything works
### 11. Replace IMEM and DMEM with ICACHE and DCACHE (set-associative)
### 12. Make Memory Global (look into FPGA BRAM resources for sizing (its more than 64kB)
### 13. Add a top wrapper for the control unit, and add interrupts, have interupts interface with the control unit
