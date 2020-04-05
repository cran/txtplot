# txtplot
Text based plots in R. 

Basic plotting function
```r
require(stats)
txtplot(cars[,1], cars[,2])
```
```
    +----+------------+------------+-----------+------------+--+
120 +                                                     *    +
    |                                                          |
100 +                                                          +
    |                                                     * *  |
 80 +                           *         *                    +
    |                                        *       *    *    |
 60 +                           *              *               +
    |                              *    * *    *       *       |
 40 +                         *      *  * *  *                 +
    |                 *       * *    *  *    * *               |
 20 +         *       *  * *  * *  *                           +
    |            *    *  * *                                   |
    |  *      *    *                                           |
  0 +----+------------+------------+-----------+------------+--+
         5           10           15          20           25   

```
Can include axis labels when desired
```r
txtplot(cars[,1], cars[,2], xlab = "speed", ylab = "distance")
```
```
      +----+-----------+------------+-----------+-----------+--+
  120 +                                                   *    +
      |                                                        |
d 100 +                                                   *    +
i     |                                    *                *  |
s  80 +                          *         *                   +
t     |                                       * *    *    *    |
a  60 +                          *  *      *    *      *       +
n     |                        *         * *  * *              |
c  40 +                *       * *    *  *    * *              +
e     |         *      *  * *  * *  *                          |
   20 +           *    *  * *       *                          +
      |  *      *    *                                         |
    0 +----+-----------+------------+-----------+-----------+--+
           5          10           15          20          25   
                                speed                           
```
Text based density plot
```r
txtdensity(rnorm(500))
```
```
0.4 +-----------+--------------+-------------+--------------+--+
    |                       ****                               |
    |                      **   **                             |
    |                     **     **                            |
0.3 +                   ***       ****                         +
    |                 ***            **                        |
    |                **               **                       |
0.2 +               **                 **                      +
    |               *                   *                      |
    |              *                    **                     |
0.1 +            **                      ***                   +
    |           **                         ****                |
    |         ***                             ***              |
  0 +  ********                                 *************  +
    +-----------+--------------+-------------+--------------+--+
               -2              0             2              4   
```
Text based plotting of functions
```r
txtcurve(x/(x+1), 0, 4, xlab = "Emax model")
```
```
    +--+------------+------------+-------------+------------+--+
0.8 +                                        ****************  +
    |                              ***********                 |
    |                       *******                            |
0.6 +                 ******                                   +
    |              ****                                        |
    |           ***                                            |
0.4 +         **                                               +
    |       **                                                 |
0.2 +     **                                                   +
    |    **                                                    |
    |   *                                                      |
  0 +  *                                                       +
    +--+------------+------------+-------------+------------+--+
       0            1            2             3            4   
                             Emax model                         
```
Text based acf
```r
txtacf(rnorm(100))
```
```
     +--+------------+------------+------------+------------+--+
   1 +  *                                                      +
     |  *                                                      |
 0.8 +  *                                                      +
     |  *                                                      |
 0.6 +  *                                                      +
     |  *                                                      |
 0.4 +  *                                                      +
     |  *                                                      |
 0.2 +  *    *  *                                              +
     |  *    *  *                                   *     *    |
   0 +  * *  *  * *  * *  *  * *  *  * *  * *  *  * *  *  * *  +
     |            *  *    *          * *  * *  *  *            |
-0.2 +            *       *            *                       +
     +--+------------+------------+------------+------------+--+
        0            5           10           15           20   
```
Text based barchart
```r
x <- factor(c("orange", "orange", "red", "green", "green", "red",
             "yellow", "purple", "purple", "orange"))
txtbarchart(x)
```
```
   +--+------------+-------------+-------------+------------+--+
30 +               *                                           +
   |               *                                           |
25 +               *                                           +
   |               *                                           |
20 +  *            *             *             *               +
   |  *            *             *             *               |
15 +  *            *             *             *               +
10 +  *            *             *             *            *  +
   |  *            *             *             *            *  |
 5 +  *            *             *             *            *  +
   |  *            *             *             *            *  |
 0 +  *            *             *             *            *  +
   +--+------------+-------------+-------------+------------+--+
      1            2             3             4            5   
Legend: 1=green, 2=orange, 3=purple, 4=red, 5=yellow
```
Text based boxplots
```r
rand1 <- rnorm(100, 1, 2)
rand2 <- rnorm(50, 2, 2)
rand3 <- rnorm(50, 2, 5)
txtboxplot(rand1)
```
```
  -4        -2         0          2         4         6         
 |-+---------+---------+----------+---------+---------+--------|
                      +------+--------+                         
    ------------------|      |        |--------------------     
                      +------+--------+                         
```
```r
txtboxplot(rand1, rand2, rand3)
```
```
          -5               0               5              10    
 |---------+---------------+---------------+---------------+---|
                          +---+-----+                           
1              -----------|   |     |-------------              
                          +---+-----+                           
                               +--+-----+                       
2                       -------|  |     |-----------            
                               +--+-----+                       
                        +--------+-----+                        
3   --------------------|        |     |-------------------     
                        +--------+-----+                        
Legend: 1=rand1, 2=rand2, 3=rand3
```

