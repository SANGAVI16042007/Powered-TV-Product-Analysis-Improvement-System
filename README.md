# Powered-TV-Product-Analysis-Improvement-System

A modern, responsive Micro SaaS web application designed for TV product teams, product managers, technical analysts, and marketers. The system analyzes TV product documents (PDF and DOCX), extracts 28+ standardized technical specifications, validates them against industry standards, calculates multi-dimensional scores (0–100), detects missing specifications, and generates an actionable product and documentation improvement roadmap.

---

## 🚀 Key Features

1. **Document Upload & Parsing (PDF & DOCX)**:
   - Drag-and-drop or browse files with size, type, and progress animations.
   - Robust text extraction using `pypdf` (for PDF) and `python-docx` (for Word documents).
   - Enterprise security validation: validates file extension, limits file size (15MB), and sanitizes inputs.

2. **28+ Standardized Technical Specifications**:
   - TV Brand, Product Name, Model Number, Product Category, Screen Size.
   - Display Technology, Resolution, Refresh Rate, HDR Support, Peak Brightness, Contrast Ratio.
   - Image Processor, Operating System, Smart TV Features.
   - Audio Specifications, Total Speaker Output (Watts).
   - Connectivity, HDMI Ports & Version (2.1/2.0), USB Ports, Wi-Fi Standard, Bluetooth.
   - Gaming Features (VRR, ALLM, FreeSync/G-Sync), Voice Assistant.
   - Energy Efficiency, Manufacturer Warranty, MSRP Price, Dimensions, Weight, and Certifications.
   - **Strict Zero-Assumption Rule**: If any specification is missing or unverified, it is explicitly marked as `"Not provided"`.

3. **Multi-Dimensional Scoring Algorithm (0–100)**:
   - **Overall Score**: Weighted composite of all 10 evaluation dimensions.
   - **10 Category Scores**:
     1. Display (12%)
     2. Picture Quality (14%)
     3. Performance (10%)
     4. Smart Features (10%)
     5. Audio (10%)
     6. Connectivity (10%)
     7. Gaming (10%)
     8. Energy Efficiency (6%)
     9. Product Information Completeness (10%)
     10. Overall Value (8%)

4. **Rigorous Separation: Cons vs. Missing Information**:
   - **Cons**: Real limitations or lower hardware parameters documented in the file (e.g. 16W weak speakers, limited 2x HDMI 2.0 ports, 60Hz panel).
   - **Missing Information**: Critical unstated technical parameters (e.g. peak brightness nits unlisted, VRR status unmentioned). Each missing spec includes **Priority (High/Med/Low)**, **Why It Matters**, and **Recommended Actions**.

5. **13 Structured Report Sections**:
   1. Product Overview (Brand, Model, Category, Screen Size, Price, Status)
   2. Overall Score Card (Circular score dial & rating tier)
   3. Category Scores Matrix (10 category bars + interactive radar chart)
   4. Executive Summary (Verdict, Top 3 Pros, Top 3 Cons, Top 3 Missing Info, Top 3 Improvements)
   5. Pros (Hardware/software strengths with explanations)
   6. Cons (Documented hardware limitations)
   7. Missing Information (Checklist audit, count badge, priority pills, rationale, actions)
   8. Positive Insights (Commercial & hardware strengths)
   9. Negative Insights (Market risks and spec ambiguities)
   10. Improvement Suggestions (Product Improvements vs Documentation Improvements)
   11. Priority Improvement Roadmap (Priority 1 High Impact, Priority 2 Medium Impact, Priority 3 Low Impact)
   12. Product Information Completeness Score card
   13. Detailed Product Specifications Table (Searchable 28+ specs with Provided/Not provided badges)

6. **Export Suite**:
   - Download Executive PDF Report (ReportLab styled binary PDF).
   - Export structured JSON.
   - Export Markdown report.
   - Print-ready `@media print` layout.

7. **Side-by-Side Product Comparison**:
   - Compare two TV products across scores, radar charts, category deltas, and 28 specifications.

8. **Analysis History & Multi-User SaaS Roles**:
   - Searchable, filterable history table.
   - Switchable demo user profiles (Sarah Chen - Pro Plan, Alex Miller - Free Plan).
   - Optional Gemini AI key integration for generative strategic summaries.

---

## 💻 Tech Stack

- **Backend**: Python 3.14, FastAPI, Uvicorn, SQLAlchemy, SQLite, Pydantic, Httpx.
- **Document Processing**: `pypdf`, `python-docx`, `reportlab`.
- **Frontend**: React 18, Tailwind CSS, FontAwesome, Chart.js.

---

## 🛠️ Running the Application

Start the local server by executing:

```powershell
python run.py
```

Then open your browser to:
[http://127.0.0.1:8000](http://127.0.0.1:8000)
