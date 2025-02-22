# paper_quality_plot.matlab

All materials are from [Urban Robotics Lab.](http://urobot.kaist.ac.kr/) @KAIST

Original author: Hyungtae Lim (shapelim@kaist.ac.kr)

Advisers: Giseop Kim (paulgkim@kaist.ac.kr), Byeongho YU (bhyu@kaist.ac.kr) 

---

# Introduction

This repositoy contains 

* how to use linespecer for beautiful matlab graph

https://kr.mathworks.com/matlabcentral/fileexchange/42673-beautiful-and-distinguishable-line-colors-colormap

* how to set legend interpreter as latex

* the method for removing unnecessary white space

* the method for changing the default tick fonts to the latex version

* tilelayout (Only applicable on latest version Matlab)

* thousand seperator 

All outputs are located in `imgs` folder.

---
# Must be added for the Paper-quality Figures

:point_right: Add `set(gca,'LooseInset', max(get(gca,'TightInset'), 0.02))` below the figure declaration line.

:point_right: Add `set(groot, 'defaultAxesTickLabelInterpreter','latex');` below the figure declaration line.

:point_right: Add `ytickformat('%,4.4g');` after **plot( ) command** (optional).

The template is available on [here](template.m)

---

# When it comesto saving figures in eps...

I realized that some matlab figures (e.g., bar plot, tiles) are not available to save the format in `.eps`

So, we must use below command as follows:

```
% gcf: figure object
print(gcf, "SET_YOUR_FINENAME.png",'-dpng','-r200'); 
```

---

# Description

## [Plot cdf](plot_cdf.m)

Note that the effect of the linespecer which is illustrated as: 

### Before using linespecer

![cdf_alpha_before](./imgs/total_cdf_alpha_before.png)

![cdf_beta_before](./imgs/total_cdf_beta_before.png)

### After using linespecer

![cdf_alpha](./imgs/total_cdf_alpha.png)

![cdf_beta](./imgs/total_cdf_beta.png)

**linespecer is more beautiful!** It allows the figures to be more clean and improves readability.

So, I strongly recommend utilizing `linespecer`!

Please refer to the line 7 to 9 and 124 to 133 in `plot_cdf.m`  :) 

## [Plot pdf](plot_pdf.m)

![pdf](./imgs/erasor_pdf_diff_percentage.png)

Note that the built-in pdf function of matlab does not work sometimes. My method is better!

## [Plot 3D colormap trajectory](plot_trajectory.m)

![pdf](./imgs/Navigation_trajectory.png)

The trajectory is colored with respect to sequence length.

However, if the trajectory is too long, then it may be not applicable.

## [Line graph1](plot_linegraph1.m)

![caros_tile_output](imgs/caros_tile_output.png)

## [Line graph2](plot_linegraph2.m)

![line1](./imgs/erasor_ground_percentage.png)

![line2](./imgs/erasor_ground_rejection.png)

## [Plot boxplots](plot_boxplots.m)

![boxplot1](./imgs/boxplot1.png)

## [Plot barplot](plot_barplot.m)

Only available on **R2020a**.

![barplot](./imgs/ground_bar_plot_v2.png)

## [Tilelayout](plot_tilelayout.m)

Only available on **R2020a**.

![tilelayout](./imgs/final_tilelayout.png)
