## Topic Modeling:


- [Topics over Time: A Non-Markov Continuous-Time Model of Topical Trends](tot-kdd06.pdf)
  - Summary: A variant of LDA model trying to capture the topical trends. The mixture distribution over topics is influenced by both word co-occurrences and the document’s timestamp. Timestamp for each word is the same timestamp for that document. 
  - [![Example](totkdd06.jpg)](https://raw.github.com/yning/papers/TopicModeling/master/totkdd05.jpg)
  - Draw T multinomials &phi;<sub>z</sub> from a Dirichlet prior &beta;, one for each topic z;
  - For each document d, draw a multinomial &theta;<sub>d</sub> from a Dirichlet prior &alpha;, then for each word w<sub>di</sub> in document d:
    - Draw a topic z<sub>di</sub> from multinomial &theta;<sub>d</sub>;
    - Draw a word w<sub>di</sub> from multinomial &phi;<sub>z<sub>di</sub></sub>;
    - Draw a timestamp t<sub>di</sub> from Beta &psi;<sub>z<sub>di</sub></sub>;



