# 🇧🇮 Burundian Language Identifier (Training Repository)

This repository holds the complete source code, training notebook, and data files used to build, train, and deploy my Burundian Language Identifier model.

This is the "kitchen" where the model is built. The final, trained "meal" (the model itself) is hosted on the Hugging Face Hub.

---

### 🚀 Live Demo & Final Model

* **Live Demo:** You can use the finished model right here:
    [**https://huggingface.co/spaces/samandari/burundi-lang-id**](https://huggingface.co/spaces/samandari/burundi-lang-id)

* **Trained Model:** You can download or inspect the trained model files here:
    [**https://huggingface.co/samandari/burundi-lang-id**](https://huggingface.co/samandari/burundi-lang-id)

---

### 📁 What's in this Repository?

* `burundi_lang_id_training.ipynb`: The main Google Colab notebook. It contains all the Python code to load the data, fine-tune the `bert-base-multilingual-cased` model, and push the final model to the Hugging Face Hub.
* `train.csv`: The training dataset.
* `test.csv`: The validation dataset (used to check the model's accuracy during training).

---

### 🛠️ Technology Stack

* **Model:** Hugging Face `transformers` (BERT)
* **Data:** Hugging Face `datasets`
* **Training:** Google Colab (Free T4 GPU)
* **Deployment:** Hugging Face Hub (for the model) & Hugging Face Spaces (for the Gradio app)
* **App Framework:** `Gradio`

---
---

### 📈 My Guide: How to Improve the Model

This is the most important part of the project. The model is only as good as its data. Here is my personal guide for re-training and improving it.

#### Step 1: Add New Data

1.  Clone this repository to my computer.
2.  Open `train.csv` and `test.csv` in a program like VS Code or Excel.
3.  Add new, high-quality example sentences for **all four languages**. The more data, the better!
    * *Good data format:* `A sentence in the language,label`
    * *Example:* `Ubuhinga bwa AI buratangaje cane,kirundi`
4.  Save the files.
5.  Push the updated `train.csv` and `test.csv` files back to this GitHub repository.

```bash
git add train.csv test.csv
git commit -m "Added more example sentences for Kirundi and French"
git push origin main
```

#### Step 2: Re-Run the Training in Google Colab

The `.ipynb` notebook is designed to pull the latest data *directly from this GitHub repo*. This is a much better workflow.

1.  Go to [Google Colab](https://colab.google/).
2.  Go to `File` > `Open notebook`.
3.  Select the **"GitHub"** tab.
4.  Paste in the URL of this repository and select the `burundi_lang_id_training.ipynb` file.
5.  Make sure the runtime is set to **T4 GPU** (`Runtime` > `Change runtime type`).
6.  Run **all cells** from top to bottom.
    * **Cell 3** (the data loading cell) will now **automatically download** the new `train.csv` and `test.csv` files you just pushed to GitHub.
    * **Cell 5** will re-train the model on this new, bigger dataset.
    * **Cell 6** will push the new, *smarter* model to the Hugging Face Hub.

#### Step 3: Wait for the Demo to Update

* **Done!** The live demo on Hugging Face Spaces is linked to the model on the Hub. It will automatically detect the new model version, restart, and be live with your new, improved model within 2-5 minutes.