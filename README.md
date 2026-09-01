# 🎙️ NeuroVoice

> **AI-Powered Neurological Voice Biomarker Screening in 60 Seconds.** 
> Exposing clinical-grade vocal digital phenotyping tools directly to AI agents using the [WebMCP Standard](https://chrome.com).

[![WebMCP Standard](https://shields.io)](https://chrome.com)
[![Production App](https://shields.io)](https://zite.so)
[![Hackathon](https://shields.io)](https://devpost.com)

---

## 🎯 Inspiration & Problem Statement
Neurological, neuromuscular, and respiratory conditions often manifest early, subtle changes in human vocal fold vibrations long before macro-symptoms appear. Traditional acoustic voice analysis requires specialized laboratory-grade acoustic hardware, manual diagnostic pipelines, and localized data silos. 

**NeuroVoice** democratizes clinical pre-screening. It brings laboratory-level biomarker extraction natively to standard consumer browsers. By leveraging the **WebMCP protocol**, NeuroVoice exposes structured tool contracts to AI agents. This allows human users and browser-native assistive agents to coordinate screening sessions together, bypassing traditional manual UI interaction friction entirely while strictly preserving client-side privacy.

---

## ✨ Core Product Capabilities

*   **⚡ Live Production Deployment:** Access the working platform immediately at [https://zite.so](https://zite.so).
*   **🎙️ Clinical Voice Capture:** High-fidelity 44.1 kHz mono audio recording matching scientific research parameters with a synchronized real-time oscilloscope waveform monitor.
*   **📊 Vocal Biomarker Matrix:** Automated serverless computation of micro-perturbation metrics:
    *   `Jitter`: Frequency micro-instability variation.
    *   `Shimmer`: Amplitude cycle-to-cycle perturbation.
    *   `HNR (Harmonics-to-Noise Ratio)`: Acoustic signal clarity versus noise turbulence.
    *   `CPP (Cepstral Peak Prominence)`: Harmonic structure quality in continuous speech.
*   **🌐 Multi-Lingual Anti-Memorization Framework:** Supports regional speech configurations (India, Middle East) across 9 languages. It utilizes a dynamic paragraph rotation matrix to eliminate memorization bias across repeated screenings.
*   **📄 Structured PDF Artifact Generation:** Compiles digital biomarkers into an exportable, print-ready document paired with localized LLM-driven medical-grade visual breakdowns.
*   **🔒 Pro-Tier Lifecycle Auditing:** Free tier processes immediate evaluation metrics locally; the Pro version hooks into secure historical data logs for continuous tracking.

---

## 🏗️ Architecture & WebMCP Integration

NeuroVoice implements a dual-API strategy using the experimental Web Model Context Protocol (`navigator.modelContext`) layer to facilitate seamless machine-to-machine actuation.

### 1. Declarative API Integration (Form Component)
We annotate our configuration elements so AI agents know exactly how to pre-fill patient variables accurately to prime our acoustic reference ranges:

```html
<form id="screening-calibration-form">
  <input 
    type="text" 
    name="patientName" 
    data-webmcp-description="The full legal name of the screening candidate" 
    required 
  />
  <input 
    type="number" 
    name="patientAge" 
    data-webmcp-description="Age in years used to calculate reference control groups" 
    required 
  />
  <select name="biologicalSex" data-webmcp-description="Biological sex assigned at birth for pitch threshold baseline calibration">
    <option value="male">Male</option>
    <option value="female">Female</option>
    <option value="other">Other</option>
  </select>
</form>
```

### 2. Imperative API Integration (JavaScript Tool Actions)
We register advanced frontend execution hooks directly using the browser runtime interface to expose programmatic control maps to the agent:

```javascript
if (typeof navigator.modelContext !== 'undefined') {
  navigator.modelContext.registerTool(
    'analyzeVocalBiomarkers',
    'Processes raw high-fidelity audio data arrays to compute Jitter, Shimmer, and HNR metrics.',
    {
      audioBufferLength: { type: 'number', description: 'Sample length of the collected audio array' },
      samplingRate: { type: 'number', description: 'Target audio capture rate, standard 44100Hz' }
    },
    async function(args) {
      try {
        const response = await fetch('https://zite.soapi/dsp/extract', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({ length: args.audioBufferLength, rate: args.samplingRate })
        });
        const metrics = await response.json();
        
        return {
          content: [{
            type: 'text',
            text: `Extraction Complete. Jitter: ${metrics.jitter}%, Shimmer: ${metrics.shimmer}%, HNR: ${metrics.hnr}dB.`
          }]
        };
      } catch (error) {
        return { content: [{ type: 'text', text: `Tool Execution Failure: ${error.message}` }], isError: true };
      }
    }
  );
}
```

---

## 🛠️ Complete Technical Stack

*   **Frontend Client Platform:** Next.js 14 / React Engine, Tailwind CSS architecture integrated with the Zite custom script configuration framework.
*   **Audio DSP Pipeline Backend:** Python 3.11, Librosa, SciPy Signal Library, NumPy processing arrays.
*   **Agentic Protocol Layer:** Google Chrome WebMCP Native Interface API.
*   **Document/Report Systems:** FastAPI framework, ReportLab / PDFKit automated generation pipelines.

---

## 🚀 Setup & Browser Testing Sandboxing

### 💻 Configure Your WebMCP Browser Environment
Because WebMCP is an emerging browser-native standard, judges must prepare their local development environment explicitly to intercept tool contracts:
1. Open a Google Chrome window.
2. In the URL navigation address bar, navigate to: `chrome://flags/#enable-webmcp-testing`.
3. Locate the **WebMCP Testing Support** flag and switch its setting dropdown to **Enabled**.
4. Click the **Relaunch** button at the bottom of the screen to commit browser changes.

---

## 📋 Comprehensive Hackathon Evaluation Walkthrough

Judges can execute the following verification workflow to audit the live platform:
1. **Context Initialization:** Open your WebMCP-enabled browser and navigate to the live deployment link: [https://zite.so](https://zite.so).
2. **Authentication Access:** Complete the Google OAuth authentication flow.
3. **Onboarding Context Capture:** Fill out the demographics calibration card (Name, Age, Sex). The WebMCP layer converts these entries into physical targets.
4. **Regional Adaptation Mapping:** Use the header toggles to choose a region (e.g., India) and a native language script (e.g., Bengali, Hindi, English). Observe the framework render an isolated, phonetically precise target passage block.
5. **Telemetry Ingestion:** Provide microphone peripheral input authorization. Record continuous reading execution aloud for up to 60 seconds.
6. **Actuation Callback Verification:** Click stop recording. The backend ingests data blocks via automated runtime tool definitions.
7. **Artifact Output Audit:** Review the visual charts rendered instantly alongside an on-screen chatbot assessment log, or print/download the finalized clinical PDF report mapping Jitter, Shimmer, HNR, and CPP anomalies.

---

## 🔮 Strategic Technical Roadmap
*   **Fully Decentralized Edge Architectures:** Compile Python signal processing models down into WebAssembly (Wasm) modules for client-side processing without relying on servers.
*   **Multi-Modal Screening Protocols:** Update the browser tool mapping profile to incorporate facial micro-tremor computer vision diagnostics via modern WebGL/Webcam video stream integration layers.
*   **EMR Data Sync Channels:** Interface backend report dispatch actions with standardized hospital HL7/FHIR communication adapters.

---

## ⚖️ Clinical Safety & Regulations Disclaimer
This application uses code systems modeled after diagnostic voice profiling dashboards, but is constructed exclusively as a hackathon engineering mockup for prototype evaluation purposes. It does not provide medical diagnoses, treatment options, or prescriptive care paths. Users should check physical documentation labels and consult certified healthcare practitioners for actual medical validation.
