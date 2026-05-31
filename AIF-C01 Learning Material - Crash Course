# AWS AI/ML Exam Notes

## AI/ML Hierarchy

- **Artificial Intelligence** — The broad umbrella discipline where machines are designed to perform tasks that typically require human intelligence, such as playing chess, recognising speech, or making decisions.
- **Machine Learning** — A subset of AI where systems automatically learn and improve from data by finding patterns, without being explicitly programmed for each task.
- **Deep Learning** — A subset of ML that uses neural networks with multiple layers to excel at complex pattern recognition tasks like image classification and natural language processing.
- **Generative AI** — Goes beyond analysing existing data to create new original content such as text, images, audio, or code. Examples include ChatGPT and DALL-E.
- **Foundation Models** — Large models pre-trained on massive, diverse datasets that have broad general capabilities and can be adapted or fine-tuned for many downstream tasks. Examples include Claude, GPT-4, and Titan.
- **Large Language Models** — A specific type of foundation model that specialises in text understanding and generation, usually built on transformer architecture. Examples include GPT-3.5, Claude, and LLaMA.
- **Transformer Models** — The architectural backbone of modern LLMs. They process entire sentences simultaneously using attention mechanisms to understand context and relationships between words.
- **Diffusion Models** — Generate high-quality images by learning to gradually remove noise from random data, reversing a corruption process during training. Example: Stable Diffusion.
- **GANs** — Generative Adversarial Networks use two competing neural networks: a generator that creates content and a discriminator that detects fakes. This adversarial training helps produce realistic synthetic outputs.

---

## Learning Types

- **Supervised Learning** — Trains on labelled input-output pairs so the model can predict outcomes on new data. It covers both classification and regression.
- **Unsupervised Learning** — Discovers hidden structure and patterns in unlabelled data using techniques like clustering, dimensionality reduction, and anomaly detection.
- **Semi-supervised Learning** — Combines a small amount of labelled data with a large amount of unlabelled data. Useful when full labelling is too expensive or time-consuming.
- **Reinforcement Learning** — An agent learns optimal behaviour through trial and error by receiving rewards for good actions and penalties for bad ones. Used in games and autonomous systems.

---

## Data Concepts

- **Structured Data** — Neatly organised tabular data with defined fields and schemas, such as sales records, spreadsheets, or sensor readings.
- **Unstructured Data** — Data with no predefined format, including text, images, audio, and video.
- **Training Set** — The data used to teach the model.
- **Validation Set** — The data used to tune hyperparameters and prevent overfitting.
- **Test Set** — The data used for unbiased final performance evaluation.
- **High Bias** — When a model is too simple to capture the underlying patterns in data. This causes underfitting and poor performance on both training and new data.
- **High Variance** — When a model is too complex and memorises the training data too closely. This causes overfitting and poor performance on unseen data.
- **Data Quality: Volume** — Enough data to learn from.
- **Data Quality: Variety** — Diverse data that reduces bias.
- **Data Quality: Veracity** — Accurate and trustworthy data.
- **Data Quality: Velocity** — The speed at which new data is generated and processed.

---

## Text and Language AWS Services

- **Amazon Comprehend** — An NLP service that detects sentiment, extracts key phrases, identifies people, places, and organisations, flags PII, analyses syntax, and supports custom classification across many languages.
- **Amazon Translate** — Provides real-time or batch language translation with support for custom terminology dictionaries.
- **Amazon Textract** — Extracts structured text, form fields, and tables from scanned documents and PDFs while preserving layout.
- **Amazon Transcribe** — Converts speech to text in real time or batch mode. Supports speaker identification, custom vocabularies, and a medical version for healthcare terminology.
- **Amazon Polly** — Converts written text into natural speech using standard and neural voices. Supports SSML for pronunciation control.

---

## Vision and Conversation AWS Services

- **Amazon Rekognition** — A managed computer vision service that analyses images and video to detect objects, scenes, text, faces, celebrities, motion patterns, inappropriate content, and custom labelled items.
- **Amazon Lex** — Builds chatbots and voice assistants with natural language understanding. It integrates with Lambda for business logic and can run across web, mobile, and Alexa interfaces.

---

## Recommendations and Search

- **Amazon Personalize** — Delivers real-time, individually tailored product and content recommendations using your own data, without requiring ML expertise.
- **Amazon Forecast** — A time-series forecasting service that automates feature engineering and identifies seasonality patterns for demand, inventory, and resource planning.
- **Amazon Kendra** — An intelligent enterprise search service that understands natural language questions, returns ranked relevant results, and learns from user behaviour.

---

## Specialised AI Services

- **Amazon Fraud Detector** — Provides real-time fraud detection using built-in ML models or custom models trained on your own data.
- **Amazon DevOps Guru** — Uses ML to monitor application and infrastructure behaviour, detect operational anomalies, and recommend fixes.
- **Amazon CodeGuru** — Scans code for bugs, performance issues, and security vulnerabilities, then suggests improvements.
- **AWS DeepRacer** — A physical and simulated autonomous race car environment used to teach reinforcement learning concepts.

