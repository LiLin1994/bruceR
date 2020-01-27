# Installation Bugs and Solutions

All the bugs DO NOT have relation with the `bruceR` package *per se*.

���ڰ�װ��������������������**������**`bruceR`����������⣡

**ǿ�ҽ���**�Ȱ�װ��`tidyverse`��`ggstatsplot`�����������Ҹ���һ���Ѱ�װ������R����Ȼ���ٰ�װ`bruceR`��
```r
install.packages("devtools")
install.packages("tidyverse")
install.packages("ggstatsplot")
update.packages(ask=F)

devtools::install_github("psychbruce/bruceR")
```


## Bug #01:
```
> install.packages("bruceR")
Warning in install.packages :
  package ��bruceR�� is not available (for R version 3.6.1)
```
### Solution:
Use `devtools::install_github("psychbruce/bruceR")`.
DO NOT use `install.packages("bruceR")`.

����`bruceR`��û�з�����CRAN�����ϣ�������ͨ��`devtools`������װ��������ֱ��ʹ��`install.packages()`������


## Bug #02:
```
> devtools::install_github("psychbruce/bruceR")
Downloading GitHub repo psychbruce/bruceR@master
Error in utils::download.file(url, path, method = method, quiet = quiet,  : 
  cannot open URL 'https://api.github.com/repos/psychbruce/bruceR/tarball/master'
```
### Solution:
Check your network connections.

Or see https://ask.csdn.net/questions/713186


## Bug #03:
```
WARNING: Rtools is required to build R packages, but is not currently installed.

Please download and install Rtools 3.5 from http://cran.r-project.org/bin/windows/Rtools/

Error in parse_repo_spec(repo) : Invalid git repo specification: 'bruceR'
```
### Solution:
Download and install [Rtools](http://cran.r-project.org/bin/windows/Rtools/).


## Bug #04:
```
* installing *source* package 'bruceR' ...
** using staged installation
** R
** data
*** moving datasets to lazyload DB
** byte-compile and prepare package for lazy loading
����: (�ɾ���ת����)�̼���'rio'����R�汾3.6.1 �������
ִֹͣ��
ERROR: lazy loading failed for package 'bruceR'
Error: Failed to install 'bruceR' from GitHub:
  (converted from warning) installation of package ��bruceR�� had non-zero exit status
```
or
```
* installing *source* package 'bruceR' ...
** using staged installation
** R
** data
*** moving datasets to lazyload DB
** byte-compile and prepare package for lazy loading
����: (�ɾ���ת����)�̼���'dplyr'����R�汾3.6.1 �������
ִֹͣ��
ERROR: lazy loading failed for package 'bruceR'
Error: Failed to install 'bruceR' from GitHub:
  (converted from warning) installation of package ��bruceR�� had non-zero exit status
```
### Solution:
Update R to the [latest version](https://cran.r-project.org/), because the latest versions of some packages (e.g., `rio`, `dplyr`) also require the latest version of R.

Tips: You can use the `installr` package to copy all your installed packages from the old folder to the new one.
```r
install.packages("installr")
library(installr)
copy.packages.between.libraries(ask=TRUE)
```


## Bug #05:
```
Error: Failed to install 'bruceR' from GitHub:
  (converted from warning) installation of package ��rlang�� had non-zero exit status
```
or
```
Error: Failed to install 'bruceR' from GitHub:
  (converted from warning) cannot remove prior installation of package ��Rcpp��
```
### Solution:
Use the menu bar [**`Packages -> Update`**](https://shimo.im/docs/YWwKvcRgqWRdh3HR) (on the panes, not on the top) or the code `update.packages(ask=F)` to update all the other packages before you install `bruceR`.


## Bug #N:
There might be some other bugs not listed above.
### Solution:
Read the warning messages. Follow the instruction. Search the Internet. Get the answer.

