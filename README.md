
# Stock Digitization Assistant – Requirement Analysis

## 1. Project Title

**Stock Digitization Assistant**

*A Python-based tool to scan handwritten stock entries from images and transform them into structured, copyable digital data.*

---

## 2. Problem Statement

Currently, stock data is recorded manually on paper during the day and entered into a computer system at the end of the day. This process is:

- Time-consuming
- Prone to human error
- Redundant (same data recorded twice)

The goal is to reduce manual effort and errors by automating the digitization of handwritten records.

---

## 3. Objectives

- Upload or scan handwritten stock sheets.
- Automatically extract item data using OCR.
- Display structured item data in an editable format.
- Provide a "Copy" button for easy data transfer into the main stock system.
- Allow users to manually correct OCR output before using the data.

---

## 4. Functional Requirements

### 4.1 Input Handling

- Upload image files (`.jpg`, `.jpeg`, `.png`, `.pdf`)
- Optionally capture images from webcam

### 4.2 Image Processing

- Convert to grayscale
- Apply thresholding or binarization
- Deskew and remove noise

### 4.3 OCR & Data Extraction

- Use `pytesseract` for text recognition
- Basic support for handwritten text
- Extract fields: **Item Name**, **Quantity**, **Unit**, **Price**

### 4.4 Field Mapping

- Use fixed templates or detect table layout
- Align data with expected fields

### 4.5 UI Features

- Show extracted items in a table/grid
- Editable fields for manual corrections
- "Copy" button for each row
- Option to export as CSV

### 4.6 Clipboard Integration

- Use `pyperclip` to copy data per row in a preformatted string

---

## 5. Non-Functional Requirements

- **Platform**: Desktop (Windows/Linux/macOS)
- **Language**: Python 3.8+
- **Performance**: Process a typical sheet in ≤10 seconds
- **Accuracy**: Aim for ≥90% accuracy with good image quality

---

## 6. Tools & Technologies

| Component | Technology |
| --- | --- |
| OCR | Tesseract + pytesseract |
| Image Processing | OpenCV |
| GUI | Tkinter / PyQt5 / Streamlit |
| Clipboard Access | pyperclip |
| Optional DB | SQLite / MySQL |
| Packaging | PyInstaller / cx_Freeze |

---

## 7. Potential Enhancements

- Train custom handwriting OCR model
- Multi-language support
- Direct database integration
- Mobile version (future)

---

## 8. Assumptions

- Sheet layout is consistent
- Handwriting is reasonably legible
- Users will verify and edit results as needed

