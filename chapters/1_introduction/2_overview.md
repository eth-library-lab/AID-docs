\pagebreak
# Introduction

## Overview

Over the years, machine learning has been widely used in many different fields. Numerous libraries, frameworks and systems have been invented to develop ML-driven applications. However, the popularity of ML has still not done enough to ease the process of running ML algorithms; both for ML experts and other software engineers.

The project AID aims to remove the barriers in the way of using machine learning algorithms. It provides a digital library and a package manager for searching, downloading and running machine learning models. With AID, software developers are enabled to perform ML experiments and apply ML algorithms in a unified and systematic way. Interdisciplinary teams also benefit from the unified interface and they do not need to learn different machine learning algorithms, which is a major difficulty for interdisciplinary teams. The benefit of AID is three-fold:

* When scientists need to reproduce and evaluate ML algorithms, they have to manually find out and install the dependencies and any other requirements to run the algorithm. If they need to evaluate several different algorithms and compare the results, they have to repeat the process several times, which is tedious and time-consuming. 
* At the same time, software engineers are increasingly expected to have more ML knowledge and the technical skills to apply ML algorithms, which is not always feasible and can be inefficient.
* For interdisciplinary teams, they always need to hire a machine learning team to perform ML experiments, before they know if they can apply machine learning. It is not only time-consuming but also a major difficulty for interdisciplinary teams to find the right machine learning team.

With AID, the application of ML algorithms can be made more accessible in the following way. First, the whole team can search for established ML algorithms in the library, and then the software engineers deploy the models and upload a test dataset. Finally, experts from different domains can examine and explain the results before making a final decision on implementing the algorithm.

In order to make the usage of ML algorithms more systematic, AID imitates libraries for books and proposes three components. First, like the ISBN for books, AID provides a unified format for different ML models, such that these models can be read, extracted and indexed in the same way. Secondly, AID maintains a digital library where users are enabled to search, filter and inspect existing ML models. Last but not least, like checking out a copy of a book, AID allows users to download, install and run ready-to-use ML algorithms, all in a unified way with a package manager that handles the algorithms dependencies. An extensible pipeline allows these existing ML algorithms from the platform to be easily integrated into existing machine learning systems.

## Intended Audience

### Machine Learning Researchers

The first intended user group is for machine learning researchers. In this project, the "researchers" are defined as those who contribute models to the AID library. They have some intrinsic interests in sharing their own research results with the community, for example:

* To test their models on new datasets, even in battlefield environments.
* To gain reputation and credibility for their work.
* To hear back from the community about the limitations of their work.

As researchers, they are usually well-versed in machine learning and have a good understanding of the underlying algorithms. However, they are usually not familiar with the software development process, and do not have enough time to learn new tools.

### Machine Learning Users

Nowadays, machine learning has been used more and more widely. In this project, we define the machine learning users in two different categories:

* Machine learning researchers who need to evaluate and compare their results with the results of other researchers.
* Interdisciplinary teams who need machine learning algorithms in their data processing pipeline.

For researchers, they are usually comfortable and can be productive with command line interfaces. For interdisciplinary teams, they are usually not familiar with the software development process, and do not have much experience in the command line environment. Hence, to facilitate these two types of users, the AID project provides not only a command line interface but also a web user interface for operating the machine learning models.

## Project Motivation for ELL

*ETH Library Lab strives to advance information infrastructure and services for science, research and education. By boosting related ideas, practices and strategies, the initiative contributes to future scientific work environments.*

Machine learning has become a core component of recent research and education advancement. However, the infrastructure for machine learning research and education is not well-developed. Unlike books, papers, and even data, machine learning models are not equipped with a unified, well-established platform for users to access. The lack of such a system leads to the common difficulties, challenges and the complaints we have described before. 

As an initiative in a scientific library, ETH Library Lab is working towards building infrastructure and services for education, research and scientific discovery, in which machine learning algorithms are forms an essential component. Hence, it is of great interest the ETH Library Lab to develop, support and sustain such a system and provide it to the entire university, community and industry.