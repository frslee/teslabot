# _Answers to Rubric Questions for Week-14 Model Serving Assignment:_  
  
## _1. What are 3 advantages of deploying using Model Serving methods vs. deploying on GitHub Pages or HuggingFace for free?_  
___Ans:___  
ML models are often deployed, using a wide array of available (and often automated) tools, as __web services__ e.g., on AWS, Azure, Google Cloud Platform. In general, __Model Serving methods__ have several advantages compared to deploying on, for example, GitHub or HuggingFace:   
  
- Deploying on a _public repository,_ while certainly easy, requires _each_ end-user to reconstruct a _full, working copy of the ML model,_ together with all dependencies, helper functions, etc. This places an onerous burden on users without any guarantee that the (re)-assembled model will work as intended with the user's environment and hardware. _By comparison, serving methods sidestep this significant problem by serving the ML model through an API._  
    
- Serving methods allow for multiple access points and simultaneous requests by multiple users via appropriate _traffic management and load-balancing._ In this way, _near real-time_ predictions can be delivered with net cost savings. Furthermore, this approach allows the ML model to be available to _other applications_ via API calls.  
  
- Finally, model serving _permits close monitoring in (near) real time for model drift and deterioration in model performance._   
  
  
## 2. What is ML model deployment?  
___Ans:___  
As Kreuzberger, Kuhl, and Hirshl recently stated, _"The final goal of all industrial machine learning (ML) projects is to develop ML products and rapidly bring them into production" (arXiv:2205.02302)._ After all, even the most performant ML model confined to the research setting is of little value. _As such, model deployment can even be considered to be as important as model development._ 

To deploy an ML model is to productionize it--that is, to operationalize it for __end user__ access, utilization, and--if fulfilling its intended purpose--benefit.

Model deployment is a complex process, which currently incorporates numerous critical tasks, commonly including e.g., _containerization; continuous ML training,  evaluation, & monitoring; and, continuous integration, delivery, and deployment (CI/CD)._  
    
Note that models may be deployed in a variety of ways e.g., as  _live web services_ (as discussed above); in an offline _on-demand batch prediction mode_ (favored for e.g., high-volume inference using complex models); or even as _(simplified) embedded models_ on mobile devices.
  
  
  
## 3. What is causal inference and how does it work?  
___Ans:___  
___Causal inference___ is the result of:  
- _inferring,_ that is deriving a conclusion from facts, evidence, premises, etc. ___about:___  
- _causation,_ that is, for example, the _strong_ conclusion that X _causes_ Y (X → Y), as distinct from the _weaker_ conclusion that X & Y are often/always observed in each other's company viz., X & Y are _correlated_ (X ⇿ Y). Note that correlation is _bidrectional,_ since _both_ X & Y occur together, while causation is most often _unidirectional,_ viz. X → Y, which does not necessarily imply, but also does not necessarily exclude, that Y → X.  

Most ML/AI to date (together with 'big data') has focused on learning  (often highly complex) patterns in data i.e., in establishing ___correlations___ and ___not causation.___ For instance, after training on sufficient data from the past, a performant ML/AI model may learn to make reasonably good predictions on inputs that lie within the learning space of its training data. However, it is critical to keep in mind that such a model has not formally and provably learned much about _causation._ As the admonition so popular in the financial industry goes, _"Past performance is no guarantee of future returns."_  

_Causal inference_ is the next frontier in AI, and holds the potential (1) to learn more fundamental truths relating inputs and outputs; (2) to make more accurate predictions regarding the outcomes of, for example, hypothetical scenarios in which variables in the input space are changed to ask specific questions; and (3) to 'modularize' portions of large ML/AI models (in which causation has been established), for use in asking other questions.  

___How does causal inference___ work? Although still in its infancy, there are currently two main approaches to discovering causality:  

- ___Potential outcomes framework:___ This approach essentially involves _reverse engineering_ an artifical control group to mimic gold-standard _randomized controlled trials._ For example in trying to establish whether or not mandating a driver's-ed class reduces teen car accidents, an AI algorithm can sift through a large training set to 'artificially' create two groups of teens that resemble one another as closely as possible in all respects (distribution of age, education, etc.), except for the variable of interest--in this case, attendance vs. non-attendance of a driver's-ed class.   
  
- ___Causal graph models:___   
    - In one approach of this type--which, in contrast to the _potential outcomes framework_ method above, can test for > 1 variable for a cause-and-effect relationship--an SME specifies which (and in what way) a subset of variables may interact, and then the AI model uses the available data to test these hypothesized interactions _(so-called structural equation model)._  
      
    - In a second approach of this type _(so-called causal Bayesian network)_, an SME creates a visual map of interacting variables by estimating the relationships between all variables in a data set. 

  
- Importantly, the use of _causal inference_ methods allows for the discovery of _causal relationships,_ giving visibility (understandability/explainability) into the relationships between input variables and outcomes, _in contrast to purely data-driven, black-box deep-learning model predictions._

_Ref.: Sgaier, S.K. et al. The Case for Causal AI. Stanford Soc. Innov. Rev., Summer 2020, pp. 50-55._
  
     
## 4. What is serverless deployment and how does it compared with deployment on a server?  
___Ans:___  
"Serverless" deployment is model deployment in the cloud, in which the backend servers have been _abstracted away_ from application development. As such, developers are freed from server management tasks by the _cloud provider,_ which dynamically provisions, scales, and maintains the underlying server infrastructure _on an as needed basis_ to match fluctuating user demand _in real-time._   
  
In general, serverless deployment involves provision by the _cloud provider_ of:  
- ___Function as a service (FaaS):___ Code hosted in the cloud is run only when triggered by _specified event(s),_ which result in the instantiation of the computing services necessary to execute the function code. Upon task completetion, FaaS--together with all required resources allocated/provisioned--vanishes, freeing up those resources, which then cease accruing billable costs.  
  
- ___Backend as a service (Baas):___ The _cloud provider_ takes care of provisioning and managing all _backend services_ required for FaaS (above), including e.g., code/data storage and user authentication and management.  

In sum, serverless deployment, a recent (and fast-growing) cloud technology, not only unburdens developers (who now need only focus on writing and deploying code instead of also managing servers); but also yields significant cost savings to clients and to the environment.
  


