作业一:
走pa01的引脚,实现外接LED每隔250ms闪烁.
相关代码:

```c
  while (1)
  {

    /***********************
    这是使用hal_delay的点灯
    ***********************/
//		HAL_GPIO_WritePin(GPIOC,GPIO_PIN_13,GPIO_PIN_RESET);
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_1,GPIO_PIN_SET);
		HAL_Delay(250);
//		HAL_GPIO_WritePin(GPIOC,GPIO_PIN_13,GPIO_PIN_SET);
		HAL_GPIO_WritePin(GPIOA,GPIO_PIN_1,GPIO_PIN_RESET);
        HAL_Delay(250);
  }



    /* USER CODE END WHILE */

    /* USER CODE BEGIN 3 */
```
作业2:使用tim2定时器完成定时中断实现led闪烁.引脚选择PA12.
相关代码:
```c
  HAL_TIM_Base_Start_IT(&htim2);  //启用tim2的定时器

//......
void HAL_TIM_PeriodElapsedCallback(TIM_HandleTypeDef *htim)
{
  if (htim ->Instance == TIM2) {
    HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_12);
  }
}
```


