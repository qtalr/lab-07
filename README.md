# Lab 07: Transforming and documenting data

<!--
- [ ] Create dev container
-->

## Preparation

- Read/ annotate: [Recipe \#7](https://qtalr.github.io/qtalrkit/articles/recipe-7.html). You can refer back to this document to help you at any point during this lab activity.

## Objectives

- Review skills and knowledge to use R read, organize, and document data
- Learn to interpret a curated dataset and plan dataset transformation strategies
- Apply skills and knowledge to use R to transform and document data

## Instructions

### Getting started

In this lab, you will be using Git and Github to fork, clone, commit, and push changes to a repository. The repository you will select to use as the repository to fork to your own Github account can be one of the following:

- [Lab 07 repository](https://github.com/qtalr/lab-07)
- [Minimal template](https://github.com/qtalr/project)
- [Web-based project template](https://github.com/qtalr/project_web)
- Other (consult your instructor)

If you are starting with a new repository, fork and clone the repository you selected to your local machine. Then orient yourself to the repository by opening the README file and reviewing the template configuration.

If you are using an existing reproducible research project repository, open that project on your local machine, and `pull` the latest changes from the remote repository to ensure that your local and remote repositories are in sync.

Open a Quarto document in the process directory and name it accordingly (e.g., `3_transform.qmd`, `data_transform.qmd`, *etc.*).

The data you select to transform should be in a tidy format and may be one of the following:

- State of the Union Addresses (SOTU) (see [below for details](#state-of-the-union-addresses-sotu-dataset))
- The dataset you curated in Lab 06
- Other (consult your instructor)

### Transforming datasets

In your transformation process file,

1. add a section which provides a brief description of the curated dataset you are transforming. Include:

  - the name and/ or source of the data
  - the nature of the data
  - the observations and variables in the data
  - the unit of observation in the curated dataset

2. add a section which provides a description of the data structure of the dataset, outines the research question/ hypothesis the derived dataset will be able to address, and proposes an idealized format for the transformed dataset. Include:

  - the relevant unit of observation and variables
  - the research question or hypothesis the dataset will be able to address
  - the idealized format for the transformed dataset in a tabular format

3. add a section which programmatically reads, transforms, and writes the transformed dataset. This is where you will craft the code to transform the dataset. Include prose and code comments to describe the process.

4. Make sure to organize your dataset transformation process in a way that is reproducible. This means that you should be able to run the code in your data transformation process file and reproduce the process. Use the `data/derived` (or similar) directory to store the transformed dataset and the its data dictionary.

5. Make sure that your code is well documented with code comments and that you have included prose to describe the process of transforming the dataset.

6. Include a section to describe the resulting data and to display the data dictionary you have created for this dataset as a table.

7. Confirm that your code runs without errors and that the data is transformed and displayed as expected.

8. Finally, commit and push your changes to your Github repository.

### Assessing your progress

1. In your repository on Github, open an issue to provide feedback on your experience with this lab (Click on the 'Issues' tab and then click the 'New issue' button). Title the issue "Lab 07 feedback" and provide your feedback in the body of the issue.

Some questions to consider:

  - What did you learn?
  - What did you find most/ least challenging?
  - What resources did you consult?
    - Instructor? R or Quarto documentation, Websites (provide links)?
  - What more would you like to know about transforming datasets?
    - Find potential resources you might consult to continue your learning. Provide links and a brief description of the resource.

## Submission for feedback

- Provide a link to your GitHub repository


## State of the Union Addresses (SOTU) dataset

The State of the Union Addresses (SOTU) dataset is a curated dataset of the State of the Union Addresses from 1790 to 2019. The dataset is available in the `quanteda.corpora` package. Install the package before continuing.

```r
install.packages("quanteda.corpora")
```

With the `quanteda.corpora` package installed, you can load the dataset into your R session with the following code:

```r
sotu_corpus <- quanteda.corpora::data_corpus_sotu
```

To convert the corpus to a data frame, you can use the `tidytext::tidy()` function:

```r
sotu_df <- tidytext::tidy(sotu_corpus)
```

## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

