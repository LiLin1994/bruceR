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

ע��R��һ�㶼������������R�����ڰ�װʱ�����Զ���װ����R����Ȼ���ٰ�װ����`bruceR`������`tidyverse`��`ggstatsplot`��10+��R����[�鿴�����б�](https://github.com/psychbruce/bruceR/blob/master/DESCRIPTION)������`tidyverse`��`ggstatsplot`��������һ��200+����������R�����������ֱ�Ӱ�װ`bruceR`����ᷢ���зǳ����R����Ҫ��װ������һ����װĳЩ������ʱ�������������װ�װ����Ļ���R������`rlang`��`gsl`��`Rcpp`�ȣ�����ǰ����������Ҫ��������һ�飬������Ȼ�п��ܱ����˷��˴���ʱ�䡣������Ϊ��`devtools::install_github()`�����ڰ�װGitHub�ϵ�R��ʱ��һ��ȱ�ݣ�������װ����������R��ʧ��ʱ���ú����޷��ܺõش���װʧ�ܵ�״�������᷵��һ��û���κ���Ϣ�����ı�����Ϣ��`Error: Failed to install 'bruceR' from GitHub`������ˣ�ǿ�ҽ����û��ȸ��������е�R�����е�R������Ҫ�ֶ�ж����װ����Bug #05������������װ`bruceR`���⽫�����ʡ����ʱ�䣡


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
Check your network connections, or see https://ask.csdn.net/questions/713186.

��װǰ��ȷ�����Ӻ������硣������ǲ��У����Կ�������������ӡ�


## Bug #03:
```
WARNING: Rtools is required to build R packages, but is not currently installed.

Please download and install Rtools 3.5 from http://cran.r-project.org/bin/windows/Rtools/

Error in parse_repo_spec(repo) : Invalid git repo specification: 'bruceR'
```
### Solution:
Download and install [Rtools](http://cran.r-project.org/bin/windows/Rtools/).

Rtools����һ��R��������һ������Ĺ��ߣ���ð�װ��


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
Use the RStudio menu bar [**`Packages -> Update`**](https://shimo.im/docs/YWwKvcRgqWRdh3HR) or the code `update.packages(ask=F)` to update all the other packages before you install `bruceR`.

Sometimes you have to first use `remove.packages()` to uninstall the old packages (e.g., `rlang`, `gsl`, `Rcpp`) and then use `install.packages()` to reinstall them. Sometimes you also have to restart RStudio and try these again.

���Bug���û�������ġ��ܶ�������ڸ��µ�ʱ�����׳��ָ���ʧ�ܵ������Ŀǰ����`rlang`��`gsl`��`Rcpp`�������װ�װʧ��/����ʧ�ܣ�`bruceR`���߱�ʾͬ�������Σ�����ʱ���볢���ֶ�ж�ء���װ��Щ����R��������ʹ�ô��룬Ҳ����ʹ��RStudio����ϵ�**`Packages`**���������ռ������������**�ֶ�ж����װ**��**�ֶ�ж����װ**��**�ֶ�ж����װ**��

