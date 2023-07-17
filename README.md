# demixR
Interface for clustering analysis


App 3: Analysis of data groupings
This package will handle data without temporal or spatial information. It will have broad applications in the future but for now the focus will be on classification and causal direction. It will consist of two R packages and one single function from an existing package.
The first R package to be included in this app is our own AssignR which is already available in Shiny. Currently, it is within the IsoMemo app but I want to move it since of all the models within the IsoMemo app it is the only one that does not work with spatiotemporal data. AssignR is used to classify data (both continuous numeric and categorical) and the assign to one of these categories’ separate entries. For instance, imagine that you have a document classification based on word frequency (e.g. Period A document, Period B document, etc.). Word frequency is measured in a newly discovered document and AssignR will rank the probability of it belonging to the different periods.
The other R packages to be included in the app are mclust and tclust. These perform clustering on univariate and multivariate data. Mclust compares and ranks different models with various using BIC so that one can identify the best choice (see examples below). tclust includes options for handling outliers but is overall similar to mclust.



Implementation to follow this vignette: https://cran.r-project.org/web/packages/mclust/vignettes/mclust.html

Finally, when having data for different variables these might be causally linked. However, in many cases we do not know the causal direction. For instance, there is a correlation between ice-cream consumption and temperature. Here, the causal link is obvious. However, smoking is correlated with alcoholism, but it does not cause alcoholism.
The function lingam (part of the pcalg package) takes a matrix with variables and identifies causal links among these and the direction of these. Implementation as per this vignette (in this case only text output): https://rdrr.io/cran/pcalg/man/LINGAM.html
