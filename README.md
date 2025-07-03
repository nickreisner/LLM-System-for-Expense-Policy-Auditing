#PolicyPal: Automated Expense Policy Compliance Analyzer Using Multi-Stage, Zero-Shot Retrieval and Evaluation

## Overview
PolicyPal is a Jupyter notebook system for automated, interpretable expense policy compliance analysis. It processes institutional policy documents and expense receipts, retrieves relevant policy sections, and generates a transparent compliance report using large language models (LLMs).

![PolicyPal Poster](Policy%20Pal%20Poster.jpg)

*PolicyPal: Automated Expense Policy Compliance Analyzer Poster*

---

## Prerequisites
- **Python 3.8+** (recommended: 3.10+)
- **Jupyter Notebook** (or JupyterLab)
- **Internet connection** (for installing packages and LLM API calls)
- **Together.AI API key** (required for LLM access)

### Required Python Packages
The notebook will install these automatically if missing:
- `together`
- `PyPDF2`

---

## Required Files
Place the following files in the same directory as the notebook:
- `Stanford_Expenses Pre-Processed.json`  
  (Pre-processed policy summaries)
- `Stanford University Expense Policy With Labeled Sections.jsonl`  
  (Policy with labeled sections)
- A PDF file of an expense receipt (e.g., `Uber_Receipt.pdf`)

---

## Running the Notebook

1. **Open the Notebook**
   - Launch Jupyter Notebook or JupyterLab.
   - Open `Policy Pal Notebook.ipynb`.

2. **Insert Your API Key**
   - In Section 1, replace `FILL HERE` with your Together.AI API key:
     ```python
     client = Together(api_key="YOUR_API_KEY_HERE")
     ```

3. **Check/Update File Paths**
   - In Section 7 (Main Execution), ensure the following variables point to your files:
     ```python
     policy_summaries_file_path = 'Stanford_Expenses Pre-Processed.json'
     policy_tree_file_path = 'Stanford University Expense Policy With Labeled Sections.jsonl'
     receipt_pdf_file_path = 'Uber_Receipt.pdf'  # or your receipt PDF filename
     ```
   - Update `user_status`, `organization`, `organization_location`, and `date` as needed.

4. **Add Your Receipt**
   - Place your expense receipt PDF in the same directory.
   - Supported categories: Airfare, Lodging, Ground Transportation, Meals, Other Reimbursable Business Expenses, Employee Gifts, Business Meals, Travel Meals.

5. **Run the Notebook**
   - Run all cells in order, except for those in Section 6 (Pre Processing Execution, which is for advanced use only).
   - The notebook will:
     - Load the policy and receipt files
     - Extract and standardize receipt information
     - Retrieve relevant policy sections
     - Evaluate compliance
     - Generate a detailed, interpretable report

6. **View Results**
   - The final cell will display a compliance analysis report, including:
     - Requirements met/unmet
     - Required actions
     - Contextual information
     - Explanations and links to policy sections

---

## Troubleshooting
- **File Not Found:** Double-check that all required files are in the same directory and file paths are correct.
- **API Errors:** Ensure your Together.AI API key is valid and you have internet access.
- **PDF Extraction Issues:** Use clear, standard PDF receipts for best results.

---

## Notes
- Section 6 is for advanced pre-processing and should not be run for standard use.
- The system is designed for transparency and traceability—review the generated report for explanations and policy links.
- For best results, use real receipts and policies formatted as described above.