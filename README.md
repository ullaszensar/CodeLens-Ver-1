# CodeLens - Advanced Code Analysis Utility

A comprehensive web-based source code analysis tool designed to extract demographic data and integration patterns across multiple programming languages. Built by the **Zensar Project Diamond Team**.

![CodeLens Interface](images/1.png)

## 🚀 Quick Start Guide

This application is designed to run seamlessly on any Python environment. Simply:

1. **Download the project** files to your system
2. **Install dependencies** using pip as shown below
3. **Run the application** using the streamlit command
4. **Access your application** at `http://0.0.0.0:5000`

## 📋 Features

### Core Analysis Capabilities
- **Multi-Language Support**: Analyzes code across 8+ programming languages
  - Java, Python, JavaScript, TypeScript, C#, PHP, Ruby, XSD
- **Demographic Data Detection**: Advanced pattern recognition for personal information
- **Integration Pattern Analysis**: Identifies REST APIs, SOAP services, database operations, messaging systems
- **ZIP File Support**: Upload entire project folders as ZIP files for bulk analysis
- **Excel Analysis**: Demographic data extraction from Excel files using fuzzy matching algorithms

### Data Types Detected

#### Personal Information
- **Names**: Embossed Name, Primary Name, Secondary Name, Legal Name, DBA Name, Double Byte Name
- **Identity**: Gender, Date of Birth (DOB), Government IDs, SSN, Tax ID, Passport
- **Contact Information**: Multiple phone types, email addresses, preference language

#### Address Information  
- **Multiple Address Types**: Home, Business, Alternate, Temporary, Other
- **Address Arrays**: Support for multiple address entries

#### Advanced Analysis
- **Fuzzy Matching Algorithm**: Identifies demographic data with variations in naming
- **Pattern Confidence Scoring**: Provides match reliability metrics
- **Export Capabilities**: Generate reports in multiple formats (HTML, JSON, Excel)

### Interactive Dashboard
- **Visual Analytics**: Pie charts, bar graphs, line charts for data distribution
- **File Statistics**: Language distribution and analysis metrics
- **Integration Patterns**: Visual representation of detected patterns
- **Real-time Analysis**: Live progress tracking during code scanning

## 🛠 Installation & Setup

### Prerequisites
-  Python 3.11+
- **Web Browser** with JavaScript enabled

### Method 1: Local Development
1. **Clone/Download** the project files
2. **Install Dependencies**:
   ```bash
   pip install streamlit plotly pandas openpyxl pygments fuzzywuzzy python-levenshtein
   ```
3. **Run the Application**:
   ```bash
   streamlit run app.py --server.address 0.0.0.0 --server.port 5000
   ```
4. **Access**: Navigate to `http://0.0.0.0:5000` in your browser

## 📁 Project Structure

```
CodeLens/
├── .streamlit/
│   └── config.toml          # Streamlit configuration
├── images/
│   └── 1.png               # Application screenshot
├── app.py                  # Main Streamlit application
├── codescan.py            # Core analysis engine
├── utils.py               # Utility functions
├── styles.py              # Custom CSS styling
├── README.md              # This documentation
├── pyproject.toml         # Python project configuration
└── replit.nix            # Replit environment configuration
```

## 🎯 Usage Guide

### Code Analysis
1. **Select Input Method**:
   - **Upload Files**: Choose individual code files or ZIP folders
   - **Repository Path**: Enter path to local code directory

2. **Configure Analysis**:
   - Enter application name for organized reporting
   - Select supported file types (.py, .java, .js, .ts, .cs, .php, .rb, .xsd)

3. **Run Analysis**:
   - Click "Run Analysis" button
   - Monitor progress in real-time
   - Review results in interactive dashboard

### Excel Demographic Analysis
1. **Upload Excel File**: Must contain `attr_description` column
   - **Sample File**: Use `sample_demographic_data.xlsx` as a reference format
   - **Required Columns**: `table_name`, `attr_name`, `business_name`, `attr_description`
2. **Configure Export**: Data will be exported to 20 separate files
3. **Review Results**: 
   - Total records processed
   - Demographic matches found
   - Confidence scores and analysis metrics

#### Sample Excel Format
The Excel file should contain these columns:
- **table_name**: Database table name
- **attr_name**: Attribute/field name
- **business_name**: Business context or module name
- **attr_description**: Description of the attribute (used for demographic matching)