---

## Generative AI Services

- **Amazon Bedrock** — A fully managed, serverless platform for accessing, testing, and customising foundation models from different providers with enterprise-grade security.
- **Amazon PartyRock** — A no-code GenAI app builder powered by Bedrock. Useful for rapid prototyping and AI-powered demos.
- **Amazon Q Business** — An AI assistant for business users that answers questions from company documents, summarises content, automates workflows, and respects access permissions.
- **Amazon Q Developer** — An AI coding assistant that helps write, complete, debug, and optimise code. It can also support architecture, security, and cost optimisation tasks.

---

## ML Platform: Amazon SageMaker

### SageMaker Core Services

- **SageMaker Studio** — A fully integrated ML IDE with JupyterLab and RStudio support. It provides notebooks, experiment management, visual workflows, and team collaboration features.
- **SageMaker Feature Store** — A central repository for storing, versioning, and serving ML features. It supports historical snapshots, online serving, and offline batch access.
- **SageMaker Data Wrangler** — A visual data preparation tool with built-in transformations, data quality insights, bias detection, and export options.
- **SageMaker Ground Truth** — A data labelling service that supports human-in-the-loop labelling, active learning, internal teams, vendors, and crowdsourced labellers.
- **SageMaker Pipelines** — Enables automated ML workflows with step-by-step pipeline definitions, Git integration, and reproducible experiment tracking.
- **SageMaker Canvas** — A no-code AutoML interface for business analysts. It supports drag-and-drop model building without programming.
- **SageMaker Clarify** — Detects bias in training data and trained models, explains model predictions, and supports fairness monitoring.
- **SageMaker Model Monitor** — Tracks deployed model performance in production, detects data drift and quality degradation, and sends alerts.
- **MLflow on SageMaker** — Provides experiment tracking, model version management, model registry, and deployment orchestration.

### SageMaker Inference Types

- **Real-time Inference** — Always-on persistent endpoints that return predictions instantly with minimal latency. Best for live, user-facing applications where delays are unacceptable.
- **Batch Inference** — Processes large volumes of data offline on a defined schedule without a persistent endpoint. Best for bulk workloads where immediate responses are not required.
- **Serverless Inference** — Automatically scales capacity up and down, including to zero when idle. Best for intermittent or dev/test workloads, but cold-start latency can occur.
- **Asynchronous Inference** — Uses a queue-based approach for large input payloads and long-running inference tasks. Best when the caller does not need to wait synchronously.

### Built-in SageMaker Algorithms

- **KNN** — K-Nearest Neighbours is a distance-based algorithm used for classification and regression by comparing new data points to their nearest neighbours.
- **Linear Learner** — Trains linear and logistic regression models efficiently for classification and regression on structured data.
- **XGBoost** — A gradient boosting algorithm widely used for structured and tabular data.
- **PCA** — Principal Component Analysis reduces the number of features while retaining important variance. Used for dimensionality reduction and noise removal.
- **K-Means** — An unsupervised clustering algorithm that groups data points into K clusters based on feature similarity.
- **Random Cut Forest** — An unsupervised anomaly detection algorithm that identifies unusual data points by measuring how isolated they are from the rest of the dataset.

---

## Compute Infrastructure

- **Deep Learning AMIs** — Pre-configured virtual machine images with popular ML frameworks such as TensorFlow and PyTorch installed and optimised for EC2.
- **Deep Learning Containers** — Docker containers pre-loaded with optimised ML frameworks for consistent environments across development, testing, and production.
- **AWS Inferentia** — AWS-designed ML inference chips optimised for low-cost, high-performance inference workloads, especially transformer-based models.
- **Amazon Elastic Inference** — Allows right-sized GPU acceleration to be attached to EC2 or SageMaker instances to reduce inference costs.

---

## RAG: Retrieval Augmented Generation

- **RAG** — A technique that grounds LLM responses in external data by retrieving relevant document chunks before generating an answer. It helps reduce hallucination.
- **Vector Embeddings** — High-dimensional mathematical representations that capture semantic meaning. Similar concepts are positioned close together in vector space.
- **Vector Databases** — Databases designed for fast similarity search over vector embeddings. Examples include OpenSearch, Pinecone, Redis, Chroma, and Aurora pgvector.
- **Retrieve and Generate API** — A Bedrock API that executes the complete RAG workflow, maintains conversation context, and returns grounded answers with source attribution.
- **Retrieve API** — Returns relevant document chunks from a knowledge base without generating a response. Useful when you want full control over the final answer.
- **Hybrid Search** — Combines semantic vector search with traditional keyword search to improve recall and precision.

### RAG vs Fine-tuning

- **RAG** — Best when data changes frequently, when citations are required, or when cost and speed matter.
- **Fine-tuning** — Best when you need a specific tone, brand voice, behavioural pattern, or domain-specific response style.
- **Continued Pre-training** — Extends a model’s pre-training using unlabelled domain-specific data to deepen its knowledge of a field.

