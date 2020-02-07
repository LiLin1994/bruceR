# Installation Bugs and Solutions

All the bugs DO NOT have relation with the `bruceR` package *per se*.

���ڰ�װ��������������������**������**`bruceR`����������⣡

����йأ�Ҳ����Ϊ`bruceR`��Ҫ��װ�ܶ�������R�����ڰ�װ��ЩR����ʱ�����

**�󲿷��û�����������װ**`bruceR`�������װ�������������⣬����ϸ�Ķ����ĵ���������6�ֳ���bug�Ľ��������

**ǿ�ҽ���**�Ȱ�װ��`tidyverse`��`ggstatsplot`�����������Ҹ���һ���Ѱ�װ������R����Ȼ���ٰ�װ`bruceR`��
```r
install.packages("devtools")
install.packages("tidyverse")
install.packages("ggstatsplot")
update.packages(ask=F)

devtools::install_github("psychbruce/bruceR")
```

ע��R��һ�㶼������������R�����ڰ�װʱ�����Զ���װ����R����Ȼ���ٰ�װ����`bruceR`������`tidyverse`��`ggstatsplot`��10+��R����[�鿴�����б�](https://github.com/psychbruce/bruceR/blob/master/DESCRIPTION)������`tidyverse`��`ggstatsplot`��������һ��200+����������R�����������ֱ�Ӱ�װ`bruceR`����ᷢ�����ϰٸ�R����Ҫ��װ������һ����װ�������װ�װ����Ļ���R������`rlang`��`gsl`��`Rcpp`�ȣ�����ǰ����������Ҫ��������һ�飬������Ȼ�п��ܱ����˷��˴���ʱ�䡣�������������Ҫ����Ϊ��1����Щ����R���İ�װ������̿��ܱȽϸ��ӣ����׳���δ֪��bug��2��`devtools::install_github()`�����ڰ�װGitHub�ϵ�R��ʱ��һ��ȱ�ݣ����޷��ܺõش���װ����R��ʧ�ܵ�״�������᷵��һ��û���κ���Ϣ�����ı�����Ϣ��`Error: Failed to install 'bruceR' from GitHub`����ʹ�û���Ϊ��`bruceR`��������⡣��ˣ�ǿ�ҽ����û��ȸ��������е�R�����е�R������Ҫ�ֶ�ж����װ����[Bug #03](https://github.com/psychbruce/bruceR/blob/master/Installation%20Bugs%20and%20Solutions.md#bug-03)������������װ`bruceR`���⽫�����ʡʱ�䣡


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

��װǰ��ȷ�����Ӻ������硣������ǲ��У����Կ�������������ӡ����⣬������ٽ�������װ���̻�ǳ��������Ͼ���200+��������R����Ҫ�������ذ�װ������ǿ�ҽ��������ٽϿ�Ļ����°�װ`bruceR`��


## Bug #03:
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

���Bug�����ĳЩ����R���ڸ���ʱ�����׳��ָ���ʧ�ܵ������Ŀǰ���֣�`rlang`��`gsl`��`Rcpp`�������׳��ָ���ʧ�ܣ�`bruceR`���߱�ʾ�����Σ�������ԭ��һ������Щ�����°汾��**�ոշ���**��ʱ����Ҫͨ�����루compilation���ķ�ʽ����װ���£�����R����������װ���̲�ͬ�������Ӹ���ʱҲ�����׳���

��**�ֶ�ж����װ**��ЩR�����������`rlang`����������ô����
```r
## ��1�����ֶ�ж��
remove.packages("rlang")

## ��2��������R����
# ��RStudio�������ʹ�ÿ�ݼ�`Ctrl+Shift+F10`
# Ҳ����������˵��������`Session -> Restart R`

## ��3�����ֶ���װ
install.packages("rlang")
```


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

Tips: Use the `installr` package to update R and copy R packages from the old folder to the new one.
```r
install.packages("installr")
library(installr)
updateR()
copy.packages.between.libraries(ask=TRUE)
```

��R���Ա���İ汾�и���ʱ��ĳЩR��Ҳ��ͬ�����²�����Ҫ�������°汾��R������������������ЩR����������Ȱ�R�������������°汾�������ṩ��һ����������R���Ե�С��ʿ�����Է��������¹��̡�


## Bug #05:
```
WARNING: Rtools is required to build R packages, but is not currently installed.

Please download and install Rtools 3.5 from http://cran.r-project.org/bin/windows/Rtools/

Error in parse_repo_spec(repo) : Invalid git repo specification: 'bruceR'
```
### Solution:
Download and install [Rtools](http://cran.r-project.org/bin/windows/Rtools/).

Rtools����һ��R��������һ������Ĺ��ߣ���ð�װ����������װ�ƺ�Ҳû��̫������⡣


## Bug #06:
```
Skipping install of 'bruceR' from a github remote, the SHA1 has not changed since last install.
Use `force = TRUE` to force installation
```
### Solution:
Congratulations! You have already installed the latest `bruceR`. No need to reinstall or update it.

����ϸ�Ķ�������Ϣ���ף�����ʾ��GitHub�ϵİ汾�����Ѿ���װ���İ汾֮��û�б仯��**���Ѿ��ɹ���װ�����°汾**��

��Ȼ���������**��������**��������`install_github()`���������һ������`force = TRUE`��ǿ����װһ�飬��ô����Ŀ���Ǵ�ʱ�䡣

