## Typesetting from ```R```

This is a draft of an ```R``` script (**still being tested**) that takes the output of ```glm()``` in ```R``` and creates the
LaTeX code that you need for your statistical table(s). It should also work for linear models, but the crucial thing is that
you can adapt it according to your specific needs. For example, p values are given in ```R``` terms (scientific notation). You
will want to change that.

In theory, the only thing you'll want to change is the p-value column. The rest is expected to be OK. I will keep working on this, so please report any bugs you might encounter.

The function ```tex()``` will take **one** argument (your model) and will return a ```.txt``` file that you can now paste into your
```.tex``` file. The file is named ```output.txt```, and it already contains all the necessary lines for tables in LaTeX. There are several alternatives available (```Hmisc```, for example).


```{r}


# Make sure you load the usual table/tabular packages:
# caption, subcaption, booktabs etc.

tex = function(yourModel){

model = yourModel


# Extracting variable names

vars0 = names(model[[1]])

vars = c()

for(i in vars0){
	vars[length(vars)+1] = paste("{\\tt{", i, "}}", sep = "")
}

###########################################


# Extracting coefficients

# E.g., accessing the first coefficient

numberOfCoefficients = length(model[[1]])


# Looping through all betas:

coefs = c()

for(i in 1:numberOfCoefficients){
	coefs[length(coefs)+1] = round(model[[1]][[i]],3)
}




###########################################

# Getting odds-ratio


OR = round(exp(abs(coefs)),3)


###########################################



# Extracting standard errors

ses = c()

for(i in 1:numberOfCoefficients){
	ses[length(ses)+1] = round(coef(summary(model))[,2][i],3)
}


###########################################

# Z values

z = c()


for(i in 1:numberOfCoefficients){
	z[length(z)+1] = round(coef(summary(model))[,3][[i]],3)
}

###########################################

# P values

p = c()

for(i in 1:numberOfCoefficients){
	p[length(p)+1] = coef(summary(model))[,4][[i]]
}



###########################################

dataNames = c('\\textbf{Predictor} &  $\\hat\\beta$ & \\textbf{OR} & \\textbf{SE} & \\textbf{\\textit{z} value} &\\textbf{\\textit{p} value}\\\\')

data = data.frame(Predictor = vars, col = "&", beta = coefs, col = "&", OR = OR, col = "&", SE = ses, col = "&", z.value = z, col = "&", p.value = p, new = "\\\\")

data = setNames(data, rep(" ", length(data)))


options(warn = -1)

preamble = "\\vspace{0.5cm}\n\\begin{table}[h]\n    \\centering \n        \\captionsetup{justification=centering}\n        \\caption{Your caption here}\n\n        \\label{table:model}\n\n        \\def\\arraystretch{1.2} \n\n \\begin{tabular}{@{}lrrrrr@{}} \n\n \\toprule"

row = "\\midrule"

bottom = "\\bottomrule\n\\end{tabular}\n\\end{table}"


write(preamble,file="output.txt",append=F)

write(dataNames, file = "output.txt", append=T)

write(row, file = "output.txt", append=T)


# options(warn = 0)

write.table(data, "output.txt", sep="\t", quote=F, row.names=F, append=T)



write(bottom, file="output.txt", append=T)


}



```