### Report Generation
- **HTML Reports**: Comprehensive analysis with syntax highlighting
- **JSON Exports**: Machine-readable data for integration
- **Excel Exports**: Structured demographic data in multiple files
- **Download Manager**: Organized report history with timestamps

## 🔍 Supported Demographic Data Types

### Personal Identifiers
- **Embossed Name** - Name on cards/documents
- **Primary/Secondary Name** - Main and alternative names
- **Legal Name** - Official legal identification
- **DBA Name** - "Doing Business As" name
- **Double Byte Name** - Names in Unicode/multi-byte character sets
- **Gender** - Gender information
- **DOB** - Date of Birth in various formats

### Government Identification
- **Gov IDs** - Government-issued identification numbers
- **SSN** - Social Security Numbers
- **Tax ID** - Tax identification numbers
- **Passport** - Passport information and numbers

### Contact Information
- **Phone Numbers**: Home, Business, Mobile, Alternate, Attorney, Fax, ANI
- **Email Addresses**: Servicing, E-statement, Business, Other
- **Address Types**: Home, Business, Alternate, Temporary, Other
- **Arrays**: Support for multiple phone numbers, emails, and addresses

### Account Information
- **Preference Language CD** - Language preference codes
- **Member Since Date** - Account creation/membership dates

## 📊 Analysis Features

### Pattern Detection
- **REST API Patterns**: Endpoint detection, HTTP methods, API annotations
- **SOAP Services**: WSDL files, SOAP operations, XML namespaces
- **Database Operations**: SQL queries, connection strings, database URLs
- **Messaging Systems**: Kafka, RabbitMQ, JMS implementations
- **File Operations**: CSV, Excel, JSON, Properties file handling

### Advanced Analytics
- **Fuzzy Matching**: Identifies variations in field naming conventions
- **Confidence Scoring**: Reliability metrics for each match
- **Cross-File Analysis**: Tracks patterns across multiple files
- **Statistical Reporting**: Comprehensive metrics and summaries

## 🎨 Dashboard Features

### Interactive Visualizations
- **Distribution Charts**: Pie and bar charts for demographic field distribution
- **Language Analysis**: File type and extension statistics
- **Pattern Trends**: Line graphs showing integration pattern distribution
- **Correlation Analysis**: Relationship between files, fields, and patterns

### Export & Reporting
- **Multi-Format Export**: HTML, JSON, Excel support
- **Batch Processing**: Handle multiple files simultaneously
- **Historical Reports**: Timestamped report management
- **Download Management**: Organized file download system

## 🔧 Configuration

### Streamlit Configuration (`.streamlit/config.toml`)
```toml
[server]
headless = true
address = "0.0.0.0"
port = 5000

[theme]
primaryColor = "#FF4B4B"
backgroundColor = "#0E1117"
secondaryBackgroundColor = "#262730"
textColor = "#FAFAFA"
font = "sans serif"
```

### Environment Variables
- **STREAMLIT_SERVER_PORT**: Default 5000
- **STREAMLIT_SERVER_ADDRESS**: Default 0.0.0.0

## 🐛 Troubleshooting

### Common Issues
1. **Port Already in Use**: Change port in config or stop conflicting processes
2. **File Upload Errors**: Ensure files are under size limits and in supported formats
3. **ZIP Extraction Issues**: Verify ZIP file integrity and permissions
4. **Excel Analysis Errors**: Ensure `attr_description` column exists in Excel file

### Performance Optimization
- **Large Repositories**: Consider splitting into smaller chunks
- **Memory Usage**: Monitor system resources during analysis
- **File Limits**: ZIP files should be under file size limits

## 📝 Contributing

1. **Fork the Repository**
2. **Make Changes** in your forked version
3. **Test Thoroughly** with various file types
4. **Document Changes** in commit messages
5. **Share Improvements** with the community

## 📄 License

Created by **Zensar Project Diamond Team**. This project is entitled to use only in AMEX Environment
##  Support

For issues, questions, or feature requests:
1. Check the troubleshooting section above
2. Review the console logs for detailed error information
3. Ensure all dependencies are properly installed
4. Verify file formats and structure requirements

---

**Created by Zensar Project Diamond Team**