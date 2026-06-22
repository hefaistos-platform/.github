# HEFAISTOS

*The forge for hardcore Detectioniers, because your static wiki is a joke.*

## The State of "Detection Engineering" (Or Why We Built This)

Let's be brutally honest for a second. The industry is currently flooded with "detection engineering platforms" that are essentially glorified Excel spreadsheets or shiny frontends slapped onto a scraped repository of rules. We sit around hunting down sophisticated tradecraft, reverse engineering malware, and dealing with Identity Threat Engineering for Entra ID, and where do we document this gold? In some disconnected, static wiki that goes stale the moment we hit "save."

We don't need another web form. We need a rigorous, Detection-as-Code (DaC) powerhouse with full CI/CD support. If your platform can't push directly to a Git repository, validate via pipeline, and deploy native platform languages directly into your SIEM, you aren't doing detection engineering—you're just doing data entry.

That's why we built HEFAISTOS.

*(Disclaimer: While we are highly active in the DCG420 community, let's set the record straight—HEFAISTOS is a specialized, independent workbench created by th3r3d / m3c4n1sm0, not a generic committee project. We build tools that work for us, and we are sharing the heat of the forge with you.)*

## What is HEFAISTOS?

HEFAISTOS is an interactive workbench designed for the practitioners who understand that a detection rule is the end product of a rigorous adversarial modeling process. It's built for Microsoft Defender XDR, Microsoft Sentinel, and beyond, leaning heavily into native query languages (KQL, SPL, AQL) because universal abstraction formats often fall completely flat when you need robust, enterprise-grade logic. We only mention SIGMA when someone begs for it—otherwise, skip the middleman and write native capability.

### Key Features

* **True Detection-as-Code & CI/CD Support:** When you create a detection in HEFAISTOS, you aren't locking your IP into our database. The platform automatically formats your work into standard files and pushes them directly to your GitHub or GitLab repo. It is built from the ground up to integrate into your existing CI/CD pipelines for automated testing, threshold tuning, and deployment. Your rules. Your repo.
* **Visual Capability Abstraction:** Instead of filling out text boxes, HEFAISTOS allows you to visually map adversary capabilities. Connect the toolset to the APIs, the APIs to the protocols, and identify the exact choke points for your logic. It turns detection from a guessing game into a strategic mapping exercise.
* **The Automaton Apprentice (AI-Assisted Engineering):** Writing high-fidelity detections is a grind. Our built-in Maieutic Engine and LLM integrations act as your apprentice. Need to convert an identity attack path into a native KQL query? The apprentice handles the boilerplate so you can focus on the tradecraft.
* **Auto-ACH (Analysis of Competing Hypotheses):** Stop relying on analyst intuition. Auto-ACH brings intelligence community methodology directly into the SOC. Our hybrid engine evaluates evidentiary weight mathematically, exposing blind spots and killing false positives instead of confirming your cognitive biases.
* **Identity-Centric Focus:** Built with a heavy bias toward Active Directory and Entra ID environments. We map out identity deception paths so you can finally get a handle on your Identity Threat Engineering Loop.

## Speaking the Right Language (MITRE Integration)

We don't just say "we stop bad guys." We map to the frameworks correctly, using the exact codes because words are ambiguous:

* **ATT&CK:** Tracking adversary behaviors down to the exact technique (e.g., `T1059.001` for PowerShell execution or `T1078.002` for Domain Accounts).
* **D3FEND:** Countering with defensive capabilities (e.g., `D3-ITR` for File Integrity Monitoring).
* **Engage:** Laying the trap with deception and engagement operations. Want to feed the adversary fake Entra ID credentials using our decoy frameworks? That maps to `EAC0002` (Lure). If you are deploying this capability, here is the corresponding logic code you might use to monitor the honeytoken access in Sentinel:

```kusto
// Monitor for EAC0002 Lure interaction
SigninLogs
| where UserPrincipalName == "f4ke_admin@yourdomain.com"
| project TimeGenerated, UserPrincipalName, IPAddress, Location, AppDisplayName
| extend AlertName = "Honeytoken Account Compromise"

```

Get in the forge. Deploy your rules natively, test them in your pipeline, and stop letting your coverage metrics lie to you.

---

