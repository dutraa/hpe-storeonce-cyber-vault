# HPE StoreOnce Cyber Vault Interactive Demo

An interactive, browser-based visualization of **HPE StoreOnce Cyber Vault** designed to demonstrate how isolated recovery copies can remain protected when ransomware compromises the production environment.

The demo walks through a ransomware scenario from normal protection through attack and isolated recovery, visually showing the separation between **Production** and an **Isolated Recovery Environment (IRE)**.

> **Note:** This is an illustrative architecture and demonstration tool. Counts, timing, retention settings, workflows, and configurations shown in the demo are examples and may vary by deployment.

## What the Demo Shows

The demo uses an interactive six-phase scenario:

1. **Protect**  
   Production workloads and backup operations run normally.

2. **Pull**  
   The cyber vault initiates the transfer of protected data into the isolated environment.

3. **Seal**  
   The transfer completes and connectivity is closed, leaving the recovery copy separated from production.

4. **Attack**  
   A simulated ransomware event compromises production systems and backup infrastructure.

5. **Out of Reach**  
   The demo illustrates how the isolated vault remains separated from the compromised production environment.

6. **Recover**  
   Recovery begins from the protected copy inside the Isolated Recovery Environment.

The goal is to turn the cyber vault architecture into a simple visual story:

**Protect → Isolate → Attack → Survive → Recover**

---

## Supported Demo Scenarios

The interface allows several protection architectures to be explored.

### Backup Software

The demo currently includes selectable examples for:

- **HPE Zerto**
- **Commvault**
- **Veeam**
- **Cohesity**

Depending on the selected platform, the visualization adjusts portions of the protection and recovery workflow.

### Storage-Led Protection

The demo also includes:

- **HPE Alletra Storage MP B10000 direct to the cyber vault**
- **HPE Alletra Storage MP B10000 via StoreOnce**
- **HPE SimpliVity PC1000**

These options demonstrate different ways protected data can be moved into the StoreOnce Cyber Vault architecture.

---

## Architecture Concepts Visualized

The demo highlights several key architectural concepts:

### Isolated Recovery Environment

Production infrastructure is visually separated from the Isolated Recovery Environment by an air-gap boundary.

### Vault-Initiated Transfers

Where applicable, the vault initiates movement of protected data rather than relying on production infrastructure to push data into the vault.

### Restricted Connectivity

The visualization shows StoreOnce `iptables` controls being used to restrict connectivity between production and the vault.

For Catalyst-based workflows, the demo illustrates:

- **TCP 9387** for Catalyst commands
- **TCP 9388** for Catalyst data

For the B10000 direct workflow, the visualization illustrates:

- **iSCSI TCP 3260** for data access
- **HTTPS TCP 443** for REST-based commands

### Separate Vault Credentials

The architecture emphasizes that vault credentials are not stored in the production environment.

### Immutable Recovery Copies

Vaulted backups are represented as:

- Encrypted
- Immutable
- Locked according to retention policy

### Isolated Recovery

Following the simulated attack, recovery begins from the protected vault rather than the compromised production environment.

---

## Running the Demo

No installation, package manager, web server, or build process is required.

### Option 1: Open Locally

Download:

`storeonce-cyber-vault-demo-v6.html`

Then open the file in a modern web browser such as:

- Microsoft Edge
- Google Chrome
- Mozilla Firefox

### Option 2: Host with GitHub Pages

Because the demo is implemented as a self-contained HTML page, it can also be hosted directly using **GitHub Pages**.

1. Add the HTML file to your repository.
2. Enable **GitHub Pages** under the repository's **Settings → Pages**.
3. Select the branch and folder containing the demo.
4. Save the configuration.
5. Open the URL provided by GitHub Pages.

If desired, rename the HTML file to `index.html` so the demo loads automatically from the root GitHub Pages URL.

---

## Using the Demo

Use the main action button to move through the ransomware scenario.

You can also jump between phases using the navigation bar across the top.

### Keyboard Shortcuts

| Key | Action |
| --- | --- |
| `Right Arrow` | Advance to the next phase |
| `Enter` | Advance to the next phase |
| `Left Arrow` | Return to the previous phase |
| `R` | Restart the demo |
| `N` | Toggle presenter notes |

### Presenter Notes

Select **Presenter notes** to display additional talking points for each stage.

These notes are intended to help someone use the experience as a guided customer or technical presentation.

### Auto-Play

Select **Auto-play** to automatically progress through the scenario.

### Vault Operator vs. Production Admin

During the isolation portion of the demonstration, the view can be switched between:

- **Vault operator**
- **Production admin**

This helps illustrate the separation between the isolated recovery environment and the compromised production environment.

---

## Technology

The demo is intentionally lightweight and self-contained.

It uses:

- HTML5
- CSS
- Vanilla JavaScript
- Inline SVG
- CSS and SVG animation

There are **no external JavaScript frameworks, dependencies, packages, APIs, or build tools required**.

This makes the demonstration easy to run locally, host on GitHub Pages, or use during presentations without a complex deployment environment.

---

## Important Disclaimer

This project is an **illustrative technical demonstration** and should not be treated as a deployment guide or reference architecture.

Specific configurations, network ports, recovery workflows, product integrations, retention policies, timing, and supported capabilities should always be validated against current HPE product documentation and the requirements of the individual environment.

The ransomware activity, file counts, timing, and recovery sequence shown by the demo are simulated for visualization purposes.

Some product capabilities or integration paths may also depend on product version and release availability.

---

## Purpose

This project was created to make the cyber resilience story easier to understand visually.

Rather than describing isolation, ransomware protection, and recovery only through architecture diagrams, the demonstration lets the audience watch the scenario unfold:

**Production is protected.**

**The recovery copy is isolated.**

**Ransomware compromises production.**

**The vault remains separated.**

**Recovery begins from a protected copy the attack did not reach.**

That is the core story this demo is designed to communicate.
