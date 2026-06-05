# MRI-Atlas Trainer 🧠🔬

An interactive web-based educational game designed for neuroscience and medical students to learn human brain anatomy efficiently and intuitively.

👉 **[Play directly in your browser here!](https://mendeltem.github.io/mrt-atlas-trainer/)**

---

## 🚀 Features

* **Interactive MRI Slice Viewer:** Seamlessly navigate through 32 distinct anatomical brain slices using the slider, your mouse scroll wheel, or arrow keys (as seen in `grafik_2.jpg`).
* **AAL-Atlas Overlay:** A precise, color-coded overlay in MNI standard space visualizes exact anatomical regions based on the Automated Anatomical Labeling (AAL) atlas.
* **Two Learning Modes:**
  * **Explore Mode:** Click anywhere on the brain slice to instantly reveal the exact region name (German + AAL classification) and its primary neurological function. Use the "Atlas" slider to adjust transparency dynamically, allowing you to study the underlying T1 structural boundaries.
  * **Training Mode:** Test your knowledge! The application prompts you to locate and click on specific brain structures across different slices.

---

## 🛠️ Technical Implementation & Pipeline

The project is highly optimized to run entirely client-side in the browser, requiring zero server-side infrastructure or database calls:

1. **Python Preprocessing:** The underlying 3D MRI data (MNI152 T1 template) and corresponding atlas labels were preprocessed in Python and exported into highly optimized, lossless 2D image slices.
2. **Pixel-Perfect Click Detection:** To match mouse clicks to anatomical regions, a hidden color-label map is loaded in the background. Each individual pixel color value maps directly to a specific unique AAL identifier.
3. **Web Stack:** Pure HTML5, CSS3 (featuring a dark mode layout tailored for comfortable, long-term studying), and native JavaScript for responsive UI control.

---

## 🔬 Scientific Background & Validation

This tool was developed within the context of neuroimaging research. The underlying imaging pipeline, alignment, and segmentation accuracy are based on methodological evaluations validated on a cohort dataset of **94 patients**. The core focus is providing precise anatomical mapping within the standardized MNI space, effectively bridging the gap between theoretical neuroanatomy and practical MRI evaluation.

---

## 📖 Recommended Study Strategy for Students

For optimal retention and learning efficiency, we recommend following these steps:

1. **Visual Orientation:** Start in **Explore Mode**. Move your cursor over prominent structures (such as the thalamus or caudate nucleus visible in slice 17) to familiarize yourself with anatomical boundaries and adjacencies.
2. **Isolate Structures:** Use the **Atlas slider** to slowly fade out the color-coded map. Try to identify and delineate the structural borders relying purely on the grayscale T1-weighted contrast.
3. **Self-Assessment:** Switch to **Training Mode** and attempt to locate the requested structures without any visual assistance across different slices.

---

## 🤝 Feedback & Contributions

If you spot any discrepancies in region labeling, have usability feedback, or would like to suggest new features, feel free to open an **Issue** or submit a **Pull Request**!
