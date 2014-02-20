################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include src/subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
ELFSIZE += \
DDR_lowres.elf.size \

ELFCHECK += \
DDR_lowres.elf.elfcheck \


# All Target
all: DDR_lowres.elf secondary-outputs

# Tool invocations
DDR_lowres.elf: $(OBJS) ../src/lscript.ld $(USER_OBJS)
	@echo Building target: $@
	@echo Invoking: MicroBlaze gcc linker
	mb-gcc -Wl,--no-relax -Wl,-T -Wl,../src/lscript.ld -L../../standalone_bsp_0/microblaze_0/lib -mlittle-endian -mxl-barrel-shift -mxl-pattern-compare -mcpu=v8.40.a -mno-xl-soft-mul -o"DDR_lowres.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo Finished building target: $@
	@echo ' '

DDR_lowres.elf.size: DDR_lowres.elf
	@echo Invoking: MicroBlaze Print Size
	mb-size DDR_lowres.elf  |tee "DDR_lowres.elf.size"
	@echo Finished building: $@
	@echo ' '

DDR_lowres.elf.elfcheck: DDR_lowres.elf
	@echo Invoking: Xilinx ELF Check
	elfcheck DDR_lowres.elf -hw ../../hdmi_out_hw_platform/system.xml -pe microblaze_0  |tee "DDR_lowres.elf.elfcheck"
	@echo Finished building: $@
	@echo ' '

# Other Targets
clean:
	-$(RM) $(OBJS)$(C_DEPS)$(EXECUTABLES)$(ELFSIZE)$(ELFCHECK)$(S_UPPER_DEPS) DDR_lowres.elf
	-@echo ' '

secondary-outputs: $(ELFSIZE) $(ELFCHECK)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
