### 全局样式  
1. 所有元素的和模型都是*boder-box*类型的（`bootstrap-grid.scss`）
    ```
    html {
      box-sizing: border-box;
      -ms-overflow-style: scrollbar;
    }

    *,
    *::before,
    *::after {
      box-sizing: inherit;
    }
    ```