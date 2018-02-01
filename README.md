# SoapNewCov
<b>SoapNewCov: A efficient software tools to Calculate site depth of genome based soap List</b>

  </br> chr/genome mean Depth and Coverage also will be given 
  </br> Depth-GC Dis plot also can be given

1) Install
------------

  </br>Just  [make]  or [sh  make.sh ]  to compile this software.
  </br>the final software can be found in the Dir [bin/SoapNewCov]

 For <b>linux /Unix </b>
<pre>
        tar -zxvf  SoapNewCov-XXX.tar.gz
        cd SoapNewCov-XXX;                             # if Link do not work ,Try <b>re-install</b>  two  library
        cd src;                                        #【zlib and gzstream】 and copy them to the  library Dir
        make ; make clean                              # SoapNewCov-XX/src/include/zlib 
        ../bin/SoapNewCov                              # SoapNewCov-XX/src/include/gzstream
</pre>
</br>

For <b>macOS </b>
<pre>
#step1 :Should must <b>re-install</b>  two  library 【zlib and gzstream htslib】
              see  [zlib and gzstream] website 
#step2  :  # Copy these two library into Dirs 
              cp libz.a libz.so*  SoapNewCov-XX/src/include/zlib
              cp libgzstream.a  SoapNewCov-XX/src/include/gzstream
#step3  : 
              sh make.sh # or [make && make clean]
</pre>

2) Example
------------
* 1) Calculate soap files
```
#To Calculate soap Depth with all mapping Read ,add Pare [-MinHit 10000 ]
 	./bin/SoapNewCov  -List  soap.list  -OutPut  out.depth.fa.gz   -Dict  Ref.fa -MinHit  10000
#To give out the genome Coverage,MeanDepth & Depth Dis , add Pare [ -Stat ]
 	./bin/SoapNewCov  -List  soap.list  -OutPut  out.depth.fa.gz  -Stat  -Dict Ref.dict
 	./bin/SoapNewCov  -List  soap.list  -OutPut  out.depth.fa.gz  -Stat  -Dict Ref.fa.gz
```

* 2) Calculate & Plot Depth-GC Dis Figure
```

# First Out Put the Depth-GC wig info with [ -OutWig ]
 	./bin/SoapNewCov  -List soap.list   -OutPut outFix   -Ref Ref.fa  -Stat -OutWig
# Second To Plot the Figure
# Must PreInstall R with library ggplot2,gridExtra,ggExtra

 	perl  bin/GC_Depth_Plot.pl  outFix.DepthGC.wig.gz  MaxDepth  OutFig

```

3) Introduction
------------


* <b> Parameter description</b>

```php

    ./bin/SoapNewCov

        Usage: SoapNewCov  -List  <soap.list> -Dict <Ref.fa.gz>  -OutPut  <out.depth>

                -List      <str>     Input soap File List
                -Dict      <str>     Input Ref.fa or Ref.dict
                -OutPut    <str>     OutPut Depth info Fa file

                -Stat                Stat Coverage,MeanDepth & Depth Dis info
                -OutWig              Out Depth-GC wig info
                -Windows   <int>     Windows size for Depth-GC wig[10000]

                -MinHit    <int>     Filter the read bigger Mapping Hit [10]

                -help                Show this help [hewm2008 v1.10]


```


4) Results
------------
Introduction
Result is the same the these two softwares

* [SOAPcoverage](https://github.com/aquaskyline/SOAPcoverage)
* [Bamcoverage](https://github.com/BGI-shenzhen/BamCoverage)


5）Discussing
------------
- email: hewm2008@gmail.com / hewm2008@qq.com  
- join the<b><i> QQ Group : 125293663</b></i>



######################swimming in the sky and flying in the sea ########################### ##


