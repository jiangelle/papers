## Topic Modeling:

### [Topic Modeling Bibliography](http://mimno.infosci.cornell.edu/topics.html)
- Dr. Mimno organizes resources on Topic Modeling and labels each paper based on its category. It is awesome! Thanks to him!

### [Latent Dirichlet Allocation](http://www.cs.princeton.edu/~blei/papers/BleiNgJordan2003.pdf)(JMLR03)
- Authors: David M. Blei, Andrew Y. Ng, Michael I. Jordan.
- Summary: This paper presents efficient approximate inference techniques based on variational methods and an EM algorithm for empirical Bayes parameter estimation.

### [Finding Scientific Topics](http://psiexp.ss.uci.edu/research/papers/sciencetopics.pdf)(PNAS04)
- Authors:Thomas L. Griffiths, Mark Steyvers.
- Summary: Using Gibbs Sampling to discover topics in articles.

### [Topics over Time: A Non-Markov Continuous-Time Model of Topical Trends](tot-kdd06.pdf) (ACM SIGKDD06) <br/>
| Graphical Model of TOT |
|:---:|
| <a href="totkdd06.jpg"><img width=290 src="totkdd06.jpg" alt=""></a> |

<!--<div align="center"><img src="totkdd06.jpg" align="middle"/></div>-->
- Authors: Xuerui Wang, Andrew McCallum.
- Summary: A variant of LDA model trying to capture the topical trends. The mixture distribution over topics is influenced by both word co-occurrences and the document’s timestamp. Timestamp for each word is the same with that document. 
- Generative Process: 
  - Draw T multinomials &phi;<sub>z</sub> from a Dirichlet prior &beta;, one for each topic z;
  - For each document d, draw a multinomial &theta;<sub>d</sub> from a Dirichlet prior &alpha;, then for each word w<sub>di</sub> in document d:
    - Draw a topic z<sub>di</sub> from multinomial &theta;<sub>d</sub>;
    - Draw a word w<sub>di</sub> from multinomial &phi;<sub>z<sub>di</sub></sub>;
    - Draw a timestamp t<sub>di</sub> from Beta &psi;<sub>z<sub>di</sub></sub>;

- They use Gibbs Sampling to perform approximate inference and evaluate their model on 3 dataset: NIPS papers(17 years: 1987-2003), A Researcher's Emails(9 months), State-of-the-Union Addresses(21 decades) and compare TOT to LDA. Also, they use topic distributions of documents to predict timestamps. Number of topics T is fixed to be 50. &alpha;=50/T, &beta; = 0.1.

### [Dynamic Topic Models](dtm_icml06.pdf)(ICML06)
- Authors: David M. Blei, John D. Lafferty.
- Summary: While traditional time series modeling has focused on continuous data, topic models are designed for categorical data. They use state space models on the natural parameter space of the underlying topic multinomials, as well as on the nutural parameters for the logistic normal distributions used for modeling the document-specific topic proportions.

### [Probabilistic Topic Models](http://psiexp.ss.uci.edu/research/papers/SteyversGriffithsLSABookFormatted.pdf)(Handbook of Latent Semantic Analysis07) 
- Authors: Mark Steyvers, Tom Griffiths. 
- Summary: This paper introduces Gibbs Sampling for inference of LDA model.

### [Labeled LDA: A supervised topic model for credit attribution in multi-labeled corpora](http://www.aclweb.org/anthology/D09-1026)(EMNLP09)
| Graphical Model of Labeled LDA |
|:---:|
| <a href="twitter-icwsm10.png"><img width=466 src="twitter-icwsm10.png" alt=""></a> |

- Authors: Daniel Ramage, David Hall, Ramesh Nallapati and Christopher D. Manning
- Summary: A topic model that contrains LDA by defining a one-to-one correspondence between LDA's latent topics and user tags.

### [Characterizing Microblogs with Topic Models](twitter-icwsm10.pdf) (ICWSM10)
| Graphical Model of Labeled LDA on Twitter |
|:---:|
| <a href="twitter-icwsm10.png"><img width=466 src="twitter-icwsm10.png" alt=""></a> |

