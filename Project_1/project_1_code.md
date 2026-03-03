          . clear 

          . cd "C:\Users\darsh\OneDrive\Documents\PBHLT 7101\Project 1"
          C:\Users\darsh\OneDrive\Documents\PBHLT 7101\Project 1

          . use "ansur2allV2.dta"

          . save project_data_v0, replace
          file project_data_v0.dta saved

          . ds, has(type numeric)
          subjectnum~e  age           heightin      span          kneeheight~a  functional~h  trochanter~t  waistcircu~e  bicristalb~h  hipbreadth~g  date
          dodrace       weightlbs     thumbtipre~h  footlength    waistheigh~n  cervicaleh~t  stature       chestcircu~e  hipbreadth    weightkg

          . foreach var of varlist `r(varlist)'{
          .         replace `var' = .a if `var' == -77
          .         replace `var' = .b if `var' == -88
          .         replace `var' = .c if `var' == -99
          . }
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (1 real change made, 1 to missing)
          (0 real changes made)
          (0 real changes made)
          (0 real changes made)

          . set seed 27

          . gen u_id = sum(runiformint(1,5))

          . save project_data_v1, replace 
          file project_data_v1.dta saved

          . ds, has(type numeric)
          subjectnum~e  age           heightin      span          kneeheight~a  functional~h  trochanter~t  waistcircu~e  bicristalb~h  hipbreadth~g  date
          dodrace       weightlbs     thumbtipre~h  footlength    waistheigh~n  cervicaleh~t  stature       chestcircu~e  hipbreadth    weightkg      u_id

          . foreach var of varlist `r(varlist)'{
          .         summ `var', detail
          . }

                               subjectnumericrace
          -------------------------------------------------------------
                Percentiles      Smallest
           1%            1              1
           5%            1              1
          10%            1              1       Obs               7,031
          25%            1              1       Sum of wgt.       7,031

          50%            1                      Mean           16.17963
                                  Largest       Std. dev.      511.9852
          75%            2           2518
          90%           21           2518       Variance       262128.9
          95%           38           4251       Skewness       80.56994
          99%          218          42351       Kurtosis       6651.658

                                     dodrace
          -------------------------------------------------------------
                Percentiles      Smallest
           1%            1              1
           5%            1              1
          10%            1              1       Obs               7,031
          25%            1              1       Sum of wgt.       7,031

          50%            1                      Mean           1.625516
                                  Largest       Std. dev.      1.016156
          75%            2              8
          90%            3              8       Variance       1.032572
          95%            4              8       Skewness       2.132043
          99%            6              8       Kurtosis       8.714612

                                       age
          -------------------------------------------------------------
                Percentiles      Smallest
           1%           18             17
           5%           19             17
          10%           20             18       Obs               7,031
          25%           23             18       Sum of wgt.       7,031

          50%           28                      Mean           30.06756
                                  Largest       Std. dev.      8.805637
          75%           37             58
          90%           43             58       Variance       77.53925
          95%           47             58       Skewness       .7301577
          99%           53             58       Kurtosis       2.635243

                                    weightlbs
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          110              0
           5%          125              0
          10%          134             86       Obs               7,031
          25%          150             88       Sum of wgt.       7,031

          50%          175                      Mean           175.4537
                                  Largest       Std. dev.       33.6008
          75%          197            310
          90%          220            310       Variance       1129.014
          95%          235            315       Skewness       .3334848
          99%          260            321       Kurtosis       3.206623

                                    heightin
          -------------------------------------------------------------
                Percentiles      Smallest
           1%           60             56
           5%           62             56
          10%           63             56       Obs               7,031
          25%           66             57       Sum of wgt.       7,031

          50%           69                      Mean           68.34632
                                  Largest       Std. dev.       3.85409
          75%           71             86
          90%           73             87       Variance       14.85401
          95%           74             94       Skewness       .0047706
          99%           77             94       Kurtosis        3.34104

                                  thumbtipreach
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          669            602
           5%          704            607
          10%          721            614       Obs               7,030
          25%          756            625       Sum of wgt.       7,030

          50%          795                      Mean             802.76
                                  Largest       Std. dev.       282.591
          75%          829           8280
          90%          860           8440       Variance       79857.66
          95%          879           9140       Skewness       25.33348
          99%          916           9340       Kurtosis       671.9217

                                      span
          -------------------------------------------------------------
                Percentiles      Smallest
           1%         1515           1323
           5%         1580           1408
          10%         1619           1414       Obs               7,030
          25%         1691           1424       Sum of wgt.       7,030

          50%         1776                      Mean           1767.858
                                  Largest       Std. dev.       110.484
          75%         1845           2107
          90%         1904           2109       Variance       12206.72
          95%         1942           2111       Skewness      -.1248988
          99%         2010           2121       Kurtosis       2.789132

                                   footlength
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          224            198
           5%          234            210
          10%          239            212       Obs               7,030
          25%          252            213       Sum of wgt.       7,030

          50%          265                      Mean           263.4276
                                  Largest       Std. dev.      17.31881
          75%          276            313
          90%          285            316       Variance       299.9412
          95%          290            318       Skewness      -.1778448
          99%          300            323       Kurtosis       2.667612

                              kneeheightmidpatella
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          401            346
           5%          422            350
          10%          433            356       Obs               7,030
          25%          452            360       Sum of wgt.       7,030

          50%          476                      Mean            475.322
                                  Largest       Std. dev.      32.88627
          75%          497            590
          90%          517            594       Variance       1081.507
          95%          529            596       Skewness       .0365574
          99%          553            612       Kurtosis       2.965328

                              waistheightomphalion
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          889            805
           5%          929            805
          10%          951            808       Obs               7,030
          25%          989            819       Sum of wgt.       7,030

          50%         1035                      Mean           1032.601
                                  Largest       Std. dev.      62.53999
          75%         1077           1225
          90%         1112           1225       Variance        3911.25
          95%         1133           1242       Skewness      -.0449844
          99%         1179           1245       Kurtosis        2.87727

                               functionalleglength
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          950            835
           5%          990            846
          10%         1015            868       Obs               7,030
          25%         1057            884       Sum of wgt.       7,030

          50%         1107                      Mean           1104.308
                                  Largest       Std. dev.      68.07844
          75%         1150           1308
          90%         1190           1312       Variance       4634.674
          95%         1214           1316       Skewness      -.0743199
          99%         1259           1316       Kurtosis       2.851656

                                 cervicaleheight
          -------------------------------------------------------------
                Percentiles      Smallest
           1%         1290           1184
           5%         1336           1208
          10%         1365           1209       Obs               7,030
          25%         1422           1218       Sum of wgt.       7,030

          50%         1487                      Mean           1479.785
                                  Largest       Std. dev.      84.05506
          75%         1539           1717
          90%         1584           1718       Variance       7065.254
          95%         1609           1718       Skewness      -.1566652
          99%         1661           1738       Kurtosis       2.683822

                               trochanterionheight
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          763            660
           5%          796            677
          10%          815            696       Obs               7,030
          25%          846            698       Sum of wgt.       7,030

          50%          882                      Mean            882.766
                                  Largest       Std. dev.      53.99414
          75%          918           1081
          90%          952           1083       Variance       2915.367
          95%          974           1090       Skewness       .1362148
          99%         1016           1095       Kurtosis       3.108292

                                     stature
          -------------------------------------------------------------
                Percentiles      Smallest
           1%         1512           1409
           5%         1564           1435
          10%         1595           1439       Obs               7,030
          25%         1654           1442       Sum of wgt.       7,030

          50%         1722                      Mean           1716.592
                                  Largest       Std. dev.      89.66425
          75%         1780           1972
          90%       1828.5           1979       Variance       8039.679
          95%         1856           1980       Skewness      -.1268653
          99%         1919           1993       Kurtosis       2.712324

                               waistcircumference
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          694            611
           5%          744            615
          10%          774            620       Obs               7,030
          25%          831            624       Sum of wgt.       7,030

          50%          911                      Mean           916.8802
                                  Largest       Std. dev.      113.9418
          75%          996           1356
          90%         1068           1358       Variance       12982.73
          95%         1112           1358       Skewness        .317412
          99%         1194           1379       Kurtosis       2.892807

                               chestcircumference
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          812            695
           5%          862            726
          10%          895            737       Obs               7,030
          25%          952            757       Sum of wgt.       7,030

          50%         1024                      Mean           1024.875
                                  Largest       Std. dev.       100.192
          75%         1094           1358
          90%         1154           1372       Variance       10038.43
          95%         1192           1374       Skewness       .1015084
          99%         1258           1469       Kurtosis       2.749927

                                bicristalbreadth
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          231            197
           5%          244            201
          10%          251            205       Obs               7,030
          25%          262            209       Sum of wgt.       7,030

          50%          274                      Mean           274.5391
                                  Largest       Std. dev.      19.07554
          75%          287            343
          90%          299            347       Variance        363.876
          95%          305            356       Skewness       .1151802
          99%          323            362       Kurtosis       3.247883

                                   hipbreadth
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          294            264
           5%          309            264
          10%          318            264       Obs               7,030
          25%          332            268       Sum of wgt.       7,030

          50%          347                      Mean             348.41
                                  Largest       Std. dev.      24.98933
          75%          364            452
          90%          381            457       Variance       624.4667
          95%          392            470       Skewness       .3531106
          99%          415            473       Kurtosis       3.530241

                                hipbreadthsitting
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          318            280
           5%          337            280
          10%          346            288       Obs               7,030
          25%          364            291       Sum of wgt.       7,030

          50%          384                      Mean           385.8919
                                  Largest       Std. dev.      32.03045
          75%          406            518
          90%          427            533       Variance        1025.95
          95%          441            538       Skewness        .392411
          99%          472            541       Kurtosis       3.436108

                                    weightkg
          -------------------------------------------------------------
                Percentiles      Smallest
           1%         49.7           35.8
           5%         56.5           39.3
          10%         60.6           39.3       Obs               7,030
          25%         68.5             40       Sum of wgt.       7,030

          50%         79.1                      Mean           84.12404
                                  Largest       Std. dev.      58.07441
          75%         90.2            979
          90%          101           1045       Variance       3372.637
          95%        108.4           1083       Skewness       12.38843
          99%        126.8           1099       Kurtosis       170.7107

                                      date
          -------------------------------------------------------------
                Percentiles      Smallest
           1%        18547          18539
           5%        18561          18539
          10%        18597          18539       Obs               6,068
          25%        18701          18540       Sum of wgt.       6,068

          50%        18823                      Mean            18836.9
                                  Largest       Std. dev.      170.0848
          75%        19011          19088
          90%        19060          19088       Variance       28928.84
          95%        19073          19088       Skewness      -.0940339
          99%        19087          19088       Kurtosis       1.697461

                                      u_id
          -------------------------------------------------------------
                Percentiles      Smallest
           1%          205              3
           5%         1072              6
          10%         2126             10       Obs               7,031
          25%         5261             15       Sum of wgt.       7,031

          50%        10576                      Mean            10553.4
                                  Largest       Std. dev.      6086.969
          75%        15781          21095
          90%        18986          21100       Variance       3.71e+07
          95%        20047          21101       Skewness      -.0052851
          99%        20888          21104       Kurtosis       1.802299

          . gen is_suspicious = 0

          . gen is_adult = 1

          . replace is_adult = 0 if age < 18
          (2 real changes made)

          . replace age = .d if age < 18 
          (2 real changes made, 2 to missing)

          . replace is_suspicious = 1 if age == .d
          (2 real changes made)

          . replace dodrace = .d if dodrace == 7
          (18 real changes made, 18 to missing)

          . replace is_suspicious = 1 if dodrace == .d
          (18 real changes made)

          . replace weightlbs = .d if weightlbs == 0 
          (2 real changes made, 2 to missing)

          . replace is_suspicious = 1 if weightlbs == .d
          (2 real changes made)

          . replace thumbtipreach = .d if thumbtipreach > 5000
          (11 real changes made, 11 to missing)

          . replace is_suspicious = 1 if thumbtipreach > 5000
          (11 real changes made)

          . replace weightkg = .d if weightkg > 500 
          (40 real changes made, 40 to missing)

          . replace is_suspicious = 1 if weightkg == .d
          (38 real changes made)

          . ds, has(type string)
          ethnicity     gender        component     branch        writingpre~e  installation  test_date     strdate

          . foreach var of varlist `r(varlist)'{
          .         tab `var', missing
          . }

                   ethnicity |      Freq.     Percent        Cum.
          -------------------+-----------------------------------
                             |      5,380       76.52       76.52
               Aboriginal Gu |          2        0.03       76.55
          Algonquin Navajo P |          2        0.03       76.58
                      Apache |          3        0.04       76.62
               Apache Blackf |          2        0.03       76.65
          Apache Blackfoot C |          1        0.01       76.66
               Apache Cherok |          2        0.03       76.69
             Apache Cherokee |          4        0.06       76.75
                Apache Kiowa |          1        0.01       76.76
               Apache Mexica |          1        0.01       76.77
               Arab or Middl |         15        0.21       76.99
          Arab or Middle Eas |         12        0.17       77.16
                   Argentine |          2        0.03       77.19
               Argentine Bra |          1        0.01       77.20
               Argentine Mex |          2        0.03       77.23
                    Armenian |          1        0.01       77.24
                     Azorean |          2        0.03       77.27
               Aztec Mexican |          1        0.01       77.29
                    Belizean |          3        0.04       77.33
          Belizean Dominican |          2        0.03       77.36
                   Blackfoot |          7        0.10       77.46
               Blackfoot Car |          1        0.01       77.47
               Blackfoot Che |          5        0.07       77.54
          Blackfoot Cherokee |          4        0.06       77.60
               Blackfoot Cho |          1        0.01       77.61
               Blackfoot Mex |          1        0.01       77.63
          Blackfoot Puerto R |          1        0.01       77.64
               Blackfoot Sha |          1        0.01       77.66
                    Bolivian |          2        0.03       77.68
                   Brazilian |          2        0.03       77.71
                     Burmese |          3        0.04       77.76
          Caddo Cheyenne Mex |          1        0.01       77.77
                   Cambodian |          5        0.07       77.84
               Cambodian Vie |          1        0.01       77.86
                Cape Verdean |          1        0.01       77.87
               Caribbean Isl |         89        1.27       79.14
          Caribbean Islander |         67        0.95       80.09
          Carolinian Guamani |          1        0.01       80.10
                      Cheraw |          1        0.01       80.12
                    Cherokee |         73        1.04       81.15
               Cherokee Choc |          1        0.01       81.17
            Cherokee Choctaw |          1        0.01       81.18
          Cherokee Choctaw M |          1        0.01       81.20
               Cherokee Coma |          2        0.03       81.23
           Cherokee Hawaiian |          1        0.01       81.24
               Cherokee Iroq |          2        0.03       81.27
               Cherokee Japa |          2        0.03       81.30
               Cherokee Kore |          1        0.01       81.31
               Cherokee Mexi |          3        0.04       81.35
            Cherokee Mexican |          1        0.01       81.37
               Cherokee Osag |          1        0.01       81.38
               Cherokee Puer |          2        0.03       81.41
          Cherokee Puerto Ri |          2        0.03       81.44
              Cherokee Sioux |          1        0.01       81.45
              Cherokee Yaqui |          1        0.01       81.47
                    Cheyenne |          1        0.01       81.48
               Cheyenne Rive |          1        0.01       81.50
                   Chickasaw |          2        0.03       81.52
               Chickasaw Cho |          1        0.01       81.54
                     Chilean |          1        0.01       81.55
               Chilean Mexic |          2        0.03       81.58
             Chilean Mexican |          2        0.03       81.61
                     Chinese |         26        0.37       81.98
               Chinese Filip |          3        0.04       82.02
            Chinese Filipino |          2        0.03       82.05
               Chinese Hawai |          1        0.01       82.07
               Chinese Hmong |          1        0.01       82.08
               Chinese Japan |          2        0.03       82.11
               Chinese Korea |          1        0.01       82.12
               Chinese Mexic |          1        0.01       82.14
          Chinese Puerto Ric |          1        0.01       82.15
                Chinese Thai |          2        0.03       82.18
               Chinese Vietn |          2        0.03       82.21
          Chinese Vietnamese |          1        0.01       82.22
                     Chinook |          1        0.01       82.24
                    Chippewa |          7        0.10       82.34
               Chippewa Mexi |          1        0.01       82.35
          Chippewa Narragans |          1        0.01       82.36
                     Choctaw |          9        0.13       82.49
            Choctaw Cherokee |          1        0.01       82.51
               Choctaw Creek |          1        0.01       82.52
               Choctaw Sioux |          1        0.01       82.53
               Choctaw Vietn |          1        0.01       82.55
              Choinumni Mono |          1        0.01       82.56
          Cochiti Pueblo Mex |          2        0.03       82.59
                   Colombian |         19        0.27       82.86
               Colombian Cub |          1        0.01       82.88
               Colombian Ecu |          2        0.03       82.90
               Colombian Pue |          1        0.01       82.92
                    Comanche |          4        0.06       82.98
                 Costa Rican |          1        0.01       82.99
               Costa Rican C |          1        0.01       83.00
               Costa Rican S |          2        0.03       83.03
                        Cree |          4        0.06       83.09
                       Creek |          5        0.07       83.16
                Creek Samoan |          1        0.01       83.17
              Creek Seminole |          1        0.01       83.19
                       Cuban |         22        0.31       83.50
               Cuban Laotian |          1        0.01       83.52
               Cuban Mexican |          3        0.04       83.56
                Cuban Puerto |          3        0.04       83.60
          Cuban Puerto Rican |          1        0.01       83.62
               Cuban Salvado |          1        0.01       83.63
               Cuban Unreada |          1        0.01       83.64
            Cuban Venezuelan |          1        0.01       83.66
                   Dominican |         35        0.50       84.16
               Dominican Ecu |          1        0.01       84.17
               Dominican Guy |          1        0.01       84.18
               Dominican Kor |          1        0.01       84.20
               Dominican Pue |          6        0.09       84.28
          Dominican Puerto R |          2        0.03       84.31
               Dominican Sal |          1        0.01       84.33
               East/Asian In |          9        0.13       84.45
           East/Asian Indian |          6        0.09       84.54
                  Ecuadorian |         10        0.14       84.68
               Ecuadorian Pu |          1        0.01       84.70
           Ecuadorian Puerto |          1        0.01       84.71
                      Eskimo |          2        0.03       84.74
                      Fijian |          1        0.01       84.75
                    Filipino |         73        1.04       85.79
               Filipino Guam |          1        0.01       85.81
          Filipino Guamanian |          1        0.01       85.82
               Filipino Hawa |          2        0.03       85.85
           Filipino Hawaiian |          1        0.01       85.86
               Filipino Japa |          1        0.01       85.88
               Filipino Kore |          1        0.01       85.89
               Filipino Mexi |          4        0.06       85.95
            Filipino Mexican |          2        0.03       85.98
          Filipino Puerto Ri |          1        0.01       85.99
               Filipino Viet |          2        0.03       86.02
          Filipino Vietnames |          1        0.01       86.03
               Guamanian/Cha |          3        0.04       86.08
          Guamanian/Chamorro |          1        0.01       86.09
                  Guatemalan |          6        0.09       86.18
               Guatemalan Ho |          2        0.03       86.20
               Guatemalan Me |          2        0.03       86.23
          Guatemalan Mexican |          2        0.03       86.26
               Guatemalan Pu |          1        0.01       86.28
               Guatemalan Sa |          1        0.01       86.29
                    Hawaiian |          3        0.04       86.33
               Hawaiian Poly |          1        0.01       86.35
          Hawaiian Polynesia |          1        0.01       86.36
                       Hmong |          6        0.09       86.45
                    Honduran |         11        0.16       86.60
               Honduran Nica |          3        0.04       86.64
          Honduran Panamania |          1        0.01       86.66
                       Houma |          2        0.03       86.69
               Hunkpapa Lako |          1        0.01       86.70
               Indonesian Pu |          1        0.01       86.72
                    Japanese |         26        0.37       87.09
               Japanese Kore |          2        0.03       87.11
               Japanese Mexi |          5        0.07       87.19
            Japanese Mexican |          2        0.03       87.21
             Japanese Samoan |          1        0.01       87.23
                       Kiowa |          2        0.03       87.26
                      Korean |         59        0.84       88.10
               Laguna Pueblo |          1        0.01       88.11
                Lakota Sioux |          1        0.01       88.12
          Lakota Sioux Oglal |          2        0.03       88.15
                     Laotian |         11        0.16       88.31
          Lenape Puerto Rica |          1        0.01       88.32
                      Lumbee |          5        0.07       88.39
                   Malaysian |          2        0.03       88.42
               Mescalero Apa |          4        0.06       88.48
                     Mexican |        431        6.13       94.61
               Mexican Nicar |          1        0.01       94.62
               Mexican Panam |          1        0.01       94.64
                Mexican Pima |          2        0.03       94.67
                Mexican Pomo |          1        0.01       94.68
               Mexican Puert |          8        0.11       94.79
          Mexican Puerto Ric |          3        0.04       94.84
               Mexican Salva |          3        0.04       94.88
          Mexican Salvadoran |          1        0.01       94.89
               Mexican Turki |          2        0.03       94.92
          Mexican Venezuelan |          1        0.01       94.94
               Mexican Yaqui |          1        0.01       94.95
                Mexican Zuni |          1        0.01       94.97
                       Miami |          1        0.01       94.98
                 Micronesian |          5        0.07       95.05
                    Muscogee |          1        0.01       95.06
                Métis Creole |          1        0.01       95.08
                      Navajo |          6        0.09       95.16
                Navajo Sioux |          1        0.01       95.18
                      Nepali |          2        0.03       95.21
                  Nicaraguan |          8        0.11       95.32
               Nicaraguan Sa |          1        0.01       95.33
                      Ojibwe |          3        0.04       95.38
                       Omaha |          1        0.01       95.39
                      Oneida |          2        0.03       95.42
                       Osage |          1        0.01       95.43
                     Palauan |          1        0.01       95.45
                  Panamanian |          9        0.13       95.58
               Panamanian Pu |          2        0.03       95.61
                  Paraguayan |          1        0.01       95.62
                    Peruvian |         10        0.14       95.76
          Peruvian Salvadora |          1        0.01       95.78
           Polynesian Samoan |          3        0.04       95.82
                  Potawatomi |          5        0.07       95.89
                Puerto Rican |        214        3.04       98.93
          Puerto Rican Senec |          1        0.01       98.95
          Puerto Rican Vietn |          1        0.01       98.96
                  Salvadoran |         17        0.24       99.20
               Salvadoran Ve |          2        0.03       99.23
                      Samoan |         11        0.16       99.39
                    Seminole |          2        0.03       99.42
                     Shawnee |          3        0.04       99.46
                       Sioux |          1        0.01       99.47
                  Sri Lankan |          1        0.01       99.49
                   Taiwanese |          1        0.01       99.50
                        Thai |          7        0.10       99.60
                   Tsimshian |          2        0.03       99.63
                     Turkish |          2        0.03       99.66
          Undisclosed Native |          1        0.01       99.67
                         Ute |          1        0.01       99.69
                  Vietnamese |         21        0.30       99.99
               Western Chero |          1        0.01      100.00
          -------------------+-----------------------------------
                       Total |      7,031      100.00

               gender |      Freq.     Percent        Cum.
          ------------+-----------------------------------
               Female |      2,183       31.05       31.05
                 Male |      4,848       68.95      100.00
          ------------+-----------------------------------
                Total |      7,031      100.00

             component |      Freq.     Percent        Cum.
          -------------+-----------------------------------
          Army Nationa |      2,903       41.29       41.29
          Army Reserve |        308        4.38       45.67
          Regular Army |      3,820       54.33      100.00
          -------------+-----------------------------------
                 Total |      7,031      100.00

                          branch |      Freq.     Percent        Cum.
          -----------------------+-----------------------------------
                     Combat Arms |      1,949       27.72       27.72
          Combat Service Support |      3,583       50.96       78.68
                  Combat Support |      1,499       21.32      100.00
          -----------------------+-----------------------------------
                           Total |      7,031      100.00

                    writingpreference |      Freq.     Percent        Cum.
          ----------------------------+-----------------------------------
                           Either han |         25        0.36        0.36
          Either hand (No preference) |         41        0.58        0.94
                            Left hand |        757       10.77       11.71
                           Right hand |      6,208       88.29      100.00
          ----------------------------+-----------------------------------
                                Total |      7,031      100.00

          installatio |
                    n |      Freq.     Percent        Cum.
          ------------+-----------------------------------
            Camp Atte |        441        6.27        6.27
            Camp Shel |      1,160       16.50       22.77
            Fort Blis |      1,926       27.39       50.16
            Fort Brag |        397        5.65       55.81
            Fort Drum |        391        5.56       61.37
            Fort Gord |        669        9.52       70.89
            Fort Hood |        439        6.24       77.13
            Fort Huac |        436        6.20       83.33
             Fort Lee |        380        5.40       88.74
            Fort McCo |        452        6.43       95.16
            Fort Ruck |          1        0.01       95.18
            Fort Stew |        339        4.82      100.00
          ------------+-----------------------------------
                Total |      7,031      100.00

                     test_date |      Freq.     Percent        Cum.
          ---------------------+-----------------------------------
          Tested on  01aug2011 |         20        0.28        0.28
          Tested on  01dec2010 |         54        0.77        1.05
          Tested on  01dec2011 |         23        0.33        1.38
          Tested on  01feb2012 |         28        0.40        1.78
          Tested on  01jun2011 |         28        0.40        2.18
          Tested on  01mar2012 |         38        0.54        2.72
          Tested on  02apr2012 |         12        0.17        2.89
          Tested on  02aug2011 |         15        0.21        3.10
          Tested on  02dec2010 |         56        0.80        3.90
          Tested on  02dec2011 |         21        0.30        4.20
          Tested on  02feb2012 |         30        0.43        4.62
          Tested on  02jun2011 |         41        0.58        5.21
          Tested on  02mar2012 |         36        0.51        5.72
          Tested on  02may2011 |         26        0.37        6.09
          Tested on  02nov2010 |         21        0.30        6.39
          Tested on  03apr2012 |         40        0.57        6.95
          Tested on  03aug2011 |         19        0.27        7.23
          Tested on  03dec2010 |         40        0.57        7.79
          Tested on  03feb2012 |         27        0.38        8.18
          Tested on  03jun2011 |         30        0.43        8.60
          Tested on  03may2011 |         25        0.36        8.96
          Tested on  03nov2010 |         16        0.23        9.19
          Tested on  03nov2011 |         25        0.36        9.54
          Tested on  03oct2011 |         20        0.28        9.83
          Tested on  04apr2012 |         17        0.24       10.07
          Tested on  04aug2011 |         19        0.27       10.34
          Tested on  04feb2012 |         20        0.28       10.62
          Tested on  04may2011 |          9        0.13       10.75
          Tested on  04nov2010 |         25        0.36       11.11
          Tested on  04nov2011 |         25        0.36       11.46
          Tested on  04oct2010 |          3        0.04       11.51
          Tested on  04oct2011 |         25        0.36       11.86
          Tested on  05apr2012 |         44        0.63       12.49
          Tested on  05aug2011 |         12        0.17       12.66
          Tested on  05dec2011 |         29        0.41       13.07
          Tested on  05jan2011 |         34        0.48       13.55
          Tested on  05jul2011 |         26        0.37       13.92
          Tested on  05mar2012 |         43        0.61       14.54
          Tested on  05oct2010 |         20        0.28       14.82
          Tested on  05oct2011 |         30        0.43       15.25
          Tested on  06dec2010 |         36        0.51       15.76
          Tested on  06dec2011 |         29        0.41       16.17
          Tested on  06jul2011 |         21        0.30       16.47
          Tested on  06jun2011 |         26        0.37       16.84
          Tested on  06mar2012 |         41        0.58       17.42
          Tested on  06oct2010 |         15        0.21       17.64
          Tested on  06oct2011 |         15        0.21       17.85
          Tested on  07apr2011 |          2        0.03       17.88
          Tested on  07dec2010 |         28        0.40       18.28
          Tested on  07dec2011 |         30        0.43       18.70
          Tested on  07feb2011 |         52        0.74       19.44
          Tested on  07jan2011 |         42        0.60       20.04
          Tested on  07jul2011 |         30        0.43       20.47
          Tested on  07jun2011 |         32        0.46       20.92
          Tested on  07mar2012 |         36        0.51       21.43
          Tested on  07nov2011 |         31        0.44       21.87
          Tested on  07oct2010 |         20        0.28       22.16
          Tested on  07sep2011 |          1        0.01       22.17
          Tested on  08apr2011 |         23        0.33       22.50
          Tested on  08aug2011 |         19        0.27       22.77
          Tested on  08dec2010 |         76        1.08       23.85
          Tested on  08dec2011 |         31        0.44       24.29
          Tested on  08feb2011 |         50        0.71       25.00
          Tested on  08jul2011 |         20        0.28       25.29
          Tested on  08jun2011 |         33        0.47       25.76
          Tested on  08mar2012 |         32        0.46       26.21
          Tested on  08nov2011 |         21        0.30       26.51
          Tested on  09aug2011 |         20        0.28       26.80
          Tested on  09dec2010 |         16        0.23       27.02
          Tested on  09dec2011 |         26        0.37       27.39
          Tested on  09feb2011 |         36        0.51       27.90
          Tested on  09jun2011 |         17        0.24       28.15
          Tested on  09mar2011 |         19        0.27       28.42
          Tested on  09mar2012 |         29        0.41       28.83
          Tested on  09nov2011 |         17        0.24       29.07
          Tested on  10aug2011 |         19        0.27       29.34
          Tested on  10dec2010 |         52        0.74       30.08
          Tested on  10feb2011 |         28        0.40       30.48
          Tested on  10jan2011 |         54        0.77       31.25
          Tested on  10mar2011 |         15        0.21       31.46
          Tested on  10nov2011 |         25        0.36       31.82
          Tested on  11apr2011 |         36        0.51       32.33
          Tested on  11aug2011 |          9        0.13       32.46
          Tested on  11feb2011 |          6        0.09       32.54
          Tested on  11jan2011 |         52        0.74       33.28
          Tested on  11jul2011 |         22        0.31       33.59
          Tested on  11mar2011 |         24        0.34       33.94
          Tested on  11oct2011 |         17        0.24       34.18
          Tested on  12apr2011 |         18        0.26       34.43
          Tested on  12aug2011 |         13        0.18       34.62
          Tested on  12dec2011 |         31        0.44       35.06
          Tested on  12jan2011 |         52        0.74       35.80
          Tested on  12jan2012 |         21        0.30       36.10
          Tested on  12jul2011 |         28        0.40       36.50
          Tested on  12mar2012 |         14        0.20       36.69
          Tested on  12oct2010 |         21        0.30       36.99
          Tested on  12oct2011 |         28        0.40       37.39
          Tested on  13apr2011 |         25        0.36       37.75
          Tested on  13dec2010 |         42        0.60       38.34
          Tested on  13dec2011 |         27        0.38       38.73
          Tested on  13jan2011 |         48        0.68       39.41
          Tested on  13jul2011 |         16        0.23       39.64
          Tested on  13mar2012 |         39        0.55       40.19
          Tested on  13oct2010 |         21        0.30       40.49
          Tested on  13oct2011 |         26        0.37       40.86
          Tested on  14apr2011 |         26        0.37       41.23
          Tested on  14dec2010 |         38        0.54       41.77
          Tested on  14dec2011 |         29        0.41       42.18
          Tested on  14jul2011 |         15        0.21       42.40
          Tested on  14mar2011 |         29        0.41       42.81
          Tested on  14mar2012 |         28        0.40       43.21
          Tested on  14nov2011 |         17        0.24       43.45
          Tested on  14oct2010 |         28        0.40       43.85
          Tested on  14oct2011 |         12        0.17       44.02
          Tested on  15aug2011 |         33        0.47       44.49
          Tested on  15dec2010 |         28        0.40       44.89
          Tested on  15dec2011 |         27        0.38       45.27
          Tested on  15feb2011 |         34        0.48       45.75
          Tested on  15feb2012 |         28        0.40       46.15
          Tested on  15jul2011 |         19        0.27       46.42
          Tested on  15mar2011 |         39        0.55       46.98
          Tested on  15mar2012 |         29        0.41       47.39
          Tested on  15nov2011 |         15        0.21       47.60
          Tested on  15oct2010 |         28        0.40       48.00
          Tested on  16aug2011 |         32        0.46       48.46
          Tested on  16dec2010 |         20        0.28       48.74
          Tested on  16feb2011 |         48        0.68       49.42
          Tested on  16feb2012 |         29        0.41       49.84
          Tested on  16mar2011 |         21        0.30       50.14
          Tested on  16mar2012 |         34        0.48       50.62
          Tested on  16nov2010 |          2        0.03       50.65
          Tested on  16nov2011 |         16        0.23       50.87
          Tested on  17feb2011 |         38        0.54       51.42
          Tested on  17feb2012 |         29        0.41       51.83
          Tested on  17jan2012 |         24        0.34       52.17
          Tested on  17mar2011 |         31        0.44       52.61
          Tested on  17may2011 |         22        0.31       52.92
          Tested on  17nov2010 |         36        0.51       53.43
          Tested on  17nov2011 |         26        0.37       53.80
          Tested on  17oct2011 |         26        0.37       54.17
          Tested on  18apr2011 |         26        0.37       54.54
          Tested on  18jan2011 |         58        0.82       55.37
          Tested on  18jan2012 |         18        0.26       55.63
          Tested on  18jul2011 |         22        0.31       55.94
          Tested on  18mar2011 |         35        0.50       56.44
          Tested on  18nov2010 |         42        0.60       57.03
          Tested on  18nov2011 |         28        0.40       57.43
          Tested on  18oct2010 |         26        0.37       57.80
          Tested on  18oct2011 |         28        0.40       58.20
          Tested on  19apr2011 |         19        0.27       58.47
          Tested on  19jan2011 |         54        0.77       59.24
          Tested on  19jan2012 |         31        0.44       59.68
          Tested on  19mar2012 |         32        0.46       60.13
          Tested on  19may2011 |         26        0.37       60.50
          Tested on  19nov2010 |         44        0.63       61.13
          Tested on  19oct2010 |         19        0.27       61.40
          Tested on  19oct2011 |         27        0.38       61.78
          Tested on  20apr2011 |         26        0.37       62.15
          Tested on  20jan2011 |         62        0.88       63.04
          Tested on  20jan2012 |         25        0.36       63.39
          Tested on  20jun2011 |         21        0.30       63.69
          Tested on  20mar2012 |         37        0.53       64.22
          Tested on  20may2011 |         25        0.36       64.57
          Tested on  20oct2010 |         18        0.26       64.83
          Tested on  20oct2011 |         28        0.40       65.23
          Tested on  21apr2011 |         17        0.24       65.47
          Tested on  21feb2012 |         43        0.61       66.08
          Tested on  21jan2011 |         34        0.48       66.56
          Tested on  21jan2012 |         19        0.27       66.83
          Tested on  21jun2011 |          9        0.13       66.96
          Tested on  21mar2011 |         36        0.51       67.47
          Tested on  21mar2012 |         36        0.51       67.98
          Tested on  21may2011 |         28        0.40       68.38
          Tested on  21nov2011 |         19        0.27       68.65
          Tested on  21oct2010 |         27        0.38       69.04
          Tested on  21oct2011 |         22        0.31       69.35
          Tested on  22apr2011 |          6        0.09       69.44
          Tested on  22feb2011 |         56        0.80       70.23
          Tested on  22feb2012 |         25        0.36       70.59
          Tested on  22jun2011 |         25        0.36       70.94
          Tested on  22mar2011 |         19        0.27       71.21
          Tested on  22mar2012 |         29        0.41       71.63
          Tested on  22nov2010 |         58        0.82       72.45
          Tested on  22nov2011 |         23        0.33       72.78
          Tested on  22oct2010 |         24        0.34       73.12
          Tested on  23feb2012 |         39        0.55       73.67
          Tested on  23jun2011 |         19        0.27       73.94
          Tested on  23nov2010 |         60        0.85       74.80
          Tested on  23nov2011 |         13        0.18       74.98
          Tested on  24feb2011 |         50        0.71       75.69
          Tested on  24feb2012 |         34        0.48       76.18
          Tested on  24jan2012 |         36        0.51       76.69
          Tested on  24jun2011 |         12        0.17       76.86
          Tested on  24mar2011 |         14        0.20       77.06
          Tested on  24mar2012 |         30        0.43       77.49
          Tested on  24may2011 |         12        0.17       77.66
          Tested on  24oct2011 |         23        0.33       77.98
          Tested on  25apr2011 |         22        0.31       78.30
          Tested on  25feb2011 |         50        0.71       79.01
          Tested on  25jan2012 |         35        0.50       79.51
          Tested on  25jul2011 |         26        0.37       79.87
          Tested on  25mar2011 |         33        0.47       80.34
          Tested on  25mar2012 |         33        0.47       80.81
          Tested on  25may2011 |          2        0.03       80.84
          Tested on  25oct2010 |         18        0.26       81.10
          Tested on  25oct2011 |         23        0.33       81.43
          Tested on  26apr2011 |         22        0.31       81.74
          Tested on  26jan2012 |         28        0.40       82.14
          Tested on  26jul2011 |         21        0.30       82.43
          Tested on  26mar2011 |         32        0.46       82.89
          Tested on  26mar2012 |         40        0.57       83.46
          Tested on  26may2011 |         40        0.57       84.03
          Tested on  26oct2010 |         28        0.40       84.43
          Tested on  26oct2011 |         25        0.36       84.78
          Tested on  27apr2011 |         39        0.55       85.34
          Tested on  27feb2012 |         45        0.64       85.98
          Tested on  27jan2011 |         42        0.60       86.57
          Tested on  27jan2012 |         31        0.44       87.01
          Tested on  27jul2011 |         16        0.23       87.24
          Tested on  27jun2011 |         15        0.21       87.46
          Tested on  27mar2011 |         13        0.18       87.64
          Tested on  27mar2012 |         19        0.27       87.91
          Tested on  27may2011 |         33        0.47       88.38
          Tested on  27oct2010 |         18        0.26       88.64
          Tested on  27oct2011 |         22        0.31       88.95
          Tested on  28apr2011 |         16        0.23       89.18
          Tested on  28feb2012 |         43        0.61       89.79
          Tested on  28jan2011 |         22        0.31       90.10
          Tested on  28jan2012 |         33        0.47       90.57
          Tested on  28jul2011 |         23        0.33       90.90
          Tested on  28jun2011 |         20        0.28       91.18
          Tested on  28mar2012 |         20        0.28       91.47
          Tested on  28may2011 |         37        0.53       91.99
          Tested on  28nov2011 |         21        0.30       92.29
          Tested on  28oct2010 |         25        0.36       92.65
          Tested on  29apr2011 |          8        0.11       92.76
          Tested on  29feb2012 |         39        0.55       93.32
          Tested on  29jul2011 |         23        0.33       93.64
          Tested on  29jun2011 |         20        0.28       93.93
          Tested on  29mar2011 |         11        0.16       94.08
          Tested on  29mar2012 |         18        0.26       94.34
          Tested on  29nov2010 |         52        0.74       95.08
          Tested on  29nov2011 |         27        0.38       95.46
          Tested on  29oct2010 |         18        0.26       95.72
          Tested on  30jan2011 |         66        0.94       96.66
          Tested on  30jun2011 |         20        0.28       96.94
          Tested on  30mar2011 |         39        0.55       97.50
          Tested on  30nov2010 |         38        0.54       98.04
          Tested on  30nov2011 |         17        0.24       98.28
          Tested on  31jan2011 |         40        0.57       98.85
          Tested on  31jan2012 |         30        0.43       99.27
          Tested on  31mar2011 |         31        0.44       99.72
          Tested on  31may2011 |         20        0.28      100.00
          ---------------------+-----------------------------------
                         Total |      7,031      100.00

              strdate |      Freq.     Percent        Cum.
          ------------+-----------------------------------
                      |        963       13.70       13.70
            01aug2011 |         20        0.28       13.98
            01dec2010 |         27        0.38       14.36
            01dec2011 |         23        0.33       14.69
            01feb2012 |         28        0.40       15.09
            01jun2011 |         28        0.40       15.49
            01mar2012 |         38        0.54       16.03
            02apr2012 |         12        0.17       16.20
            02aug2011 |         15        0.21       16.41
            02dec2010 |         28        0.40       16.81
            02dec2011 |         21        0.30       17.11
            02feb2012 |         30        0.43       17.54
            02jun2011 |         41        0.58       18.12
            02mar2012 |         36        0.51       18.63
            02may2011 |         26        0.37       19.00
            02nov2010 |         21        0.30       19.30
            03apr2012 |         40        0.57       19.87
            03aug2011 |         19        0.27       20.14
            03dec2010 |         20        0.28       20.42
            03feb2012 |         27        0.38       20.81
            03jun2011 |         30        0.43       21.23
            03may2011 |         25        0.36       21.59
            03nov2010 |         16        0.23       21.82
            03nov2011 |         25        0.36       22.17
            03oct2011 |         20        0.28       22.46
            04apr2012 |         17        0.24       22.70
            04aug2011 |         19        0.27       22.97
            04feb2012 |         20        0.28       23.25
            04may2011 |          9        0.13       23.38
            04nov2010 |         25        0.36       23.74
            04nov2011 |         25        0.36       24.09
            04oct2010 |          3        0.04       24.14
            04oct2011 |         25        0.36       24.49
            05apr2012 |         44        0.63       25.12
            05aug2011 |         12        0.17       25.29
            05dec2011 |         29        0.41       25.70
            05jan2011 |         17        0.24       25.94
            05jul2011 |         26        0.37       26.31
            05mar2012 |         43        0.61       26.92
            05oct2010 |         20        0.28       27.21
            05oct2011 |         30        0.43       27.63
            06dec2010 |         18        0.26       27.89
            06dec2011 |         29        0.41       28.30
            06jul2011 |         21        0.30       28.60
            06jun2011 |         26        0.37       28.97
            06mar2012 |         41        0.58       29.55
            06oct2010 |         15        0.21       29.77
            06oct2011 |         15        0.21       29.98
            07apr2011 |          2        0.03       30.01
            07dec2010 |         14        0.20       30.21
            07dec2011 |         30        0.43       30.64
            07feb2011 |         26        0.37       31.01
            07jan2011 |         21        0.30       31.30
            07jul2011 |         30        0.43       31.73
            07jun2011 |         32        0.46       32.19
            07mar2012 |         36        0.51       32.70
            07nov2011 |         31        0.44       33.14
            07oct2010 |         20        0.28       33.42
            07sep2011 |          1        0.01       33.44
            08apr2011 |         23        0.33       33.76
            08aug2011 |         19        0.27       34.03
            08dec2010 |         38        0.54       34.58
            08dec2011 |         31        0.44       35.02
            08feb2011 |         25        0.36       35.37
            08jul2011 |         20        0.28       35.66
            08jun2011 |         33        0.47       36.13
            08mar2012 |         32        0.46       36.58
            08nov2011 |         21        0.30       36.88
            09aug2011 |         20        0.28       37.16
            09dec2010 |          8        0.11       37.28
            09dec2011 |         26        0.37       37.65
            09feb2011 |         18        0.26       37.90
            09jun2011 |         17        0.24       38.15
            09mar2011 |         19        0.27       38.42
            09mar2012 |         29        0.41       38.83
            09nov2011 |         17        0.24       39.07
            10aug2011 |         19        0.27       39.34
            10dec2010 |         26        0.37       39.71
            10feb2011 |         14        0.20       39.91
            10jan2011 |         27        0.38       40.29
            10mar2011 |         15        0.21       40.51
            10nov2011 |         25        0.36       40.86
            11apr2011 |         36        0.51       41.37
            11aug2011 |          9        0.13       41.50
            11feb2011 |          3        0.04       41.54
            11jan2011 |         26        0.37       41.91
            11jul2011 |         22        0.31       42.23
            11mar2011 |         24        0.34       42.57
            11oct2011 |         17        0.24       42.81
            12apr2011 |         18        0.26       43.07
            12aug2011 |         13        0.18       43.25
            12dec2011 |         31        0.44       43.69
            12jan2011 |         26        0.37       44.06
            12jan2012 |         21        0.30       44.36
            12jul2011 |         28        0.40       44.76
            12mar2012 |         14        0.20       44.96
            12oct2010 |         21        0.30       45.26
            12oct2011 |         28        0.40       45.65
            13apr2011 |         25        0.36       46.01
            13dec2010 |         21        0.30       46.31
            13dec2011 |         27        0.38       46.69
            13jan2011 |         24        0.34       47.03
            13jul2011 |         16        0.23       47.26
            13mar2012 |         39        0.55       47.82
            13oct2010 |         21        0.30       48.12
            13oct2011 |         26        0.37       48.49
            14apr2011 |         26        0.37       48.86
            14dec2010 |         19        0.27       49.13
            14dec2011 |         29        0.41       49.54
            14jul2011 |         15        0.21       49.75
            14mar2011 |         29        0.41       50.16
            14mar2012 |         28        0.40       50.56
            14nov2011 |         17        0.24       50.80
            14oct2010 |         28        0.40       51.20
            14oct2011 |         12        0.17       51.37
            15aug2011 |         33        0.47       51.84
            15dec2010 |         14        0.20       52.04
            15dec2011 |         27        0.38       52.42
            15feb2011 |         17        0.24       52.67
            15feb2012 |         28        0.40       53.06
            15jul2011 |         19        0.27       53.34
            15mar2011 |         39        0.55       53.89
            15mar2012 |         29        0.41       54.30
            15nov2011 |         15        0.21       54.52
            15oct2010 |         28        0.40       54.91
            16aug2011 |         32        0.46       55.37
            16dec2010 |         10        0.14       55.51
            16feb2011 |         24        0.34       55.85
            16feb2012 |         29        0.41       56.27
            16mar2011 |         21        0.30       56.56
            16mar2012 |         34        0.48       57.05
            16nov2010 |          1        0.01       57.06
            16nov2011 |         16        0.23       57.29
            17feb2011 |         19        0.27       57.56
            17feb2012 |         29        0.41       57.97
            17jan2012 |         24        0.34       58.31
            17mar2011 |         31        0.44       58.75
            17may2011 |         22        0.31       59.07
            17nov2010 |         18        0.26       59.32
            17nov2011 |         26        0.37       59.69
            17oct2011 |         26        0.37       60.06
            18apr2011 |         26        0.37       60.43
            18jan2011 |         29        0.41       60.84
            18jan2012 |         18        0.26       61.10
            18jul2011 |         22        0.31       61.41
            18mar2011 |         35        0.50       61.91
            18nov2010 |         21        0.30       62.21
            18nov2011 |         28        0.40       62.61
            18oct2010 |         26        0.37       62.98
            18oct2011 |         28        0.40       63.38
            19apr2011 |         19        0.27       63.65
            19jan2011 |         27        0.38       64.03
            19jan2012 |         31        0.44       64.47
            19mar2012 |         32        0.46       64.93
            19may2011 |         26        0.37       65.30
            19nov2010 |         22        0.31       65.61
            19oct2010 |         19        0.27       65.88
            19oct2011 |         27        0.38       66.26
            20apr2011 |         26        0.37       66.63
            20jan2011 |         31        0.44       67.07
            20jan2012 |         25        0.36       67.43
            20jun2011 |         21        0.30       67.73
            20mar2012 |         37        0.53       68.25
            20may2011 |         25        0.36       68.61
            20oct2010 |         18        0.26       68.87
            20oct2011 |         28        0.40       69.26
            21apr2011 |         17        0.24       69.51
            21feb2012 |         43        0.61       70.12
            21jan2011 |         17        0.24       70.36
            21jan2012 |         19        0.27       70.63
            21jun2011 |          9        0.13       70.76
            21mar2011 |         36        0.51       71.27
            21mar2012 |         36        0.51       71.78
            21may2011 |         28        0.40       72.18
            21nov2011 |         19        0.27       72.45
            21oct2010 |         27        0.38       72.83
            21oct2011 |         22        0.31       73.15
            22apr2011 |          6        0.09       73.23
            22feb2011 |         28        0.40       73.63
            22feb2012 |         25        0.36       73.99
            22jun2011 |         25        0.36       74.34
            22mar2011 |         19        0.27       74.61
            22mar2012 |         29        0.41       75.02
            22nov2010 |         29        0.41       75.44
            22nov2011 |         23        0.33       75.76
            22oct2010 |         24        0.34       76.11
            23feb2012 |         39        0.55       76.66
            23jun2011 |         19        0.27       76.93
            23nov2010 |         30        0.43       77.36
            23nov2011 |         13        0.18       77.54
            24feb2011 |         25        0.36       77.90
            24feb2012 |         34        0.48       78.38
            24jan2012 |         36        0.51       78.89
            24jun2011 |         12        0.17       79.06
            24mar2011 |         14        0.20       79.26
            24mar2012 |         30        0.43       79.69
            24may2011 |         12        0.17       79.86
            24oct2011 |         23        0.33       80.19
            25apr2011 |         22        0.31       80.50
            25feb2011 |         25        0.36       80.86
            25jan2012 |         35        0.50       81.35
            25jul2011 |         26        0.37       81.72
            25mar2011 |         33        0.47       82.19
            25mar2012 |         33        0.47       82.66
            25may2011 |          2        0.03       82.69
            25oct2010 |         18        0.26       82.95
            25oct2011 |         23        0.33       83.27
            26apr2011 |         22        0.31       83.59
            26jan2012 |         28        0.40       83.99
            26jul2011 |         21        0.30       84.28
            26mar2011 |         32        0.46       84.74
            26mar2012 |         40        0.57       85.31
            26may2011 |         40        0.57       85.88
            26oct2010 |         28        0.40       86.28
            26oct2011 |         25        0.36       86.63
            27apr2011 |         39        0.55       87.19
            27feb2012 |         45        0.64       87.83
            27jan2011 |         21        0.30       88.12
            27jan2012 |         31        0.44       88.56
            27jul2011 |         16        0.23       88.79
            27jun2011 |         15        0.21       89.01
            27mar2011 |         13        0.18       89.19
            27mar2012 |         19        0.27       89.46
            27may2011 |         33        0.47       89.93
            27oct2010 |         18        0.26       90.19
            27oct2011 |         22        0.31       90.50
            28apr2011 |         16        0.23       90.73
            28feb2012 |         43        0.61       91.34
            28jan2011 |         11        0.16       91.49
            28jan2012 |         33        0.47       91.96
            28jul2011 |         23        0.33       92.29
            28jun2011 |         20        0.28       92.58
            28mar2012 |         20        0.28       92.86
            28may2011 |         37        0.53       93.39
            28nov2011 |         21        0.30       93.69
            28oct2010 |         25        0.36       94.04
            29apr2011 |          8        0.11       94.15
            29feb2012 |         39        0.55       94.71
            29jul2011 |         23        0.33       95.04
            29jun2011 |         20        0.28       95.32
            29mar2011 |         11        0.16       95.48
            29mar2012 |         18        0.26       95.73
            29nov2010 |         26        0.37       96.10
            29nov2011 |         27        0.38       96.49
            29oct2010 |         18        0.26       96.74
            30jan2011 |         33        0.47       97.21
            30jun2011 |         20        0.28       97.50
            30mar2011 |         39        0.55       98.05
            30nov2010 |         19        0.27       98.32
            30nov2011 |         17        0.24       98.56
            31jan2011 |         20        0.28       98.85
            31jan2012 |         30        0.43       99.27
            31mar2011 |         31        0.44       99.72
            31may2011 |         20        0.28      100.00
          ------------+-----------------------------------
                Total |      7,031      100.00

          . replace is_suspicious = 1 if writingpreference == "Either han"
          (25 real changes made)

          . replace writingpreference = "Either hand (No preference)" if writingpreference == "Either han"
          (25 real changes made)

          . drop if is_adult == 0
          (2 observations deleted)

          . save project_data_v2, replace
          file project_data_v2.dta saved

          . duplicates report gender span waistcircumference chestcircumference weightkg stature subjectnumericrace

          Duplicates in terms of gender span waistcircumference chestcircumference weightkg stature subjectnumericrace

          --------------------------------------
             Copies | Observations       Surplus
          ----------+---------------------------
                  1 |         5187             0
                  2 |         1842           921
          --------------------------------------

          . duplicates tag gender span waistcircumference chestcircumference weightkg stature subjectnumericrace, gen(is_duplicate)

          Duplicates in terms of gender span waistcircumference chestcircumference weightkg stature subjectnumericrace

          . duplicates drop gender span waistcircumference chestcircumference weightkg stature subjectnumericrace , force

          Duplicates in terms of gender span waistcircumference chestcircumference weightkg stature subjectnumericrace

          (921 observations deleted)

          . foreach var of varlist thumbtipreach - hipbreadthsitting {
          .         replace `var' = `var' / 10
          . }
          variable thumbtipreach was int now float
          (6,108 real changes made, 1 to missing)
          variable span was int now float
          (6,108 real changes made, 1 to missing)
          variable footlength was int now float
          (6,108 real changes made, 1 to missing)
          variable kneeheightmidpatella was int now float
          (6,108 real changes made, 1 to missing)
          variable waistheightomphalion was int now float
          (6,108 real changes made, 1 to missing)
          variable functionalleglength was int now float
          (6,108 real changes made, 1 to missing)
          variable cervicaleheight was int now float
          (6,108 real changes made, 1 to missing)
          variable trochanterionheight was int now float
          (6,108 real changes made, 1 to missing)
          variable stature was int now float
          (6,108 real changes made, 1 to missing)
          variable waistcircumference was int now float
          (6,108 real changes made, 1 to missing)
          variable chestcircumference was int now float
          (6,108 real changes made, 1 to missing)
          variable bicristalbreadth was int now float
          (6,108 real changes made, 1 to missing)
          variable hipbreadth was int now float
          (6,108 real changes made, 1 to missing)
          variable hipbreadthsitting was int now float
          (6,108 real changes made, 1 to missing)

          . save project_data_v3, replace
          file project_data_v3.dta saved

          . label data "This dataset consists of survey data from the ANSUR-II dataset which consists of responses to a 2012 survey by the U.S. Army to measure demographic and anthropometric measures of personnel representing the US army."
          note: label truncated to 80 characters

          . label variable subjectnumericrace "A single or multi-digit code indicating a subject's self-reported race or races. Where 1 = White, 2 = Black, 3 = Hispanic, 4 = Asian, 5 = Native American, 6 = Pacific Islander, 8 = Other"
          note: label truncated to 80 characters

          . label variable dodrace "A single digit indicating a subject's self-reported preferred single race where selecting multiple races is not an option. Where 1 = White, 2 = Black, 3 = Hispanic, 4 = Asian, 5 = Native American, 6 = Pacific Islander, 8 = Other"
          note: label truncated to 80 characters

          . label variable ethnicity "Self-reported ethinicty of the individual"

          . label variable gender "Male or Female gender for the individual"

          . label variable age "Age of the respondent (years)"

          . label variable component "Which portion of the army the respondent came from:  Army National Guard, Army Reserve, or Regular Army"
          note: label truncated to 80 characters

          . label variable branch "Which branch of the army the respondent came from: Combat Arms, Combat Support, or Combat Service Support"
          note: label truncated to 80 characters

          . label variable writingpreference "Which hand the respondent prefers to write with."

          . label variable installation "U.S. army installation/camp where the measurements occurred."

          . label variable test_date "Date the measurements took place"

          . label variable weightlbs "Weight in pounds of the respondent (self-reported)"

          . label variable heightin "Height in inches of the respondent (self-reported)"

          . label variable thumbtipreach "Forward arm reach of the respondent in cm"

          . label variable span "Arm span length of the respondent in cm"

          . label variable footlength "Length of foot of the respondent in cm"

          . label variable kneeheightmidpatella "Height of the knee of the respondent in cm"

          . label variable waistheightomphalion "Height of the waist of the respondent in cm"

          . label variable functionalleglength "Functional leg length of the respondent in cm"

          . label variable cervicaleheight "Height of the neck cervical of the respondent in cm"

          . label variable trochanterionheight "Height to hip of the respondent in cm"

          . label variable stature "Measured height of the respondent in cm"

          . label variable waistcircumference "Waist circumfrence of the respondent in cm"

          . label variable chestcircumference "Chest circumfrence of the respondent in cm"

          . label variable bicristalbreadth "Pelvic breadth of the respondent in cm"

          . label variable hipbreadth "Hip breadth of the respondent in cm"

          . label variable hipbreadthsitting "Hip breadth while sitting of the respondent in cm"

          . label variable weightkg "Measured weight of the respondent in kg"

          . label variable date "Date of the testing of the respondent in date format"

          . label variable strdate "Date of the testing of the respondent in string format"

          . label variable u_id "Unique id for the respondent"

          . label variable is_suspicious "Indicator variable representing whether or not measurements from the respondent are suspicious. 1 = Yes 0 = No"
          note: label truncated to 80 characters

          . label variable is_adult "Indicator variable representing whether or not the respondent is an adult (>= 18 years of age). 1 = Yes 0 = No"
          note: label truncated to 80 characters

          . label variable is_duplicate "Indicator variable representing whether or not the response may be a duplicate of another response in the dataset based off the gender, span, waistcircumference, chestcircumference, weightkg, stature, and subjectnumericrace for the response. 1 = Potential Duplicate 0 = Unique"
          note: label truncated to 80 characters

          . ds, has(type numeric)
          subjectnum~e  weightlbs     span          waistheigh~n  trochanter~t  chestcircu~e  hipbreadth~g  u_id          is_duplicate
          dodrace       heightin      footlength    functional~h  stature       bicristalb~h  weightkg      is_suspici~s
          age           thumbtipre~h  kneeheight~a  cervicaleh~t  waistcircu~e  hipbreadth    date          is_adult

          . label define missing_value_labels .a "Not Recorded" .b "Refused Measurement" .c "Unknown Missing" .d "Suspicious Value"

          . foreach var of varlist `r(varlist)'{
          .         label values `var' missing_value_labels
          . }

          . label define dodrace_labels 1 "White" 2 "Black" 3 "Hispanic" 4 "Asian" 5 "Native American" 6 "Pacific Islander" 8 "Other" .d "Suspicious Value"

          . label values dodrace dodrace_labels

          . label define is_suspicious_labels 0 "Not Suspicious" 1 "Suspicious"

          . label values is_suspicious is_suspicious_labels

          . label define is_adult_labels 0 "Minor" 1 "Adult"

          . label values is_adult is_adult_labels

          . label define is_duplicate_labels 0 "Unique Record" 1 "Potential Duplicate"

          . label values is_duplicate is_duplicate_labels

          . save project_data_v4, replace
          file project_data_v4.dta saved

          . gen bmi = weightkg / ((stature/100)^2)
          (40 missing values generated)

          . replace bmi = .d if bmi == .
          (40 real changes made, 40 to missing)

          . label define bmi_sus_labels .d "Suspicious Value"

          . label values bmi bmi_sus_labels

          . label variable bmi "Body Mass Index (BMI) of the individual calculated from their weight in KG dvided by the square of their height in meters"
          note: label truncated to 80 characters

          . recode bmi (0/18.499999999 = 0) (18.5/24.9999999 = 1) (25/29.999999999 = 2) (30/max = 3) (missing = .d), gen(bmi_cat)
          (6,068 differences between bmi and bmi_cat)

          . label define bmi_cat_labels 0 "Underweight" 1 "Healthy" 2 "Overweight" 3 "Obese" .d "Suspicious Value"

          . label values bmi_cat bmi_cat_labels

          . label variable bmi_cat "BMI Categories for the individual based on the splits from the NIH."

          . gen month_of_testing = month(date)
          (42 missing values generated)

          . label variable month_of_testing "Month in which the testing occurred for the collected response"

          . recode month_of_testing (1 2 12 = 1) (3/5 = 2) (6/8 = 3) (9/11 = 4), gen(season_of_testing)
          (5,405 differences between month_of_testing and season_of_testing)

          . label define season_labels 1 "Winter" 2 "Spring" 3 "Summer" 4 "Autumn"

          . label values season_of_testing season_labels

          . label variable season_of_testing "Season in which the testing occurred for the collected response based on month of the year."
          note: label truncated to 80 characters

          . encode gender, generate(gender_num)

          . label variable gender_num "Numerical representation of the gender of the respondent."

          . encode writingpreference, generate(writingpreference_num)

          . label variable writingpreference_num "Numerical representation of the writing preference of the respondent."

          . gen body_category = 0

          . replace body_category = 1 if gender == "Male" & (bmi_cat == 0 | bmi_cat == 1) & stature < 171 & (trochanterionheight / stature < 0.51)
          (131 real changes made)

          . replace body_category = 1 if gender == "Female" & (bmi_cat == 0 | bmi_cat == 1) & stature < 158  & (trochanterionheight / stature < 0.51)
          (83 real changes made)

          . replace body_category = 2 if gender == "Male" & (bmi_cat == 2 | bmi_cat == 3) & stature < 171 & (trochanterionheight / stature < 0.51)
          (455 real changes made)

          . replace body_category = 2 if gender == "Female" & (bmi_cat == 2 | bmi_cat == 3) & stature < 158  & (trochanterionheight / stature < 0.51)
          (79 real changes made)

          . replace body_category = 3 if gender == "Male" & (bmi_cat == 0 | bmi_cat == 1) & stature > 179 & (trochanterionheight / stature > 0.51)
          (244 real changes made)

          . replace body_category = 3 if gender == "Female" & (bmi_cat == 0 | bmi_cat == 1) & stature < 166  & (trochanterionheight / stature > 0.51)
          (454 real changes made)

          . replace body_category = 4 if gender == "Male" & (bmi_cat == 2 | bmi_cat == 3) & stature > 179 & (trochanterionheight / stature > 0.51)
          (599 real changes made)

          . replace body_category = 4 if gender == "Female" & (bmi_cat == 2 | bmi_cat == 3) & stature < 166  & (trochanterionheight / stature > 0.51)
          (483 real changes made)

          . label define body_category_labels 0 "Average" 1 "Small" 2 "Stout" 3 "Lanky" 4 "Big"

          . label values body_category body_category_labels

          . label variable body_category "Simple category for the body type of an individual based on BMI, Gender, Height Percentiles, and Hip to Height Ratio"
          note: label truncated to 80 characters

          . save project_data_final, replace
          file project_data_final.dta saved



