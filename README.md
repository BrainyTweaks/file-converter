# 🔄 File Converter

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/release/python-380/)
[![Flask](https://img.shields.io/badge/Flask-2.3.0+-green.svg)](https://flask.palletsprojects.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A powerful, web-based file conversion tool with a sleek dark UI that supports multiple file formats. Transform your files effortlessly with drag-and-drop functionality and real-time previews.

## ✨ Features

### 🚀 **Core Capabilities**
- **Drag & Drop Interface**: Intuitive file upload with visual feedback
- **Real-time Preview**: See conversion results before downloading
- **Batch Processing**: Handle multiple file formats seamlessly
- **Dark Theme UI**: Modern, responsive design with smooth animations
- **Progress Tracking**: Visual feedback during conversion process

### 📄 **Supported Formats**

#### **Data Formats**
- **CSV** ↔ JSON, XML, Excel (.xlsx), TXT, PDF, DOCX, HTML
- **JSON** ↔ CSV, XML, Excel (.xlsx), TXT, PDF, DOCX, HTML
- **XML** ↔ TXT, PDF, DOCX, HTML, JSON

#### **Document Formats**
- **PDF** → TXT, DOCX, HTML, JSON, CSV (text extraction)
- **DOCX** → TXT, PDF, HTML, JSON, CSV (text extraction)
- **PPTX** → TXT, PDF, DOCX, HTML, JSON (slide content extraction)
- **TXT** → PDF, DOCX, HTML, JSON

#### **Web Formats**
- **Markdown (.md)** → HTML, TXT, PDF, DOCX
- **HTML** → TXT, PDF, DOCX

#### **Image Formats**
- **JPG/JPEG** ↔ PNG, BMP, GIF
- **PNG** ↔ JPG/JPEG, BMP, GIF
- **BMP** ↔ JPG/JPEG, PNG, GIF
- **GIF** ↔ JPG/JPEG, PNG, BMP

## 🛠️ Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/file-converter.git
cd file-converter
```

### 2. Create Virtual Environment
```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Application
```bash
python app.py
```

The application will start on `http://localhost:5000`

## 🚀 Usage

### Web Interface
1. **Upload File**: Drag and drop your file or click to browse
2. **Select Format**: Choose your desired output format from the grid
3. **Convert**: Click the "Convert File" button
4. **Download**: Download your converted file once processing is complete

### API Endpoints

#### Convert File
```http
POST /convert
```

**Parameters:**
- `file`: The file to convert (multipart/form-data)
- `target_format`: Target format (string)

**Response:**
```json
{
  "success": true,
  "filename": "converted_file.json",
  "file_id": "unique-id",
  "preview": "File content preview..."
}
```

#### Download Converted File
```http
GET /download/<file_id>/<filename>
```

## 🏗️ Project Structure

```
file-converter/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── templates/
│   └── index.html        # Web interface template
├── temp_uploads/         # Temporary upload directory
├── test_data.csv         # Sample test data
├── venv/                 # Virtual environment (created after setup)
└── README.md            # Project documentation
```

## 🔧 Configuration

### Environment Variables
- `FLASK_ENV`: Set to `development` for debug mode
- `SECRET_KEY`: Change the default secret key in production

### File Upload Limits
- Maximum file size: 50MB
- Supported file extensions are defined in `ALLOWED_EXTENSIONS`

### Security Settings
```python
app.config['MAX_CONTENT_LENGTH'] = 50 * 1024 * 1024  # 50MB
app.secret_key = 'your_secret_key_here'  # Change in production
```

## 🧪 Testing

### Sample Data
The project includes `test_data.csv` for testing conversions:
```csv
name,age,city
John,25,New York
Jane,30,Los Angeles
Bob,35,Chicago
```

### Testing Conversions
1. Upload the sample CSV file
2. Convert to different formats (JSON, XML, Excel, etc.)
3. Verify the output and download functionality

## 🎨 UI Features

### Dark Theme
- Modern gradient backgrounds
- Smooth animations and transitions
- Responsive design for all screen sizes
- Visual feedback for user interactions

### Interactive Elements
- Hover effects on buttons and cards
- Progress bars with animated filling
- Drag-and-drop visual states
- Format selection with color-coded icons

## 🔍 Advanced Features

### Document Processing
- **PDF Text Extraction**: Uses `pdfplumber` with `PyMuPDF` fallback
- **PowerPoint Processing**: Extracts text, tables, and slide notes
- **Word Document Handling**: Full text extraction and formatting preservation

### Image Processing
- **Format Conversion**: Lossless conversion between major formats
- **Color Space Handling**: Automatic RGBA to RGB conversion for JPEG
- **Transparency Support**: Preserves transparency in compatible formats

### Error Handling
- Comprehensive error messages
- Graceful fallbacks for failed operations
- User-friendly error display in the UI

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Troubleshooting

### Common Issues

#### Dependencies Installation
If you encounter issues installing dependencies:
```bash
pip install --upgrade pip
pip install -r requirements.txt --no-cache-dir
```

#### PyMuPDF Installation Issues
For systems having trouble with PyMuPDF:
```bash
pip install --upgrade pymupdf
```

#### Large File Processing
For files larger than 50MB, adjust the configuration:
```python
app.config['MAX_CONTENT_LENGTH'] = 100 * 1024 * 1024  # 100MB
```

### Performance Tips
- Use smaller files for faster processing
- Close browser tabs to free up memory
- Clear temporary files periodically

## 🌟 Acknowledgments

- **Flask** - Web framework
- **pandas** - Data manipulation
- **ReportLab** - PDF generation
- **python-docx** - Word document processing
- **Pillow** - Image processing
- **python-pptx** - PowerPoint processing

## 📞 Support

If you encounter any issues or have questions:
1. Check the [Issues](https://github.com/your-username/file-converter/issues) page
2. Create a new issue with detailed description
3. Include error messages and steps to reproduce

---

<div align="center">
  <strong>Transform your files with style! ✨</strong>
</div>
