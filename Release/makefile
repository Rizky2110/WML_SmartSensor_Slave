################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include myUART/subdir.mk
-include mySmartSensor/subdir.mk
-include mySPI/subdir.mk
-include myADC/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
SLAVE_SMART_Sensor.lss \

FLASH_IMAGE += \
SLAVE_SMART_Sensor.hex \

EEPROM_IMAGE += \
SLAVE_SMART_Sensor.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: SLAVE_SMART_Sensor.elf secondary-outputs

# Tool invocations
SLAVE_SMART_Sensor.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,SLAVE_SMART_Sensor.map -mmcu=atmega2560 -o "SLAVE_SMART_Sensor.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

SLAVE_SMART_Sensor.lss: SLAVE_SMART_Sensor.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S SLAVE_SMART_Sensor.elf  >"SLAVE_SMART_Sensor.lss"
	@echo 'Finished building: $@'
	@echo ' '

SLAVE_SMART_Sensor.hex: SLAVE_SMART_Sensor.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex SLAVE_SMART_Sensor.elf  "SLAVE_SMART_Sensor.hex"
	@echo 'Finished building: $@'
	@echo ' '

SLAVE_SMART_Sensor.eep: SLAVE_SMART_Sensor.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex SLAVE_SMART_Sensor.elf  "SLAVE_SMART_Sensor.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: SLAVE_SMART_Sensor.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega2560 SLAVE_SMART_Sensor.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) SLAVE_SMART_Sensor.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
