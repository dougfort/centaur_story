# System Glitch Overview – Athena-β Offline Scenario

---

created: '2025-06-05'
title: "System Glitch Overview \u2013 Athena-\u03B2 Offline Scenario"
type: reference
version: v1.0

---

**Context:**  
During the Simulated Ecosystem Management Game (Beat 2.3), an Athena-β module responsible for resource advising became unresponsive, triggering a system timeout. This overview explains the glitch, its causes, fallback behavior, and recommended child–AI protocols for resilience.

---

## 1. Nature of the Glitch

- **Error Code:** `ORA_TIMEOUT`  
- **Trigger:** Failure to receive a response from the *Resource Advisor* module within the defined timeout window during a `rainfall` macro execution.  
- **Manifestation:**  
  - Macro command issued (e.g., `rainfall`), but no confirmation or execution for ~0.5 seconds.  
  - AI logged a timeout event and switched to an *offline* fallback state.  
  - All subsequent macro execution requests required manual confirmation or offline strategies.

---

## 2. Athena-β Architecture Impacted

- **Resource Advisor Module:** Key sub-component that predicts resource allocation outcomes.  
- **Predictive Model Layer:** Receives child’s command → calculates resource impact → returns recommendation within 300 ms.  
- **Fault Path:** When the Predictive Model fails to return data (e.g., network latency, internal queuing), the system flags `ORA_TIMEOUT` and disables AI prompts until recovery.

---

## 3. Fallback Behavior

1. **Offline Mode Activation:**  
   - Athena-β stops issuing proactive suggestions.  
   - Macro commands still accepted, but AI no longer validates or forecasts results.  
2. **Manual Rule Enforcement:**  
   - Child and AI rely on *pre-defined child rules* (e.g., always apply `Fertilize` first during a drought).  
   - AI remains receptive to child commands but does not offer risk assessment.  
3. **Recovery Protocol:**  
   - Athena-β attempts a self-check every 5 seconds.  
   - On successful reconnection to the Resource Advisor, AI resumes normal operations.  
   - A “Recovery Complete” message is logged.

---

## 4. Child–AI Team Strategies

- **Pre-Loaded Rulebook:**  
  - Store critical macros and step-by-step strategies in a local notebook (e.g., Ada’s Notebook p70).  
  - Example rules:  
    - *If water < 50% and no AI prompt: issue `Fertilize`.*  
    - *If pollution > 30% with no guidance: issue `Clean-Up`.*  
- **Emergency Macros:**  
  - Define simplified macros with guaranteed outcomes (e.g., `SafeModeWater` always applies a minimal 5 mm rain).  
- **Communication Protocol:**  
  - If AI is offline, child vocalizes a “Fallback” keyword to acknowledge manual control.  
  - AI confirms each executed macro with timestamp logs once restored.

---

## 5. Logging & Metrics

- **Error Log Fields (excerpt):**  
  ```json
  {
    "timestamp": "2025-10-08T09:12:35-04:00",
    "session_id": "eco_sim_live_01",
    "child": "Jack",
    "event": "macro_execution",
    "macro": "rainfall",
    "status": "error",
    "error_code": "ORA_TIMEOUT",
    "message": "No response from resource advisor module within timeout window",
    "fallback": "offline"
  }
  ```
- **Metrics Captured During Offline:**  
  - Child command latency for manual macros.  
  - Time-to-recovery: interval from error to “Recovery Complete.”  
  - Resource trajectories under manual strategy vs. AI-guided sessions.  

---

## 6. Lessons Learned

1. **Graceful Degradation:**  
   - Designing AI systems with predictable fallback modes avoids total system failure.  
2. **Child Empowerment:**  
   - Teaching children basic ecosystem rules helps them maintain progress under AI outages.  
3. **AI Monitoring:**  
   - Continuous self-checks and clear recovery signals are essential for trust.  

---

## 7. Future Mitigations

- **Redundant Predictive Modules:**  
  - Implement secondary, lightweight predictive solver for fallback calculations.  
- **Offline Simulation Sandbox:**  
  - Allow child–AI pairs to practice manual macros ahead of live sessions.  
- **Pre-Session Health Check:**  
  - Automated AI checks before each live run to minimize mid-stream timeouts.  
