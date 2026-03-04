# ECG Analysis

ECG analysis pipeline with agent framework - GenAI creates ? based on ECH signal form Apple Watch

---

# Pipeline


1. Input: MRI neuroimage
Data Type: 3D NIfTI (.nii) tai DICOM -tiedosto, esimerkiksi rakenteellinen T1-painotteinen aivokuva.
Context: Potilasdata, joka on esikäsitelty (esim. kohinanpoisto ja asennon korjaus) ohjelmiston toimesta ennen agentille siirtämistä.

2. Agent: "I see a neuroimage. I will trigger tool for generatin matching PET image"
Tool: Cross-Modality Synthesis Pipeline.
Action: Agentti (orkestraattori) tunnistaa, että sisääntulona on MRI-kuva, mutta lääkäri/tutkija tarvitsee PET-kuvan analyysia varten. Agentti päättää käyttää generatiivista mallia luodakseen synteettisen PET-kuvan suoraan MRI-kuvasta välttäen radioaktiivisen merkkiaineen käytön.

3. Model: GenAI model
Model: Latent Diffusion Model (LDM) tai CycleGAN.
Function: Suorittaa Image-to-Image Translation -tehtävän.
Operation: Malli on koulutettu tuhansilla MRI-PET-kuvapareilla. Se "ymmärtää" MRI-kuvan anatomian ja generoi (GenAI) sen perusteella todennäköisen metabolisen aktiivisuuden, joka näkyisi PET-kuvassa. Se täyttää 3D-vokselit synteettisellä datalla, joka vastaa aivojen glukoosiaineenvaihduntaa.

4. Output:
Result: Synthetic FDG-PET scan (Synteettinen PET-kuva).
Deliverables: MRI ja synteettinen PET rinnakkain.
Anomalioiden tunnistus: Agentin (LLM-aivojen) kirjoittama yhteenveto, joka vertaa synteettistä PET-kuvaa viitearvoihin ja huomauttaa mahdollisesta hypometaboliasta tietyllä aivoalueella.
