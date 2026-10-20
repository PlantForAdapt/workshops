# Instalação

Esta é uma página wiki sobre a instalação para o workshop "Dinâmica florestal com R". Para aproveitar ao máximo esse workshop prático, você precisará de:

- R: uma linguagem de programação para computação estatística e gráficos
- Rstudio: um ambiente de desenvolvimento integrado para R
- Inicialização do ambiente R, ou seja, todos os pacotes necessários para que o seminário use esse projeto com o R no Rstudio
- Teste: para confirmar que a instalação foi realizada corretamente

# R

Se ainda não a tiver, você precisará instalar a linguagem de programação R. Você pode encontrá-la aqui: <https://www.r-project.org/>. Recomendo que você use uma versão acima de 4.0.0.

# Rstudio

Da mesma forma, caso ainda não o tenha, recomendo que você use o R no ambiente de desenvolvimento integrado RStudio. Você pode encontrar o RStudio aqui: <https://posit.co/products/open-source/rstudio/>.

# Inicialização do ambiente

Você precisa prepare o ambiente de trabalho no R :

```         
install.packages(c("tidyverse", "GGally", "vegan", "brms", "tidybayes"))
```

:warning: Essa etapa pode demorar um pouco, pois instala os pacotes R necessários para o seminário.

# Teste

Para verificar se tudo está pronto, pode executar as seguintes linhas de código no Rstudio:

```         
library(brms)
fit1 <- brm(count ~ zAge + zBase * Trt + (1|patient),
            data = epilepsy, family = poisson())
summary(fit1)
```

Deverá obter o seguinte resultado:

```         
summary(fit1)
#>  Family: poisson 
#>   Links: mu = log 
#> Formula: count ~ zAge + zBase * Trt + (1 | patient) 
#>    Data: epilepsy (Number of observations: 236) 
#>   Draws: 4 chains, each with iter = 2000; warmup = 1000; thin = 1;
#>          total post-warmup draws = 4000
#> 
#> Multilevel Hyperparameters:
#> ~patient (Number of levels: 59) 
#>               Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
#> sd(Intercept)     0.59      0.07     0.46     0.74 1.01      566     1356
#> 
#> Regression Coefficients:
#>            Estimate Est.Error l-95% CI u-95% CI Rhat Bulk_ESS Tail_ESS
#> Intercept      1.78      0.12     1.55     2.01 1.00      771     1595
#> zAge           0.09      0.09    -0.08     0.27 1.00      590     1302
#> zBase          0.71      0.12     0.47     0.96 1.00      848     1258
#> Trt1          -0.27      0.16    -0.60     0.05 1.01      749     1172
#> zBase:Trt1     0.05      0.17    -0.30     0.38 1.00      833     1335
#> 
#> Draws were sampled using sampling(NUTS). For each parameter, Bulk_ESS
#> and Tail_ESS are effective sample size measures, and Rhat is the potential
#> scale reduction factor on split chains (at convergence, Rhat = 1).
```

Se tudo correu bem, parabéns :clap:!

:broken_heart: Caso contrário, não hesite em entrar em contato conosco usando nossos e-mails.

Esperamos vê-lo no seminário :heart:
