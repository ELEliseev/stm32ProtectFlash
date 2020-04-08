# stm32ProtectFlash
#define RELEASE

* #ifdef RELEASE
* #warning "Protection is ON. Debug is OFF"
* 	    FLASH_OBProgramInitTypeDef obConfig;
* 	    HAL_FLASHEx_OBGetConfig(&obConfig);*
* 	    if (obConfig.RDPLevel == OB_RDP_LEVEL_0) {
* 	        // this is first time we run mcu after flashing firmware
* 	        obConfig.RDPLevel = OB_RDP_LEVEL_1;
*          HAL_FLASH_Unlock();
* 	        HAL_FLASH_OB_Unlock();
* 	        HAL_FLASHEx_OBProgram(&obConfig);
* 	        HAL_FLASH_OB_Launch();
* 	    }
* #endif
