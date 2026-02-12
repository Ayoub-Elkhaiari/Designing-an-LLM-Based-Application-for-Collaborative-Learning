## 1. What “collaborative learning” means *in general*

At a high level, collaborative learning is when learning happens through:

- dialogue  
- shared problem-solving  
- explanation and justification  
- negotiating meaning  

Instead of:

> Learner → receives knowledge

It’s:

> Learner ↔ partner → co-construct knowledge

Traditionally, that partner is:

- another student  
- or a teacher  

In ALMA, that partner can be an **LLM**.

---

## 2. Collaborative learning **with an LLM** (this is the twist)

They are **not** saying:

> “Let’s replace peers with a chatbot”

They are asking:

> “How can an LLM *behave* like a collaborative learning partner?”

That means the LLM must **change its default behavior**.

### Default LLM behavior (what i don't want)

- Answer immediately  
- Be confident and authoritative  
- Optimize for correctness  
- End the interaction fast  

This leads to **passive learning**.

---

### Collaborative LLM behavior (what I want)

A collaborative LLM:

-  asks questions *before* answering  
-  asks the learner to explain their thinking  
-  encourages revision and reflection  
-  builds on the learner’s ideas  
-  negotiates meaning instead of asserting truth  

So learning happens *during* the interaction, not after it.

---

## 3. Key dimensions of collaborative learning 

### 1️ Shared goal

Both the learner and the LLM are oriented toward:

- understanding  
- reasoning  
- improvement  

Not just “getting the right answer”.

Example:

> “Let’s try to understand why this approach works. What do you think is the key assumption here?”

---

### 2️ Mutual contribution

The learner is **not passive**.

The system forces the learner to:

- explain  
- justify  
- choose  
- reflect  

The LLM:

- reacts to those explanations  
- adapts its responses  

If the learner gives nothing → the system gives nothing back.

---

### 3️ Turn-taking & dialogue

Collaboration requires **multiple turns**.

Instead of:

> Q → A → done

You get:

> Q → partial answer → question → learner response → refinement

Your system should **require at least 2–3 turns** per idea.

---

### 4️ Scaffolding (very important)

Scaffolding means:

- the LLM supports the learner  
- but does NOT remove the cognitive effort  

Examples:

- “Can you think of a counterexample?”  
- “What assumption are you making here?”  
- “How would this change if X was different?”  

This is classic educational theory — reviewers will love seeing it implicitly.

---

### 5 Productive friction

This is subtle but powerful.

Good collaboration includes:

- mild disagreement  
- challenge  
- uncertainty  

A collaborative LLM might say:

> “I’m not fully convinced. Can you explain why this step follows?”

That friction triggers learning.

---

## 4. Roles the LLM can play (you must pick one)

The task explicitly asks this.

Common **strong choices**:

###  Facilitator

- guides discussion  
- asks reflective questions  
- keeps learner thinking  

###  Co-explorer

- explores the problem *with* the learner  
- admits uncertainty  
- proposes alternatives  

###  Critic

- challenges reasoning  
- points out gaps  
- asks for justification  



---

## 5. How collaboration quality is judged

They will look for evidence that:

- the learner must **think**  
- the LLM **does not dominate**  
- interaction is **iterative**  
- learning is **process-oriented**  

Even without real users, your **design rationale** must make this clear.

---

## 6. A strong mental model 

> **Collaborative learning = designing the interaction so that thinking cannot be skipped.**



---