Text based image plots (contributed by Ivan Krylov)
```r
txtimage(datasets::volcano, legend = FALSE)
```
```
01111111111111111111111111111111111111111111000010000000000000000000000000000000
11111111111111111111111111222211111111111111111111100000000000000000000000000000
11111111111111111222333333333332222211111111111111111111000000000000000000000000
11111111122222223344444445544444332222222222111111111100000000000000000000000000
11111112222333444555566666666555443333222222222211111111110000000000000000000000
11111112223344555667777888877766655443333222222222111111111110000000000000000000
11112223334445566778888888888877665444333333333222222222222111100000000000000000
11122334445566677889888888888887665544433333333333334444332222111100000000000000
11223444555677788999888877778777666555444444444444444444443322211111000000000000
12233445566778899999877766666777766665554444444444444444433332221111111000000000
12233445667788999999877665555667777766665555555555444444433332222211111110000000
11233455667788999999876665555667777777666666665555544444433333222222211111110000
11223445667788899999877666666677788887766666666655554444444333332222221111111100
11222334566778899999988777777778888887777777776665555555444443333322222111111110
11122233456677889999998888888888888887777777777666555555555554433332221111111100
01112223455677888899999888888887777777766677777666655555555555444333221111000000
00111223345667777888888888877766666666666666666666555555555555544432211000000000
01111122334566666777777777776655555555555555555555555555555555544332111000000000
00111112223344555566676666665555554444444444444444445555555555444322111110000000
00011111122333344445566665555444443333333333344444444444444444433332211110000000
00000111112222333344455555544433332222223333333333333333333333333322111110000000
00001111111222233334444444443332222222222222222222222222222233322221111100000000
00011111111122223333444444333222222212222222222222222222222222222211111000000000
00011111111122222333333333222211111111111122222222221122222222222211100000000000
00001111111112222222233322222111111111111111122221111111222222222111100000000000
```
```r
## this works if your terminal supports shade/block characters
txtimage(datasets::volcano, alphabet = " \u2591\u2592\u2593\u2588", legend = TRUE)
```
```
                                                                                
                          ░░░░                                                  
                 ░░░░░░░░░░░░░░░░░░░                                            
         ░░░░░░░░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░░░░                                    
       ░░░░░░░▒▒▒▒▒▒▒▓▓▓▓▓▓▓▓▒▒▒▒▒░░░░░░░░░░░░░░                                
       ░░░░░▒▒▒▒▒▓▓▓▓▓▓████▓▓▓▓▓▓▒▒▒▒░░░░░░░░░░░░░                              
    ░░░░░░▒▒▒▒▒▓▓▓▓███████████▓▓▓▓▒▒▒▒░░░░░░░░░░░░░░░░░░░░░                     
   ░░░░▒▒▒▒▒▓▓▓▓▓██████████████▓▓▓▒▒▒▒▒░░░░░░░░░░░░░▒▒▒▒░░░░░░                  
  ░░░▒▒▒▒▒▒▓▓▓▓█████████▓▓▓▓█▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░                 
 ░░░░▒▒▒▒▓▓▓▓████████▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░                
 ░░░░▒▒▒▓▓▓▓█████████▓▓▓▓▒▒▒▒▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░              
  ░░░▒▒▒▓▓▓▓█████████▓▓▓▓▒▒▒▒▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░░░░           
  ░░░▒▒▒▓▓▓▓█████████▓▓▓▓▓▓▓▓▓▓▓▓████▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░░░          
  ░░░░░▒▒▓▓▓▓██████████▓▓▓▓▓▓▓▓██████▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░░         
   ░░░░░▒▒▓▓▓▓███████████████████████▓▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░          
    ░░░░▒▒▒▓▓▓█████████████████▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░          
     ░░░░▒▒▓▓▓▓▓▓██████████▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░           
      ░░░░▒▒▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░            
       ░░░░░▒▒▒▒▒▒▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░            
         ░░░░░░▒▒▒▒▒▒▓▓▓▓▒▒▒▒▒▒▒▒▒░░░░░░░░░░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░           
          ░░░░░░░░▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░            
           ░░░░░░░░▒▒▒▒▒▒▒▒▒░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░             
            ░░░░░░░░▒▒▒▒▒▒░░░░░░░░░░ ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░              
            ░░░░░░░░░░░░░░░░░░            ░░░░░░░░░   ░░░░░░░░░░░░              
             ░░░░░░░░░░░░░░░░                ░░░░       ░░░░░░░░░               

 94 ‘ ’ 114 ‘░’ 134 ‘▒’ 154 ‘▓’ 174 ‘█’ 194 
```
