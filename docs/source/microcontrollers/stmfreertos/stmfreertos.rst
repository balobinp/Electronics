Quick start STM32 FreeRTOS
==========================

In this example I used **STM32F401CCU6** and **STM32CubeIDE (Version: 1.17.0)**

#. Create Project

    File -> New -> STM32 Project

#. Select MCU

    .. figure:: images/stmfreertos_001.png
       :align: center

#. Setup Project

    Specify the location

    .. figure:: images/stmfreertos_002.png
       :width: 350px
       :align: center

#. Setup PC13 as GPIO_Output

    PC13 is connected to LED on the board

#. Setup RCC Low Speed Clock (LSE)

    .. figure:: images/stmfreertos_003.png
       :align: center

#. Setup SYS Timebase source

    "При использовании FreeRTOS, в качестве базового таймера для HAL рекомендуется выбрать
    не SysTick (стоит по умолчанию), а другой."

    -- `STM32CubeMx. Быстрый старт с FreeRTOS для STM32`_

    .. figure:: images/stmfreertos_004.png
       :align: center

#. Select FREERTOS with CMSIS_V2

    .. figure:: images/stmfreertos_005.png
       :align: center

#. Create Tasks

    .. figure:: images/stmfreertos_006.png
       :align: center

#. Enable USE_NEWLIB_REENTRANT

    .. figure:: images/stmfreertos_007.png
       :align: center

#. Save project and Generate Code

    File -> Save

#. Include some code into task functions

    .. code-block:: c++

        void StartTask01(void *argument)
        {
          /* USER CODE BEGIN StartTask01 */
          /* Infinite loop */
          for(;;)
          {
            HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
            osDelay(500);
          }
          /* USER CODE END StartTask01 */
        }

#. Save changes

    File -> Save

#. Build and Run Project

    .. figure:: images/stmfreertos_008.png
       :align: center

References
----------

#. `STM32CubeMx. Быстрый старт с FreeRTOS для STM32`_
#. `Лекция-практикум "SM32CubeIDE + FreeRTOS`_
#. `STM32 - программирование для начинающих. Пошагово. CubeMX CubeIDE`_

.. _STM32CubeMx. Быстрый старт с FreeRTOS для STM32: https://microtechnics.ru/stm32cubemx-bystryj-start-s-freertos-dlya-stm32/
.. _Лекция-практикум "SM32CubeIDE + FreeRTOS: https://www.youtube.com/watch?v=JKkyF53AAM4
.. _STM32 - программирование для начинающих. Пошагово. CubeMX CubeIDE: https://www.youtube.com/watch?app=desktop&v=fxAsY0S2Xa0
