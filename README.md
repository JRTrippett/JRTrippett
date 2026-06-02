# Jonathan Trippett

**Physician · Army Veteran · AI Systems Builder**

MD, BCMAS. Army veteran. Finishing an MS in Business Analytics and Project Management
at the University of Connecticut School of Business.

My career started in the military, ran through medical school, and moved through
preventive medicine consulting, medical informatics work for VC-funded healthcare
companies, and startup advising. Somewhere in there I kept running into the same
problem: data people don't understand medicine, and medical people don't understand
data. Nobody was sitting in the middle. I decided to close that gap on my end, which
is what brought me to UConn and eventually to building AI systems in clinical and
humanitarian contexts.

I'm not coming from a CS background. I'm coming from years of working in environments
where incomplete information and high stakes are just the conditions, not the exception.
That shapes what I build and what I think is worth building.

---

## RAG Systems

Most of my active work sits here. The gap between a basic RAG implementation and one
that holds up reliably is significant, and I've spent a lot of time in that gap.

**The Research Librarian** is a local RAG system built for clinical and operational
knowledge retrieval, running entirely on an M1 MacBook Pro with 16GB unified memory.
The corpus covers clinical medicine, UN logistics and workforce data, and operational
project histories, pulled from sources including openFDA and national medical
databases. The ingestion pipeline processed and vectorized 744,325 discrete knowledge
bricks using all-MiniLM-L6-v2 embeddings at roughly 120 bricks per second, stored in
a ChromaDB instance with HNSW graph indexing. The LLM layer runs Phi-4 quantized
locally via Ollama.

One design decision worth calling out: every knowledge brick carries a reliability
classification that distinguishes clinically validated data from homeopathic or
traditional sources. The Streamlit interface surfaces those classifications in real
time alongside retrieved context, so you can see not just what the system retrieved
but how much weight to give it. In a clinical setting that distinction matters quite
a bit. Nothing leaves the machine.

**Project Commonplace** is a conversational AI system built on the Project Gutenberg
corpus using a hybrid retrieval architecture. A relational SQL layer
(Author → Work → Work_Concept → Concept → Subject) actively shapes what gets retrieved
alongside vector search. The idea is that the structure of the knowledge base informs
retrieval, not just keyword proximity. Most RAG systems don't do this.

A Dify-based research assistant powered by GPT-4o rounds out this work on the
academic side. It queries a curated corpus of papers on small language model
optimization and was built as a practical tool for my own research workflows at UConn.

---

## Fine-tuning

I've been running QLoRA fine-tuning pipelines on Apple Silicon using the MLX
framework, targeting Phi-4-mini-instruct. The training dataset is a 160-pair
instruction/input/output set grounded in UN operational and academic contexts,
covering document formatting, correspondence, and text editing tasks. The pipeline
uses LoRA adapters for parameter-efficient fine-tuning (PEFT), keeping the whole
process tractable on local hardware without giving up meaningful performance.

The practical question driving this work: how capable can a fine-tuned small model
get for a specific domain, running entirely on-device, without touching a cloud API?

---

## Small Language Models

SLMs are where my longer-term interest sits. A capable, fine-tuned model running
locally on consumer hardware changes what's possible in regulated or constrained
environments. Healthcare, humanitarian operations, field medicine. Places where cloud
dependency is a liability rather than a feature. I've been building in that direction
on an M1 MacBook Pro and exploring what coordinated multi-SLM pipelines could look
like in practice.

---

## Deployed Projects

### [UN Survey Dashboard](https://jrtrippett.github.io/un-survey-dashboard/)
Built during a data and analytics internship at the UN Department of Operational
Support (DHMOSH). Replaced an existing Power BI solution. Aggregates and visualizes
staff survey data across 40+ global clinic locations. HTML/JS, deployed on GitHub
Pages, in active use.

### [UN Medical Exam Platform](https://dos-mwf.github.io/un-exam-platform/)
An exam generation and delivery tool built for medical recruitment across the UN
clinic network. Combines an Excel question bank with an HTML exam generator.
In active use.

---

## Publications

**[A SWIFT Model for Universal Health Data Interoperability](https://ssrn.com/abstract=6556199)**
Proposes a cooperative governance model for health data exchange modeled on the SWIFT
financial messaging infrastructure. Argues for a neutral, vendor-independent
interoperability clearinghouse for health data, independent of any single platform
or government. SSRN, 2026.

**[The Field-to-Hospital Data Gap in Disaster Response: A Persistent Failure Point
in Continuity of Care and the Case for an NFC-Based Offline Patient
Tracker](https://ssrn.com/abstract=6507038)**
Identifies where patient data continuity breaks down between field triage and hospital
intake in disaster scenarios and proposes an NFC-based offline tracking system as a
structural fix. Grounded in UN humanitarian operations experience. SSRN, 2026.

---

## Connect

[LinkedIn](https://www.linkedin.com/in/jonathantrippettmd) &nbsp;·&nbsp; jrtrippett@gmail.com
