# AI Assignment: Personalized News Feed Recommender System (PEAS Framework)

**System B: Personalized News Feed Recommender (e.g., Facebook)**

This repository contains a complete analysis of a **Personalized News Feed Recommender System** using the **PEAS (Performance, Environment, Actuators, Sensors)** framework from *Artificial Intelligence: A Modern Approach* by Russell and Norvig. The assignment explores how modern social media platforms curate content using sophisticated AI agents.

##  Table of Contents
- [Overview](#overview)
- [Task 1: PEAS Specification](#task-1-peas-specification)
- [Task 2: Environment Classification](#task-2-environment-classification)
- [Task 3: Critical Analysis](#task-3-critical-analysis)
- [Task 4: Structured JSON Representation](#task-4-structured-json-representation)
- [Key Insights](#key-insights)
- [References](#references)

---

## Overview

The **Personalized News Feed Recommender** is one of the most impactful AI systems in the world. Unlike search engines that respond to explicit queries, this agent **proactively curates content** based on user behavior across billions of sessions. It ranks thousands of candidate posts in real-time to maximize platform objectives while balancing engagement, diversity, and societal impact.

This analysis breaks down the system using the standard PEAS framework and evaluates its environmental properties, engineering challenges, and ethical trade-offs.

---

## Task 1: PEAS Specification

### 1.1 Performance Measure
Four key metrics define success:

- **Session Engagement Rate**: Primary target proportion of recommended posts receiving meaningful interactions (click, share, comment, watch >5s). Typical baseline: 15-25%.
- **Feed Diversity Index**: Measures breadth of topics, sources, and political perspectives to prevent filter bubbles.
- **Misinformation Exposure Rate**: Tracks fact-checked false content. Target: ≥30% reduction vs. chronological feed.
- **User Retention Delta**: Measures impact on daily active users. Even 0.1% improvement equals millions of extra sessions.

These metrics are in **perpetual tension**, making optimization extremely challenging.

### 1.2 Environment
The agent operates in a complex **layered digital environment**:

- **User Level**: Diverse demographics, languages, cultures, and shifting moods.
- **Platform Level**: Massive corpus of user-generated content (posts, images, videos), advertiser bidding, and jurisdiction-specific regulations.
- **Network Level**: Near-zero latency requirements across global data centers serving hundreds of millions of concurrent users.
- **Dynamic Events**: Trending topics (elections, disasters, news) create sudden spikes in content volume.

### 1.3 Actuators
Digital actions with real-world consequences:

- **Feed Ranking and Display Engine** (primary): Reorders and selects posts, determines format (text, image, video autoplay, etc.).
- **Notification Dispatch System**: Pushes alerts to re-engage users.
- **Content Promotion/Demotion**: Adjusts distribution scores to amplify or suppress posts.
- **A/B Testing Framework**: Automatically deploys and evaluates ranking model variants.

### 1.4 Sensors
Rich behavioral and contextual inputs:

- **Explicit Signals**: Likes, shares, comments, saves.
- **Implicit Signals**: Scroll velocity, dwell time, video watch percentage, hover events.
- **User Context**: Profile data, social network, historical affinities.
- **Content Analysis**: NLP for topics/sentiment/credibility + Computer Vision models.
- **External Signals**: News APIs and real-world event data.

---

## Task 2: Environment Classification

| Dimension       | Classification       | One-Sentence Justification |
|-----------------|----------------------|---------------------------|
| **Observable**  | Partially Observable | Cannot directly observe user intent — only sees behavioral signals. |
| **Agent Type**  | Multi-Agent          | Millions of users + advertisers compete simultaneously. |
| **Outcome**     | Stochastic           | User receptiveness is mood-dependent and unpredictable. |
| **Time Horizon**| Sequential           | Recommendations shape long-term user preferences. |
| **World Change**| Dynamic              | Trends and user states evolve continuously. |
| **State Space** | Continuous           | Relevance scores, probabilities, and attention estimates are real-valued. |

---

## Task 3: Critical Analysis

### 3.1 Most Difficult Engineering Challenge
**Sequential nature of the environment** is the hardest challenge.

- Every recommendation influences future user behavior.
- Creates **preference amplification spirals** (e.g., outrage content → more clicks → more similar content).
- Standard reinforcement learning struggles due to **delayed reward signals** (weeks/months) and lack of reliable long-term user simulation.
- **Temporal credit assignment** remains an open research problem.

### 3.2 Utility Function and Trade-off Analysis

```math

U = α · Engagement_Score − β · Misinformation_Risk − γ · Outrage_Amplification
```

## Key Insights

Multi-objective Optimization is central engagement often conflicts with diversity and truthfulness.
Feedback Loops can create unintended societal consequences (filter bubbles, polarization).
Long-term vs Short-term optimization remains the biggest unsolved challenge.
Ethical Governance of utility function weights is crucial.


## References

Russell, S., & Norvig, P. (2022). Artificial Intelligence: A Modern Approach (4th ed.). Pearson.
Internal studies from major social media platforms on recommendation dynamics.