<!--<div align="center"><img src="twitter-icwsm10.png"/></div>-->
- Authors: Daniel Ramage, Susan Dumais, Dan Liebling.
- Summary: This paper introduces a way to characterize tweets using topic modeling.
- Generative Process:
  - For each topic k in 1..K, draw a multinomial distribution &beta;<sub>k</sub> from symmetric Dirichlet prior &eta;.
  - For each tweet d in 1..D:
    - 1. Build a label set &Lambda; describing the tweet from the deterministic prior &Phi;
    - 2. Select a multinomial distribution &theta;<sub>d</sub> over the labels &Lambda;<sub>d</sub> from symmetric Dirichlet prior &alpha;.
    - 3. For each word position i 1..N in tweet d. First draw a label z<sub>d</sub> from label multinomial &theta;<sub>d</sub>. Then draw a word w<sub>d</sub>from word multinomial &beta;<sub>z</sub>.
- Implementation: Their methods does threading within compute nodes and communicates across nodes with MPI, and can complete training on the OneWeek dataset within about four days on a 24-machine cluster.

### [Geographical Topic Discovery and Comparison](http://web.engr.illinois.edu/~hanj/pdf/www11_zyin.pdf)(WWW11)
- Authors: Zhijun Yin, Liangliang Cao, Jiawei Han, Chengxiang Zhai, Thomas Huang
- Summary: Discover and compare the geographical topics from GPS-associate documents.

### [Probabilistic Topic Models](http://www.cs.princeton.edu/~blei/papers/Blei2012.pdf)(CACM12)
- Authors: David M. Blei.
- Summary: This paper surveyes probabilistic topic models to provide a statistical solution to manage large archives of documents. It investigated the Latent Dirichlet Allocation model(LDA), the extended versions and future directions for LDA.

### [Dirichlet Process with Mixed Random Measures:A Nonparametric Topic Model for Labeled Data](http://arxiv.org/pdf/1206.4658v1.pdf)(ICML12)
- Authors: Dongwoo Kim, Suin Kim and Alice Oh
- Summary: This paper describes a nonparametric topic model for labeled data using a mixture of random measures as a base distribution of the Dirichlet process of the HDP framework.

### [Sparse Stochastic Inference for Latent Dirichlet Allocation](http://mimno.infosci.cornell.edu/papers/mimno2012sparse.pdf)(ICML12)
- Authors: David Mimno, Matthew Hoffman, David Blei.
- Summary: A hybrid algorithm for Bayesian topic models that combines the efficiency of sparse Gibbs Sampling with the scalability of onilne stochastic inference.


### [The Contextual Focused Topic Model](http://people.ee.duke.edu/~lcarin/Xu_KDD_2012.pdf)(KDD12)
- Authors: Xu Chen, Mingyuan Zhou and Lawrence Carin
- Summary: A nonparametric Bayesian contextual focused topic model (cFTM) is proposed. The cFTM infers a sparse (“focused”) set of topics for each document, while also leveraging contex- tual information about the author(s) and document venue.

### [Syndromic Surveillance of Flu on Twitter using Temporal Topic Models](http://people.cs.vt.edu/naren/papers/twitter-topic-icdm14.pdf)(ICDM14)
| Graphical Model of HFSTM |
|:---:|
| <a href="hfstm.png"><img width=280 src="hfstm.png" alt=""></a> |

<!--<div align="center"><img src="hfstm.png"/></div>-->
- Authors: Liangzhe Chen, K. S. M. Tozammel Hossain, Patrick Butler, Naren Ramakrishnan, B. Aditya Prakash
- Summary: This paper proposes temporal topic models to capture hidden states of a user from his tweets and aggregate states in a geographical region for better estimation of flu trends. They define states of flue and combines the states as a hidden random variable into the temporal topic graphical models. 

### [Reducing the Sampling Complexity of Topic Models](http://www.sravi.org/pubs/fastlda-kdd2014.pdf)(KDD14)
- Authors: Aaron Q. Li, Amr Ahmed, Sujith Ravi and Alexander J. Smola
- Summary: 

### [The Inverse Regression Topic Model](http://www.cs.columbia.edu/~blei/papers/RabinovichBlei2014.pdf)(ICML14)
- Authors: Maxim Rabinovich and David Blei
- Summary:

