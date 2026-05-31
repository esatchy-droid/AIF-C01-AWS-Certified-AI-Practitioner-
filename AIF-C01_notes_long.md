# AIF-C01 AWS Certified AI Practitioner — Topics & Concepts Reference

> Organised by exam domain. Each entry: **Concept** — expanded explanation (~1.5× one-liner).
> Exam weight: D3 28% · D2 24% · D1 20% · D4 14% · D5 14%

---

## D1 · AI/ML Fundamentals (20%)

### Core AI/ML Hierarchy

- **Artificial Intelligence** — The broad umbrella discipline where machines are designed to perform tasks that typically require human intelligence, such as problem solving, decision making, natural language understanding, speech recognition, and image recognition.

- **Machine Learning** — A subset of AI where systems automatically learn to improve at a task by finding patterns in data, without being explicitly programmed with rules for every scenario.

- **Deep Learning** — A subset of ML using neural networks with multiple hidden layers, enabling the model to learn hierarchical feature representations and excel at complex tasks like image classification, speech recognition, and NLP.

- **Generative AI** — A subset of AI focused on creating new, realistic content or data rather than just analysing existing data; modalities include text, images, audio, video, code, and even molecular or drug-discovery data.

- **Foundation Models** — Large models pre-trained on massive, diverse datasets that develop broad general capabilities and can be adapted or fine-tuned for many downstream tasks through prompting, RAG, or continued training (e.g. Claude, GPT-4, Amazon Titan).

- **Large Language Models (LLMs)** — A specific type of foundation model designed to generate and understand human-like text; typically built on transformer architecture and used for text generation, summarisation, Q&A, and chat use cases.

- **Transformer Models** — The architectural backbone of modern LLMs; processes entire sequences simultaneously using self-attention mechanisms that model contextual relationships between all tokens in a sentence, enabling superior language understanding.

- **Diffusion Models** — Generate high-quality images by learning to iteratively reverse a noise-addition process; the model gradually denoises random noise until a coherent image emerges (e.g. Stable Diffusion).

- **GANs (Generative Adversarial Networks)** — Use two competing networks — a generator that creates synthetic data and a discriminator that attempts to detect fakes — trained adversarially until the generator produces highly realistic outputs.

- **VAE (Variational Autoencoder)** — A generative model that encodes inputs into a compressed probabilistic latent space and can sample from that space to generate new data; distinct from standard autoencoders used mainly for compression/representation.

---

### Learning Types

- **Supervised Learning** — Trains on labelled input-output pairs so the model can generalise and predict outcomes on unseen data; covers classification (e.g. spam detection, churn prediction) and regression (e.g. price or demand prediction). Labelled data is the key requirement.

- **Unsupervised Learning** — Trains or analyses unlabelled data where the system discovers hidden structure, groupings, or relationships by itself, without predefined correct answers; techniques include clustering, association, and dimensionality reduction. Human validation of discovered patterns is still often needed.

- **Semi-supervised Learning** — Combines a small amount of labelled data with a much larger pool of unlabelled data to improve model performance; particularly valuable when full labelling is too expensive, slow, or practically infeasible.

- **Reinforcement Learning** — An agent learns optimal behaviour by operating in an environment and iteratively receiving rewards for good actions and penalties for bad ones; used in game AI, robotics, navigation, and real-time decision optimisation. There is no pre-existing labelled training set in the conventional supervised sense.

---

### ML Task Types

- **Classification** — A supervised learning task that predicts a discrete class or category for each input, such as fraud/not fraud, rain/no rain, or customer churn/no churn. Evaluation uses metrics like precision, recall, F1, and accuracy.

- **Regression** — A supervised learning task that predicts a continuous numeric value such as price, temperature, demand, or revenue. Do not choose regression for categorical yes/no outcomes — that is classification.

- **Clustering** — An unsupervised learning task that groups unlabelled data points together based on similarity, without pre-defined categories; commonly used for customer segmentation, anomaly grouping, or topic discovery.

- **Association** — An unsupervised technique for discovering co-occurrence relationships between variables in a dataset, such as "customers who buy bread often buy butter"; used for recommendation and market-basket analysis, not to be confused with classification.

- **Dimensionality Reduction** — Reduces the number of features or dimensions in a dataset while retaining the most important variance and signal, primarily used for preprocessing, visualisation, and noise removal — not just for storage cost savings.

- **Anomaly Detection** — Identifies unusual patterns, events, or data points that deviate significantly from expected behaviour; used in fraud detection, operations monitoring, and security; the SageMaker built-in algorithm for this is Random Cut Forest.

---

### Model Training Concepts

- **Neural Network Layers** — A neural network consists of an input layer (receives raw data), one or more hidden layers (learn intermediate representations), and an output layer (produces predictions). Deep learning refers specifically to networks with multiple hidden layers.

- **Weights** — Learnable numerical parameters on the connections between nodes in a neural network; training adjusts these weights iteratively to minimise prediction error. Weights are learned from data, unlike hyperparameters which are set before training.

- **Backpropagation** — The core learning algorithm that propagates prediction error backward through the network layers, computing gradients and adjusting weights to reduce the loss on the next forward pass. Feed-forward prediction and backpropagation learning are separate sequential phases.

- **Loss Function** — A mathematical function that quantifies the difference between the model's predictions and the ground truth labels; training aims to minimise this value. Lower loss indicates better model fit, but very low training loss with high test loss signals overfitting.

- **Activation Function** — A mathematical function applied to a neuron's output that introduces non-linearity, enabling the network to learn complex, non-linear relationships that stacked linear transformations alone cannot capture.

- **Feature** — A measurable characteristic or input variable extracted from raw data and provided to the model as input; feature quality and engineering strongly influence model performance. Labels are the targets to predict; features are the inputs.

- **Label** — The target value or category that a supervised model is trained to predict; labels are known during training but typically unknown at inference time for new incoming data.

- **Ground Truth** — A properly labelled dataset that serves as the objective reference standard for training or evaluating a model; poor-quality labels directly produce poor-quality models regardless of algorithmic sophistication.

- **Feature Engineering** — The process of creating, selecting, transforming, or encoding input features from raw data to improve model learning and predictive performance; includes techniques like one-hot encoding, normalisation, and interaction features.

- **One-hot Encoding** — Converts categorical variable values into binary indicator columns so ML algorithms can process nominal categories that have no inherent ordinal relationship.

- **Normalisation** — Scales numeric feature values to a common range (e.g. 0–1) to ensure no single feature dominates training due to magnitude differences, improving training stability and convergence speed.

- **Standardisation** — Transforms numeric features to have mean 0 and standard deviation 1 (z-score scaling), making features comparable and improving the behaviour of distance-based and gradient-based algorithms.

- **Model Parameters** — The internal learned values — primarily weights and biases — that define the model's behaviour after training is complete. Parameters are learned from training data, as opposed to hyperparameters which are configured externally.

- **Hyperparameters** — Configuration values set by the practitioner before or during training, such as learning rate, batch size, number of epochs, number of layers, and regularisation strength. They are not directly learned from training data.

- **Overfitting** — When a model performs very well on training data but poorly on unseen data because it has memorised noise, outliers, or specific training examples rather than learning generalisable patterns. High training accuracy alone does not confirm good generalisation.

- **Underfitting** — When a model is too simple or insufficiently trained to capture the underlying pattern in data, leading to poor performance on both training and test data. Adding more training data alone may not fix a fundamentally underpowered model architecture.

- **Inference** — The act of feeding new, unseen data to a trained model to obtain a prediction or generated output. Inference is fundamentally different from training; AWS services expose distinct infrastructure options for each.

- **Batch Inference** — Running predictions across a large collection of records offline, usually on a schedule, without requiring a persistent endpoint; highly cost-effective for bulk workloads where immediate response is not needed.

- **Real-time Inference** — Serving predictions with very low latency via a persistent, always-on endpoint; best suited for live user-facing applications where response delay is unacceptable, though at higher ongoing infrastructure cost.

- **Serverless Inference** — Deploying ML inference without provisioning or managing servers; automatically scales up and down to zero when idle, billed per request; ideal for intermittent or unpredictable traffic but carries cold-start latency risk.

- **Endpoint** — A deployed model interface — typically a REST API — that applications call to submit input data and receive inference predictions or generated output.

- **Latency** — The elapsed time from when a request is submitted to when the response is returned; influenced by model size, token count, infrastructure region, and serving architecture. Critical selection criterion for real-time use cases.

- **Throughput** — The number of requests or units of work a system can process in a given time window; a key scaling consideration for production ML systems under concurrent load.

---

### Model Evaluation Metrics

- **Confusion Matrix** — A table that counts true positives, true negatives, false positives, and false negatives for a classification model, providing the raw foundation from which precision, recall, F1, and accuracy are derived.

- **Precision** — Of all items the model predicted as positive, the fraction that were actually positive (TP / TP + FP); prioritise precision when false positives are costly, such as in content moderation or spam flagging.

- **Recall (Sensitivity)** — Of all actual positive cases in the data, the fraction the model successfully identified (TP / TP + FN); prioritise recall when false negatives are costly, such as in disease detection or fraud identification.

- **F1 Score** — The harmonic mean of precision and recall, balancing both metrics into a single number; particularly useful when class distributions are imbalanced and accuracy alone would be misleading.

- **Regression Metrics** — Common metrics for numeric prediction tasks include Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE). These are not appropriate for categorical classification outcomes.

- **Confidence Score** — A numeric estimate of how certain the model is about a prediction; commonly used with thresholds to trigger human escalation when confidence falls below an acceptable level. Scores must be calibrated and validated — raw scores are not always reliable.

---

### Data Concepts & Pipeline

- **Structured Data** — Neatly organised, tabular data with clearly defined fields and schemas, such as sales records, spreadsheets, or sensor readings; straightforward to query with SQL and process with traditional ML algorithms.

- **Unstructured Data** — Data with no predefined format, including text, images, audio, and video; represents the vast majority of data generated in the world and typically requires deep learning or NLP techniques to process.

- **Training / Validation / Test Sets** — The standard three-way data split: training teaches the model, validation is used to tune hyperparameters and detect overfitting during development, and the test set provides a completely unbiased final performance estimate on unseen data.

- **Data Quality (4 Vs)** — Volume (sufficient data for learning), Variety (diverse data reduces bias), Veracity (accuracy and trustworthiness of data), and Velocity (the rate at which new data is generated and must be processed).

- **Data Quality Attributes** — Completeness, accuracy, consistency, freshness, and relevance are the key properties that determine whether a dataset is fit for purpose in AI/ML workflows.

- **Synthetic Data** — Artificially generated data used to augment training datasets, simulate rare scenarios, or replace real sensitive data for testing; must be validated carefully for bias, realism, and potential quality issues.

- **Data Wrangling** — The process of cleaning, transforming, restructuring, and organising raw data into a format suitable for analysis or model training; performed before modelling using tools like SageMaker Data Wrangler or AWS Glue DataBrew.

- **Data Modeling** — Defining and structuring data requirements, relationships, and schemas to support business processes and downstream systems; distinct from ML model training.

- **Data Analytics** — Examining, transforming, and interpreting data to discover patterns, validate hypotheses, and support business decisions; broader in scope than ML and served by tools like Athena, QuickSight, and Glue.

- **Data Mining Phases (CRISP-DM)** — Business understanding, data understanding, data preparation, modelling, evaluation, and deployment — a structured process for analytics and ML projects. Modelling should never begin before understanding the business problem and data.

- **Data Lineage** — Tracking the origin, movement, transformation, and consumption of data through the full pipeline; essential for governance, auditability, debugging model behaviour, and regulatory compliance.

- **Data Lake** — A centralised repository built on object storage (typically Amazon S3) that stores structured, semi-structured, and unstructured data at scale as a foundation for analytics and ML workloads.

- **Data Catalog** — A metadata repository that stores schema, type, and location information about data assets; AWS Glue Data Catalog is shared by Glue, Athena, and Lake Formation.

- **Crawler Schema Inference** — An AWS Glue Crawler automatically scans data sources, infers the schema from the data format, and writes updated metadata to the Glue Data Catalog without manual schema definition.

- **Evaluation Dataset** — A representative, held-out set of labelled examples used to compare models, prompts, or RAG configurations against quality and business metrics before production deployment.

- **A/B Testing** — A controlled experiment comparing two model, prompt, or application variants against measurable business or quality metrics to determine which performs better in production conditions.

- **Validation Set** — A subset of labelled data held aside during training used to compare candidate models or hyperparameter configurations without contaminating the final test set evaluation.

- **Train/Test Split** — The fundamental practice of partitioning a labelled dataset into separate portions for model training and unbiased final evaluation, preventing information leakage between the two.

- **Knowledge Mining** — Using AI and ML services to extract, structure, and make searchable the knowledge embedded in large unstructured document corpora; overlaps conceptually with RAG retrieval patterns.

- **Metadata Filtering** — Using structured attributes such as document type, owner, date, or department tag to narrow retrieval results and improve the precision of search or RAG pipelines beyond pure semantic similarity.

---

### Classical vs Deep Learning vs GenAI

- **Classical ML** — Well-suited when data is relatively tabular and structured, features are interpretable, the dataset is moderate in size, and cost-efficiency is prioritised; covers algorithms for classification, regression, clustering, association, and forecasting. Avoid defaulting to deep learning when simpler approaches fit the problem.

- **Deep Learning** — The appropriate choice when dealing with high-dimensional, unstructured, or complex data like images, audio, video, or raw text; typically requires significantly more data and compute than classical ML.

- **Jupyter Notebook** — A web-based interactive environment that combines live executable code, narrative text, mathematical equations, and visualisations in a single document; the standard tool for ML experimentation and exploration, deeply integrated with SageMaker Studio.

- **Anomaly Detection vs Forecasting** — Forecasting predicts future numeric values in a time series; anomaly detection flags observations that are statistically unusual relative to the expected distribution. They serve different analytical purposes and use different algorithms.

- **Recommendation Engine** — A system that uses patterns in historical user behaviour and item attributes to suggest relevant items, content, or actions; implemented with Amazon Personalize for managed recommendations.

---

## D2 · Generative AI Fundamentals (24%)

### Core GenAI Concepts

- **Token** — A unit of text processed by an LLM, which may be a word, sub-word piece, character, or punctuation mark depending on the tokeniser; tokens directly drive context window capacity, inference latency, and API cost. More tokens generally means higher cost and slower response.

- **Context Window** — The maximum total number of input plus output tokens a model can process and attend to within a single request; critical for long-document analysis, multi-turn chat, and RAG scenarios where retrieved context must fit alongside the user query.

- **Embedding** — A dense numeric vector representation of text, image, or other data that encodes semantic meaning in a high-dimensional space; items with similar meaning produce vectors that are numerically close, enabling similarity search and retrieval. Embeddings are not summaries — they are mathematical representations.

- **Vector Database** — A specialised database designed to store embedding vectors at scale and perform fast approximate nearest-neighbour (similarity) search to retrieve semantically relevant content for RAG and recommendation systems.

- **Vector Similarity** — A measure of how semantically related two items are by computing the geometric distance or angle between their embedding vectors; close vectors indicate related meaning regardless of surface-level keyword overlap.

- **Multimodal Model** — A model capable of processing or generating across multiple content types — such as text, images, audio, or video — in a single unified architecture; text-only LLMs are not multimodal.

- **Model Distillation** — Training a smaller, faster, and cheaper student model to approximate the behaviour of a larger, more capable teacher model; reduces inference cost and latency while attempting to preserve most of the performance gains.

- **Model Artifact** — The saved output of a completed training job — including weights, configuration, and vocabulary — that is loaded later for deployment and inference.

---

### Model Customisation Spectrum

- **Pre-training** — Training a foundation model from scratch on massive broad datasets; extremely expensive in compute, time, and data; almost never the appropriate choice for typical business use cases. For exam scenarios, pre-training is rarely the cost-effective answer.

- **Fine-tuning** — Further training a pre-trained foundation model on task-specific labelled data to specialise its behaviour, tone, domain vocabulary, or output structure; appropriate when specific brand voice or consistent behavioural patterns are needed, but not the first choice for simply adding frequently changing facts.

- **Continued Pre-training** — Extending the pre-training process using large amounts of unlabelled domain-specific text to deepen the model's general knowledge of a particular domain (e.g. legal, medical, financial); uses unlabelled data as opposed to fine-tuning's labelled task data.

- **In-context Learning** — The model adapts its responses based on instructions and examples provided directly within the prompt, without any update to model weights; a powerful, cost-free alternative to fine-tuning for many tasks.

- **RAG (Retrieval Augmented Generation)** — Retrieves relevant external knowledge chunks and injects them into the model's prompt so it can generate factually grounded answers without retraining; directly addresses the hallucination problem and is usually cheaper and faster to update than fine-tuning.

- **Model Customisation Cost Order** — From generally lowest to highest cost: prompt engineering / in-context learning → RAG → fine-tuning → continued pre-training → training from scratch. Use the cheapest approach that meets the quality requirement.

---

### RAG Deep Dive

- **RAG Steps (Typical Flow)** — Ingest documents → chunk content into digestible pieces → generate embeddings for each chunk → store vectors in a vector database → on user query, embed the question → retrieve top semantically matching chunks → inject retrieved context into the prompt → generate a grounded answer with citations. Always retrieve before generating.

- **Chunking Strategy** — The approach to splitting source documents into segments before embedding; chunk size and overlap directly affect retrieval quality — too large loses precision, too small loses context. Choosing the right chunking strategy is a key RAG design decision.

- **Groundedness** — The degree to which a generated answer is supported by and traceable to the retrieved source evidence; a key quality metric for RAG systems alongside accuracy and completeness.

- **Hallucination** — When a model generates plausible-sounding but factually incorrect or entirely fabricated information with apparent confidence; mitigated by RAG, guardrails, grounding evaluation, and human review, though not eliminated entirely.

- **Citation / Source Attribution** — Returning references to the specific source documents or passages that supported a generated answer; improves user trust, auditability, and factual accountability in RAG applications.

- **Hybrid Search** — Combining semantic vector search with traditional keyword (BM25-style) matching in a single retrieval query, improving both recall (finding more relevant chunks) and precision (filtering irrelevant ones).

- **Access Control for RAG** — Ensuring users can only retrieve and receive answers based on documents they are authorised to access; permissions must be enforced at the retrieval layer, not just at the application UI level.

---

### Prompt Engineering

- **Prompt Engineering** — The practice of designing, structuring, and refining the instructions and context provided to a GenAI model to consistently produce desired, high-quality outputs; a skill that can dramatically improve results without any model training.

- **System Prompt** — A high-priority set of instructions provided to the model before the user interaction begins, defining the model's role, behavioural guidelines, constraints, persona, and safety boundaries; user prompts should not be able to override trusted system instructions.

- **Zero-shot Prompting** — Asking the model to perform a task with a clear instruction but no examples; works reliably for simple, well-known tasks where the model's training already covers the required behaviour.

- **Few-shot Prompting** — Providing two to five worked examples within the prompt to demonstrate the expected input-output pattern; most effective for complex, nuanced, or domain-specific output formats. Few-shot is in-context learning — it does not update model weights.

- **Chain-of-thought Prompting** — Instructing the model to reason through a problem step by step before producing a final answer; significantly improves accuracy on logic, mathematics, and multi-step reasoning tasks.

- **Negative Prompting** — Explicitly telling the model what to avoid or exclude in its response, in addition to what to include; effective for preventing common errors, off-topic diversions, or unwanted formats.

- **Role-based Prompting** — Assigning the model a specific expert persona before asking a question (e.g. "You are a senior financial adviser"); focuses the model's response style and vocabulary toward domain-appropriate depth.

- **Prompt Chaining** — Decomposing a complex task into a sequence of smaller, focused sub-prompts where each output feeds into the next step; keeps individual responses accurate and manageable while enabling sophisticated multi-stage workflows.

- **Prompt Templates** — Reusable, parameterised prompt structures that enforce consistency, improve maintainability, and make it easier to test and iterate on prompt changes across an application.

- **Prompt Versioning** — Tracking prompt changes systematically so that regressions in model output quality can be diagnosed, attributed to specific prompt changes, and rolled back if needed.

- **Temperature** — A sampling parameter (0.0–1.0) controlling output randomness; low values produce deterministic, conservative responses while high values produce more varied and creative outputs. Temperature controls creativity, NOT speed — a common exam trap.

- **Top-p (Nucleus Sampling)** — Restricts the model to sample from the smallest set of candidate tokens whose cumulative probability reaches the value p; lower values constrain vocabulary, higher values allow more diverse word choice. Usually tuned alongside temperature, not both set aggressively at once.

- **Max Tokens** — Sets the upper bound on how many tokens the model will generate in a single response; a key lever for controlling API cost, enforcing response length, and staying within context window limits.

- **Stop Sequences** — Specific strings or characters that, when generated by the model, immediately halt further output; used to enforce clean output boundaries like stopping after a closing XML tag or delimiter character.

---

### GenAI Risks & Attacks

- **Prompt Injection** — An attack where malicious input embedded in a user message or retrieved document attempts to override the model's original instructions, alter its behaviour, or exfiltrate information. "Ignore previous instructions" is a classic pattern.

- **Direct Prompt Injection** — The attacker's malicious instructions are contained directly in the user's own input to the model, attempting to override system prompt behaviour.

- **Indirect Prompt Injection** — Malicious instructions are hidden within external content that the model retrieves or processes — such as a web page, uploaded document, email, or database record — allowing attacks without direct user interaction. Particularly relevant for RAG and agent architectures.

- **Prompt Injection Mitigations** — Separate trusted system instructions from untrusted external content; apply input and output filtering; enforce least-privilege permissions on tools and APIs the model can invoke; validate all tool calls; use guardrails and human review for high-stakes actions.

- **Toxicity** — Harmful, abusive, offensive, or unsafe content generated by the model; mitigated by aggressive content filtering and guardrails applied at both input ingestion and output generation stages.

---

### GenAI Business Context

- **Business Metrics for GenAI** — Evaluating GenAI applications requires business-level metrics including ROI, efficiency gains, conversion rate, average revenue per user, accuracy, customer lifetime value, speed to market, and alignment with specific business objectives — not just technical model scores.

- **GenAI Value Proposition (Managed Services)** — Using managed AWS GenAI services delivers lower barrier to entry, faster time to market, managed infrastructure and scaling, built-in security integration, multi-model access, and avoidance of deep ML expertise requirements. Being managed does not remove all customer responsibilities.

- **Monitoring Token Usage** — Actively tracking token consumption across requests is essential for managing inference cost, enforcing usage quotas, avoiding unexpected billing, and optimising prompt design for efficiency.

---

## D3 · Foundation Model Applications & AWS Services (28%)

### Amazon Bedrock Ecosystem

- **Amazon Bedrock** — A fully managed, serverless AWS platform that provides API access to multiple foundation models from different providers, alongside managed capabilities for knowledge bases (RAG), agents, guardrails, model evaluation, and fine-tuning — all with enterprise-grade security and pay-as-you-go billing.

- **Bedrock Model Selection** — When choosing a foundation model in Bedrock, evaluate: task fit and modality, accuracy, latency, cost per token, context window length, customisation support, compliance requirements, and regional availability. Bigger model is not always the right choice.

- **Bedrock Knowledge Bases** — Managed RAG capability within Bedrock that handles document ingestion, chunking, embedding, vector storage, and retrieval; connects to data sources like S3, Confluence, SharePoint, and Salesforce to ground model responses in private or current data.

- **Bedrock Agents** — Orchestrate multi-step, goal-directed tasks by coordinating a foundation model, a set of instructions, action groups (external APIs/tools via Lambda), and knowledge bases; capable of breaking complex user requests into sub-tasks and executing them sequentially.

- **Bedrock Guardrails** — Configurable safety controls applied at the Bedrock layer that filter harmful content, block denied topics, detect and redact sensitive information (PII), and defend against prompt injection; reduces risk but does not replace full application-level security.

- **Bedrock Model Evaluation** — A capability for systematically comparing model outputs against defined quality criteria — including accuracy, toxicity, robustness, and task-specific performance — using automated scoring or human reviewers, supporting evidence-based model selection.

- **Bedrock Customisation Options** — Encompasses prompting, RAG via Knowledge Bases, fine-tuning (where supported per model), continued pre-training (where supported), and model distillation; RAG should be evaluated before fine-tuning for knowledge-grounding use cases.

- **PartyRock** — A no-code, browser-based Bedrock playground for building and sharing GenAI-powered applications through drag-and-drop composition; designed for rapid prototyping and demos, not production enterprise ML pipelines.

---

### Amazon Q Family

- **Amazon Q Business** — A GenAI assistant for enterprise business users that answers questions by searching company documents and systems, summarises content, automates tasks, enforces access-based permissions, and delivers enterprise-grade search across connected data sources.

- **Amazon Q Developer** — A GenAI-powered coding assistant that helps developers write, complete, and debug code, design AWS cloud architectures, apply security best practices, and optimise infrastructure costs, integrated into IDEs and the AWS console.

---

### New/Updated Guide Services

- **Kiro** — An AWS AI-enabled development tool referenced in the updated AIF-C01 exam guide for building GenAI and software development workflows; recognise it as a GenAI-assisted development environment.

- **Strands Agents** — An AWS-supported open-source agent SDK and framework area referenced in the updated exam guide for building agentic AI applications; likely tested at recognition level, not deep implementation detail.

- **Amazon Bedrock AgentCore** — A Bedrock capability area for building, deploying, securing, and operating agents, including identity management and policy enforcement concepts; treat as the operational and security infrastructure layer for Bedrock agents.

---

### Amazon SageMaker AI Platform

- **Amazon SageMaker AI** — AWS's flagship managed ML platform covering the complete lifecycle from data preparation and feature engineering through model building, training, hyperparameter tuning, deployment, and ongoing monitoring; not limited to GenAI workloads.

- **SageMaker Studio** — An integrated, browser-based ML IDE providing a unified interface for Jupyter notebooks, experiment tracking, training job management, model deployment, and workflow orchestration with collaboration support.

- **SageMaker JumpStart** — A hub of pre-built ML solutions, foundation models, curated notebooks, and end-to-end examples that accelerate model development and GenAI adoption; does not function as a data warehouse or inference endpoint itself.

- **SageMaker Data Wrangler** — A visual, low-code data preparation tool with 300+ built-in transformations, data quality profiling, bias detection, and export options; used in the data preparation stage of the ML pipeline, not for inference hosting.

- **SageMaker Feature Store** — A centralised online-and-offline repository for storing, sharing, versioning, and reusing ML features across teams and models; ensures consistency between training and serving feature pipelines. Not a document retrieval service.

- **SageMaker Ground Truth** — A managed data labelling service that combines human annotators (internal teams, vendors, or Amazon Mechanical Turk crowdworkers) with automated active learning to progressively reduce labelling cost as confidence grows.

- **SageMaker Autopilot** — An AutoML capability within SageMaker that automatically explores data, selects algorithms, trains, and tunes models based on your dataset and target objective, with full transparency into generated notebooks and pipelines.

- **SageMaker Canvas** — A no-code, point-and-click AutoML interface designed for business analysts and non-technical users to build predictive models and generate forecasts without writing any code; note potential cost exposure from compute resources left running.

- **SageMaker Clarify** — Detects statistical bias in training data and trained models, explains individual model predictions using feature attribution methods (SHAP), and monitors for fairness drift and explainability changes post-deployment. Not used for content filtering — that is Guardrails.

- **SageMaker Model Monitor** — Continuously monitors deployed model endpoints for data quality drift, model quality degradation, bias drift, and feature attribution drift; sends alerts when metrics deviate from baselines established at deployment time. Monitoring occurs after deployment.

- **SageMaker Model Cards** — Structured documentation artefacts that capture a model's purpose, intended use cases, risk rating, evaluation results, and governance information; improve transparency and support auditability. Model cards document — they do not enforce runtime controls.

- **SageMaker Pipelines** — Workflow orchestration for ML as directed acyclic graphs (DAGs) with defined steps and dependencies; enables automated, repeatable CI/CD-style ML pipelines with Git integration and step-level monitoring.

- **SageMaker Model Registry** — A centralised catalogue for tracking, versioning, approving, and managing model deployments across environments; supports MLOps governance and controlled promotion from development to production.

---

### Text & Language Services

- **Amazon Comprehend** — A managed NLP service that extracts insights from text including sentiment, named entities (people, places, organisations), key phrases, language detection, topic modelling, PII identification, and custom classification/entity recognition — without requiring ML expertise.

- **Amazon Comprehend Medical** — A specialised variant of Comprehend that extracts clinically relevant information — medical conditions, medications, dosages, and protected health information (PHI) — from unstructured clinical notes and EHR text, without requiring custom training data.

- **Amazon Translate** — A neural machine translation service that converts text between 75+ language pairs in real time or batch mode, with support for custom terminology to preserve domain-specific brand terms or product names accurately.

- **Amazon Transcribe** — An automatic speech recognition (ASR) service that converts speech and audio recordings to text in real time or batch mode; supports speaker identification, custom vocabularies, and a dedicated medical version for clinical transcription. Do not confuse with Translate, which handles language translation.

- **Amazon Polly** — A managed text-to-speech service that converts written text into natural, lifelike speech across 60+ voices and 29+ languages, with SSML support for pronunciation control and neural voice options for enhanced realism. Polly speaks — Transcribe listens.

- **SSML in Polly** — Speech Synthesis Markup Language tags embedded in text allow precise control over Polly's output, including pronunciation, pauses, pitch, emphasis, speaking rate, and voice style for more natural-sounding audio.

---

### Vision & Conversational Services

- **Amazon Rekognition** — A managed computer vision service for image and video analysis; detects objects, scenes, activities, text, faces, celebrities, and inappropriate content; supports custom label training for domain-specific visual recognition tasks. Use Textract for structured document extraction, not Rekognition.

- **Rekognition Custom Labels** — An extension of Rekognition that allows you to train domain-specific custom image classifiers on your own labelled image data for use cases not covered by the built-in label detection models.

- **Amazon Lex** — A managed conversational AI service for building chatbots and voice assistants using natural language understanding; models user intents, captures slot values, and integrates with Lambda for business logic and with Alexa for voice deployment.

- **Lex Intent** — A defined goal or action that a user wants to accomplish in a Lex conversation, such as BookFlight, OrderPizza, or GetAccountBalance; intents are the core building blocks of a Lex chatbot.

- **Lex Slot** — A named data field that must be collected to fulfil an intent; for example, the BookFlight intent might require slots for destination, departure date, and passenger count.

---

### Search, Recommendations & Forecasting

- **Amazon Kendra** — A managed enterprise intelligent search service powered by ML and NLP that understands natural language questions, returns ranked relevant results from connected content repositories, and learns from user feedback over time. For GenAI answer generation over documents, Bedrock Knowledge Bases is the complement.

- **Kendra Connectors** — Pre-built integrations that allow Kendra to crawl and index content from enterprise sources including SharePoint, Confluence, Salesforce, ServiceNow, S3, and databases.

- **Amazon Personalize** — A managed real-time recommendation service that trains and hosts personalised recommendation models using your own user-item interaction data, without requiring ML expertise; ideal for e-commerce product recommendations, content personalisation, and next-best-action use cases.

- **Amazon Forecast** — A managed time-series forecasting service that automates feature engineering, identifies seasonality and trends, and trains accurate forecasting models; suited for demand planning, inventory optimisation, and capacity forecasting. Not the same as general regression in SageMaker.

---

### Specialised AI Services

- **Amazon Fraud Detector** — A managed service for building and deploying real-time fraud detection models using built-in fraud-specific ML templates or custom models trained on your own transaction history; plugs directly into payment and account workflows.

- **Amazon Textract** — An OCR-plus service that extracts not just raw text but also structured data from forms, tables, and key-value pairs in scanned documents and PDFs; purpose-built for document digitisation and forms processing. Do not use Rekognition for structured document field extraction.

- **Textract AnalyzeDocument** — The Textract API operation that analyses a document image or PDF and returns the extracted text, detected form fields/values, and table structure with cell relationships.

- **Amazon HealthLake** — A HIPAA-compliant, FHIR-enabled health data store and analytics service that aggregates, normalises, and structures health data from multiple sources; supports NLP on clinical records and prepares healthcare data for downstream ML and analytics.

- **Amazon Mechanical Turk** — A crowdsourcing marketplace that can support human annotation and labelling tasks (e.g. for SageMaker Ground Truth workflows), but is not a managed ML training or inference service.

---

### Data, Storage & Analytics Services

- **Amazon S3 for Data Lakes** — Object storage widely used as the foundational storage layer for data lakes, ML training datasets, model artefacts, RAG document corpora, and batch inference inputs/outputs in AWS AI/ML architectures.

- **AWS Glue** — A serverless, fully managed ETL and data integration service featuring crawlers for schema discovery, the Data Catalog for centralised metadata, and Spark-based jobs for transforming and moving data at scale across sources.

- **Glue Crawler** — An automated schema discovery component that scans data sources (S3, databases, etc.), infers data formats and schemas, and registers or updates the metadata in the Glue Data Catalog. Crawlers catalogue metadata — they do not train models.

- **Glue Data Catalog** — A centralised metadata repository shared by AWS Glue, Amazon Athena, Amazon EMR, and AWS Lake Formation, storing table schemas, partition details, and data location information.

- **Amazon Athena** — A serverless, interactive SQL query service that runs queries directly against data stored in S3 without requiring a database server; ideal for ad-hoc analytics and data exploration in a data lake architecture. Athena queries; Glue transforms.

- **Athena Workgroup** — An organisational unit within Athena that controls query execution settings, output locations, data usage limits, and cost tracking, enabling multi-team governance of query access and spend.

- **AWS Lake Formation** — A service for building, securing, and governing data lakes on S3, providing column- and row-level access control, permission management, and integration with the Glue Data Catalog.

- **Amazon OpenSearch Service** — A managed search and analytics engine supporting both text (keyword/BM25) and vector (approximate nearest-neighbour) search; frequently used as the vector store in RAG architectures and for log analytics.

- **OpenSearch Vector Search** — A capability of Amazon OpenSearch Service that stores embedding vectors and performs approximate nearest-neighbour similarity search, enabling semantic retrieval for RAG pipelines alongside traditional keyword search.

---

### Monitoring & Operations Services

- **Amazon CloudWatch for AI Apps** — The primary AWS observability service for monitoring application logs, custom metrics, latency, error rates, and usage patterns for AI/ML applications; supports alarms, dashboards, and automated responses.

- **AWS CloudTrail for Governance** — Records every API call made across AWS services, capturing who performed what action, when, and from where; the essential audit trail for compliance, security investigations, and AI governance frameworks.

- **AWS Secrets Manager** — Securely stores sensitive credentials such as API keys, database passwords, and authentication tokens, with automated rotation and fine-grained access policies; never hardcode secrets in prompts, notebooks, or code repositories.

- **VPC Endpoints** — Private network connectivity constructs (powered by AWS PrivateLink) that allow resources within a VPC to access AWS services without traversing the public internet; reduces attack surface for AI workloads handling sensitive data.

---

### Key Use Case Mappings

- **Document Q&A (Private Docs)** — Use RAG with Amazon Bedrock Knowledge Bases over your document corpus; do not fine-tune purely to add private knowledge unless the use case additionally requires specific behavioural adaptation.

- **Sentiment Analysis** — Amazon Comprehend for managed, purpose-built text sentiment analysis; Amazon Bedrock if custom GenAI-based analysis or generation is required alongside sentiment.

- **Contact Centre Audio Analytics** — Amazon Transcribe (speech to text) → Amazon Comprehend or Bedrock (analyse/summarise) → Amazon Polly if audio responses needed → Amazon Lex for chatbot-style flows; add Translate only if language conversion is required.

- **Invoice / PDF Field Extraction** — Amazon Textract; specifically the AnalyzeDocument API for forms and tables. Do not route structured document extraction through Rekognition.

- **Image / Video Content Moderation** — Amazon Rekognition for detecting unsafe or inappropriate visual content in images and video streams; Bedrock Guardrails manages FM input/output text safety, not raw image moderation.

- **Enterprise Document Search** — Amazon Kendra for intelligent search returning ranked results; Bedrock Knowledge Bases for generated natural language answers grounded in retrieved content. Search returns results; RAG generates answers.

---

## D4 · Responsible AI (14%)

### The Eight Pillars

- **Fairness** — AI systems should avoid unjust bias and discriminatory outcomes across all demographic groups; requires diverse and representative training data, inclusive development teams, and regular bias testing with mitigation measures.

- **Explainability** — Users, operators, and affected stakeholders should be able to understand why the model produced a given output; requires interpretability tools, human-centred explanation design, and documentation of decision logic.

- **Privacy & Security** — Data and model interactions must protect sensitive and personal information through access controls, encryption, data minimisation, and secure training and deployment practices.

- **Safety** — AI systems should behave reliably and predictably; avoid generating harmful or dangerous outputs; fail gracefully under unexpected inputs; and maintain human oversight mechanisms for high-risk decisions.

- **Controllability** — Humans and organisations must be able to meaningfully guide, constrain, override, and shut down AI system behaviour; boundaries must be explicitly defined and enforced with escalation paths.

- **Veracity & Robustness** — Outputs should be factually accurate and reliable; systems should perform consistently across edge cases, resist adversarial attacks, handle distribution shift gracefully, and avoid hallucination.

- **Governance** — Clear accountability structures, defined ownership, regular internal audits, documentation of AI development decisions, and adherence to applicable legal and ethical frameworks must be established and maintained.

- **Transparency** — Users should be clearly informed when they are interacting with AI, what the system's capabilities and limitations are, how it makes decisions, and what data it uses; AI impact should be reported publicly where appropriate.

---

### Bias & Fairness

- **Bias in ML/AI** — Systematic unfairness or skew in data, model behaviour, or outcomes that disadvantages certain groups or produces unreliable decisions; can be introduced at data collection, feature engineering, model training, or post-deployment stages.

- **SageMaker Clarify Role** — AWS's primary service for detecting and measuring statistical bias in training datasets and trained models, providing SHAP-based feature attribution explanations, and monitoring for fairness drift over time in production. Do not choose Guardrails for model bias quantification.

- **Human-centred Explainability** — Explanations of AI system behaviour should be designed to be genuinely understandable and actionable for the people affected by or operating the system, not just technically interpretable to ML practitioners.

---

### Monitoring & Governance

- **Model Drift** — The phenomenon where a deployed model's predictive performance degrades over time because real-world data patterns or relationships change after training; requires ongoing monitoring with SageMaker Model Monitor and periodic retraining.

- **Data Lineage** — Comprehensive tracking of where data originated, how it was transformed across pipeline stages, and what model outputs it contributed to; fundamental for debugging model behaviour, meeting regulatory requirements, and supporting governance audits.

- **Model Cards** — Structured documentation artefacts capturing a model's intended purpose, performance evaluation results, risk rating, limitations, and governance metadata; improve transparency and accountability. Model cards document context — they do not enforce runtime behaviour.

- **Human-in-the-loop** — The practice of routing model outputs to human reviewers for validation or correction, particularly for high-risk, ambiguous, regulated, or sensitive decisions where full automation introduces unacceptable risk. Automation should not eliminate accountability.

- **Amazon Augmented AI (A2I)** — A managed service for building human review workflows into ML prediction pipelines; routes low-confidence or high-risk predictions to human reviewers according to configurable thresholds and custom review interfaces.

---

### Guardrails vs Clarify (Critical Distinction)

- **Guardrails vs Clarify** — Bedrock Guardrails is an input/output safety control for FM application interactions — filtering harmful content, denied topics, and PII in real time. SageMaker Clarify is an analytical tool for detecting bias and explaining predictions in ML model training and monitoring. They solve fundamentally different problems and should not be substituted for each other.

---

### Pre-production & Sensitive Data

- **Evaluation Before Production** — Before releasing a GenAI application, systematically evaluate: task accuracy, groundedness/factuality, toxicity and safety, bias metrics, adversarial robustness, latency, cost, privacy controls, and alignment with business success metrics. Demo quality alone is insufficient.

- **Responsible AI Risk Assessment** — For each AI use case, identify: the population of affected users, sensitivity of data involved, severity and probability of failure modes, required control mechanisms, and applicable regulatory obligations.

- **Sensitive Data in Model Output** — If a model reveals confidential or sensitive training data in its outputs, the correct remediation is to remove the sensitive data from the training dataset and retrain; additionally strengthen data governance, input filtering, and output monitoring. Masking output does not remove learned sensitive patterns.

- **PII Handling** — Before using data containing personally identifiable information in AI training or RAG pipelines, classify the data, minimise or remove unnecessary PII fields, apply access permissions, encrypt data at rest and in transit, monitor for exposure, and obtain legal/compliance approval.

---

## D5 · Security, Compliance & Governance (14%)

### Foundations

- **Shared Responsibility for AI** — AWS secures the cloud infrastructure and the managed service foundation layers; the customer remains responsible for data governance, access control configuration, prompt design, model outputs, application logic, compliance use, and appropriate use of AI capabilities.

- **IAM Least Privilege** — AI applications, agents, notebooks, and Lambda functions should be granted only the minimum permissions required to perform their specific tasks; never assign broad administrative access to AI-adjacent compute or inference roles.

- **Encryption** — Encryption must be considered for data at rest (S3, vector stores, model artefacts, logs), data in transit (API calls, inter-service communication), and sensitive outputs; AWS KMS provides centralised key management for most AWS services.

---

### Data Protection Services

- **AWS KMS** — The AWS Key Management Service provides centralised, HSM-backed encryption key management with automated rotation, seamless integration across AWS services, and support for both symmetric and asymmetric keys protecting data at rest and in transit.

- **Amazon Macie** — An ML-powered managed service that automatically discovers, classifies, and alerts on sensitive data (particularly PII and credentials) stored in Amazon S3 buckets; supports compliance with data privacy regulations. Macie is a data discovery tool, not an AI inference service.

- **AWS Secrets Manager** — Securely centralises storage of sensitive credentials including API keys, database passwords, OAuth tokens, and SSH keys, with automated credential rotation and fine-grained IAM-based access control and full CloudTrail audit integration.

---

### Network & Application Security

- **AWS PrivateLink** — A managed network connectivity service enabling private access to supported AWS services (including Bedrock and SageMaker) from within a VPC without traffic traversing the public internet, significantly reducing the network attack surface for AI workloads. PrivateLink provides a private network path — it does not replace IAM authorisation or sanitise model inputs.

- **VPC Endpoints** — Interface or gateway endpoints implemented using AWS PrivateLink that allow VPC-hosted resources to privately connect to AWS services; a common security architecture pattern for AI workloads handling sensitive regulated data.

---

### Logging, Audit & Compliance

- **CloudTrail for Governance** — Records all AWS API activity with immutable logs including caller identity, timestamp, source IP, and affected resource; the primary audit trail for AI system governance, compliance evidence, and security incident investigation.

- **CloudWatch for AI Apps** — Provides real-time log aggregation, custom metric publishing, alerting, and dashboards for monitoring AI application behaviour, latency, error rates, token usage, and cost patterns.

- **Logging & Audit** — AI application activity logging supports monitoring for safety, auditability for compliance, incident response readiness, troubleshooting, cost analysis, and governance evidence. Exercise care not to log sensitive prompt content or PII without appropriate access controls on log storage.

- **Compliance Documentation** — A comprehensive compliance posture requires model cards, data lineage records, evaluation reports, access policy documentation, risk assessments, human review records, and change history — compliance is both evidence and process, not just technical controls.

---

### AI-specific Security

- **Agent Security** — Agents with tool/API access introduce elevated risk because excessive permissions or successful prompt injection can cause unauthorised actions, data exposure, or unintended side effects; enforce least-privilege on every action group and validate all tool invocations.

- **Input Filtering** — Proactively scanning and validating inputs to GenAI applications to detect malicious prompt patterns, PII, unsafe requests, or content violating policy; input filtering is a necessary complement to output filtering but cannot stop all indirect prompt injection.

- **Output Filtering** — Inspecting and sanitising model-generated responses before delivering them to users or triggering downstream actions; reduces harmful, unsafe, sensitive, or policy-violating outputs while complementing input controls and model-level guardrails.

- **Data Minimisation** — The principle of collecting and retaining only the data strictly necessary for the defined purpose; reduces privacy risk exposure, limits regulatory liability, and narrows the blast radius if a data breach occurs.

- **Data Residency** — For AI workloads handling regulated data, verify that the required AWS services are available in compliant regions, that cross-region data movement does not violate residency requirements, and that service terms support the applicable compliance framework.

---

### Security & Responsible AI Overlap

- **Security vs Responsible AI Overlap** — Security and responsible AI both contribute to trustworthy systems: privacy, access control, data governance, transparency, robustness, and human oversight are shared concerns across Domains 4 and 5. Together these domains represent 28% of exam content — do not skip them in favour of the heavier technical domains.

---

## Exam Strategy & Scenario Traps

### Domain Priorities

- **Exam Weighting** — Allocate study time proportionally: Domain 3 (Foundation Model Applications, 28%) → Domain 2 (GenAI Fundamentals, 24%) → Domain 1 (AI/ML Fundamentals, 20%) → Domains 4 and 5 (Responsible AI and Security/Governance, 14% each). Domains 4 and 5 combine to 28% — do not deprioritise them.

- **Question Types** — The exam includes multiple-choice single answer, multiple-response (all correct options required, no partial credit), ordering, matching, and case-study-style scenario questions; newer format types like matching and ordering can be disorienting if not practised.

- **One-week Pass Plan** — Day 1: AI/ML basics → Day 2: GenAI and prompts → Day 3: Bedrock, RAG, agents → Day 4: SageMaker and managed AI services → Day 5: responsible AI and security → Day 6: practice exams and weak-area review → Day 7: scenario traps and timed test. Practice questions matter more than passive re-reading.

---

### High-yield Scenario Patterns

- **RAG vs Fine-tuning Trap** — When a question describes frequently updated internal documents, changing data, citation requirements, or cost sensitivity, the answer is RAG/Bedrock Knowledge Bases. Fine-tuning is expensive, slow to update, and not suited to dynamic knowledge retrieval.

- **Chatbot with Structured Intents** — When the scenario specifies structured conversation flows, defined intents, and slot-based data collection, the answer is Amazon Lex. Do not overcomplicate with SageMaker when a managed conversational AI service fits.

- **Text-to-speech Trap** — Converting written text into lifelike audio output → Amazon Polly. Transcribe does the exact opposite.

- **Speech-to-text Trap** — Converting spoken audio or call recordings into text → Amazon Transcribe. Polly converts text to speech.

- **Language Translation Trap** — Translating text between languages → Amazon Translate. Comprehend analyses text; Translate changes its language.

- **Enterprise Search Trap** — Intelligent search returning ranked document results → Amazon Kendra. GenAI-generated answers grounded in retrieved enterprise content → Bedrock Knowledge Bases. Search and generation serve different needs.

- **Document Extraction Trap** — Extracting structured fields, forms, and tables from scanned PDFs → Amazon Textract. Rekognition is for image/video scene and object recognition, not structured document field extraction.

- **Bias Detection Trap** — Detecting bias and explaining model predictions → SageMaker Clarify. Bedrock Guardrails controls FM input/output content — it is not a bias measurement or explanation tool.

- **No-code ML Trap** — Business analyst building predictions without coding → SageMaker Canvas. SageMaker Studio is IDE-oriented for data scientists and ML engineers.

- **Data Preparation Trap** — Visual data transformation and preparation for ML → SageMaker Data Wrangler. Schema discovery and ETL pipelines → AWS Glue. Do not confuse data prep tools with inference endpoints.

- **Model Monitoring Trap** — Deployed model performance declining over time → SageMaker Model Monitor plus a retraining workflow. High initial training accuracy does not guarantee sustained production performance as data distributions shift.

- **Cost Control Trap** — Reducing GenAI costs → select appropriately-sized models, limit context and token length, use caching where applicable, prefer RAG over fine-tuning for knowledge updates, and monitor usage continuously. The largest model and longest context window is almost never the cost-optimal choice.

- **Private Network Trap** — AI workload must avoid public internet for service connectivity → AWS PrivateLink / VPC Endpoints. PrivateLink provides private network routing — it does not sanitise prompts, filter outputs, or replace IAM permissions.

- **Sensitive Data Discovery Trap** — Discovering and classifying PII in S3 before using data for AI → Amazon Macie. Macie is a data classification and discovery service, not a vector database or inference service.

---

### Keyword Recognition Guide

| Trigger phrase in question | Service or concept to consider |
|---|---|
| "document repository", "need citations", "external knowledge" | RAG / Bedrock Knowledge Bases |
| "multi-step process", "calling APIs", "business automation" | Bedrock Agents |
| "brand voice", "domain expertise", "consistent behavior" | Fine-tuning |
| "training pipeline", "MLOps", "custom model lifecycle" | SageMaker |
| "multiple foundation models", "foundation model selection", "GenAI app" | Amazon Bedrock |
| "understand text", "sentiment", "key phrases", "entities" | Amazon Comprehend |
| "image or video", "object detection", "face analysis" | Amazon Rekognition |
| "speech to text", "call recordings", "audio transcript" | Amazon Transcribe |
| "text to speech", "lifelike audio", "spoken output" | Amazon Polly |
| "chatbot", "conversational interface", "intents and slots" | Amazon Lex |
| "translate between languages", "multilingual content" | Amazon Translate |
| "extract from PDF", "forms", "scanned documents", "tables" | Amazon Textract |
| "intelligent search", "enterprise document search" | Amazon Kendra |
| "personalised recommendations", "right product to right user" | Amazon Personalize |
| "demand forecasting", "inventory", "time-series" | Amazon Forecast |
| "bias detection", "explain predictions", "feature attribution" | SageMaker Clarify |
| "sensitive data in S3", "PII discovery" | Amazon Macie |
| "private network access", "avoid public internet" | AWS PrivateLink / VPC Endpoints |
| "content filtering", "denied topics", "guardrails for FM" | Bedrock Guardrails |
| "human review", "low-confidence predictions" | Amazon A2I |
| "no-code ML", "business analyst", "without coding" | SageMaker Canvas |
| "API call audit", "who did what", "immutable logs" | AWS CloudTrail |

---

## Rapid Review — True / False

| Statement | Answer |
|---|---|
| Classification predicts categories; regression predicts continuous numbers. | **True** |
| Unsupervised learning requires labeled data. | **False** |
| RAG updates model weights. | **False** |
| Fine-tuning changes model behavior by additional training. | **True** |
| Embeddings are useful for semantic similarity search. | **True** |
| Amazon Textract is the best fit for extracting tables from scanned PDFs. | **True** |
| Amazon Polly converts speech to text. | **False** |
| Amazon Transcribe converts speech to text. | **True** |
| SageMaker Clarify is used for bias detection and explainability. | **True** |
| Bedrock Guardrails can help control harmful FM inputs/outputs. | **True** |
| Amazon Macie helps discover sensitive data in S3. | **True** |
| AWS PrivateLink replaces IAM permissions. | **False** |
| Model cards are runtime enforcement tools. | **False** |
| Temperature affects randomness of generated outputs. | **True** |
| A larger foundation model is always the best choice. | **False** |
| Human review is useful for high-risk AI decisions. | **True** |
| Data quality directly affects model quality. | **True** |
| Prompt injection can be indirect through retrieved documents. | **True** |
| Amazon Kendra is an intelligent enterprise search service. | **True** |
| AWS Glue crawlers train ML models. | **False** |

---

*Exam: 65 questions · 90 minutes · $100 · Passing score 700/1000 (~45 correct)*
*Cert valid 3 years · Think like a business consultant, not a cloud architect*