---

## Bedrock Agents

- **Bedrock Agents** — Action-driven AI assistants that interpret user intent, plan multi-step tasks, and execute actions using connected systems.
- **Action Groups** — Define external APIs that an agent can call. They are specified using OpenAPI schemas and connected to business systems through AWS Lambda.
- **Multi-agent Collaboration** — Allows multiple specialist agents to handle different domains or sub-tasks and coordinate complex workflows.
- **Bedrock Guardrails** — Safety controls that block harmful content, redact PII, reduce prompt injection risk, and enforce application-specific policies.

---

## Security Services

- **IAM** — Defines who can access what across AWS using users, groups, roles, and policies. It supports the principle of least privilege.
- **AWS KMS** — Manages encryption keys backed by HSMs. Supports key rotation and integrates with many AWS services.
- **Amazon Macie** — Uses ML to discover, classify, and alert on sensitive data such as PII stored in S3.
- **AWS Secrets Manager** — Stores credentials such as API keys, database passwords, and tokens with rotation, access control, and audit logging.
- **AWS WAF** — A Layer 7 web application firewall that protects against common web exploits such as SQL injection, cross-site scripting, and bot traffic.
- **AWS Shield** — Provides DDoS protection. Shield Standard is enabled for all AWS customers, while Shield Advanced adds enhanced support and protections.
- **AWS Network Firewall** — A managed stateful firewall with deep packet inspection, custom rules, and threat intelligence feed support.
- **AWS CloudTrail** — Records API calls made in an AWS account. Used for auditing, compliance, investigations, and forensics.
- **Amazon GuardDuty** — A managed threat detection service that analyses account activity and network behaviour using AWS threat intelligence.
- **Amazon Inspector** — Scans EC2 instances and container workloads for software vulnerabilities and unintended network exposure.
- **AWS Security Hub** — Aggregates and normalises security findings from AWS and third-party tools into a centralised security view.

---

## Responsible AI

- **Fairness** — Ensures AI systems do not create or amplify unfair bias.
- **Explainability** — Makes model decisions understandable to humans.
- **Privacy and Security** — Protects user data and prevents unauthorised access.
- **Safety** — Reduces the risk of harmful or unsafe model behaviour.
- **Controllability** — Allows humans and systems to guide or limit model behaviour.
- **Veracity and Robustness** — Ensures outputs are accurate, reliable, and resilient.
- **Governance** — Defines ownership, controls, review processes, and accountability.
- **Transparency** — Makes it clear how AI systems are used and what limitations they have.
- **Hallucination** — When an LLM confidently generates incorrect information. RAG is a common mitigation.
- **Toxicity** — Offensive, harmful, or inappropriate model output. Mitigated using content filters and guardrails.
- **Prompt Injection** — A malicious input that tries to override the model’s original instructions. Mitigated with strict prompt templates and input validation.
- **Prompt Leakage** — An attempt to extract hidden system prompts or confidential instructions. Mitigated with secure prompt design and access controls.
- **Jailbreaking** — Attempts to bypass model safety controls through clever phrasing or roleplay. Mitigated through red teaming and layered content filtering.
- **Data Poisoning** — Deliberately corrupting training data to influence model behaviour. Mitigated with data validation and source verification.
- **Model Extraction** — Attempting to reverse-engineer a proprietary model by querying it systematically. Mitigated using rate limits and privacy techniques.
- **Amazon Augmented AI** — Adds human review into ML workflows for sensitive or low-confidence predictions.

---

## Prompt Engineering

- **Zero-shot Prompting** — Giving a clear instruction without examples. Best for simple and well-understood tasks.
- **Few-shot Prompting** — Providing a few examples to teach the expected pattern or format.
- **Chain-of-Thought Prompting** — Asking the model to reason step by step before answering. Useful for logic, maths, and multi-step reasoning.
- **Negative Prompting** — Telling the model what to avoid or exclude.
- **Role-based Prompting** — Assigning the model a specific expert role or persona to guide the response.
- **Prompt Chaining** — Breaking a complex task into smaller prompts where each output feeds into the next step.
- **Temperature** — Controls randomness and creativity. Lower values are more predictable, while higher values are more varied. It does not control speed.
- **Top P** — Controls the breadth of the token pool used for generation. Lower values make output tighter and more focused.
- **Top K** — Restricts token selection to the top K most probable next tokens.
- **Max Tokens** — Sets the maximum output length and helps manage cost and response size.
- **Stop Sequences** — Specific strings that tell the model when to stop generating.

---

## Healthcare AI

- **Amazon HealthLake** — A HIPAA-compliant service that stores, normalises, and analyses health data in FHIR format.
- **Amazon Comprehend Medical** — Extracts medical conditions, medications, dosages, and protected health information from clinical notes.
- **Amazon Transcribe Medical** — A speech-to-text service tuned for medical terminology and doctor-patient conversations. 
