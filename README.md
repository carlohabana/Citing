# Citing
Cite
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AGLC4 Citation Converter</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background-color: #f5f5f5;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 12px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            padding: 30px;
        }
        
        h1 {
            text-align: center;
            margin-bottom: 30px;
            color: #1f2937;
            font-size: 2.25rem;
            font-weight: bold;
        }
        
        .type-selector {
            margin-bottom: 30px;
        }
        
        .type-label {
            display: block;
            margin-bottom: 15px;
            font-weight: 500;
            color: #374151;
        }
        
        .type-buttons {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 12px;
        }
        
        .type-button {
            padding: 12px 24px;
            border: 2px solid #d1d5db;
            background: white;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s;
            font-size: 14px;
            font-weight: 500;
        }
        
        .type-button:hover {
            border-color: #9ca3af;
        }
        
        .type-button.active {
            border-color: #3b82f6;
            background-color: #eff6ff;
            color: #1d4ed8;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }
        
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }
        
        .form-section h2 {
            margin-bottom: 20px;
            color: #1f2937;
            font-size: 1.5rem;
            font-weight: 600;
        }
        
        .input-group {
            margin-bottom: 16px;
        }
        
        .input-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
        }
        
        .input-row-3 {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 12px;
        }
        
        input {
            width: 100%;
            padding: 12px;
            border: 1px solid #d1d5db;
            border-radius: 8px;
            font-size: 14px;
            transition: border-color 0.2s;
        }
        
        input:focus {
            outline: none;
            border-color: #3b82f6;
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
        }
        
        .citation-section h2 {
            margin-bottom: 20px;
            color: #1f2937;
            font-size: 1.5rem;
            font-weight: 600;
        }
        
        .citation-output {
            position: relative;
            background-color: #f9fafb;
            border: 1px solid #d1d5db;
            border-radius: 8px;
            padding: 16px;
            min-height: 100px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            line-height: 1.6;
        }
        
        .citation-placeholder {
            color: #6b7280;
            font-style: italic;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
        }
        
        .copy-button {
            position: absolute;
            top: 8px;
            right: 8px;
            background: white;
            border: 1px solid #d1d5db;
            border-radius: 6px;
            padding: 8px 12px;
            cursor: pointer;
            font-size: 12px;
            transition: all 0.2s;
        }
        
        .copy-button:hover {
            background-color: #f3f4f6;
            border-color: #9ca3af;
        }
        
        .copy-success {
            color: #10b981;
            font-size: 14px;
            margin-top: 8px;
        }
        
        .tips-box {
            margin-top: 24px;
            background-color: #eff6ff;
            border-radius: 8px;
            padding: 16px;
        }
        
        .tips-title {
            font-weight: 600;
            color: #1e40af;
            margin-bottom: 8px;
        }
        
        .tips-list {
            color: #1e40af;
            font-size: 14px;
            line-height: 1.5;
            list-style: none;
        }
        
        .tips-list li {
            margin-bottom: 4px;
        }
        
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>AGLC4 Citation Converter</h1>
        
        <div class="type-selector">
            <label class="type-label">Citation Type</label>
            <div class="type-buttons">
                <button class="type-button active" data-type="case">Case Law</button>
                <button class="type-button" data-type="legislation">Legislation</button>
                <button class="type-button" data-type="journal">Journal Article</button>
                <button class="type-button" data-type="book">Book</button>
                <button class="type-button" data-type="website">Website</button>
                <button class="type-button" data-type="government">Government Document</button>
            </div>
        </div>

        <div class="main-content">
            <div class="form-section">
                <h2>Input Details</h2>
                
                <!-- Case Law Form -->
                <div id="case-form" class="citation-form">
                    <div class="input-group">
                        <input type="text" id="case-name" placeholder="Case Name (e.g., Mabo v Queensland (No 2))">
                    </div>
                    <div class="input-group input-row">
                        <input type="text" id="case-year" placeholder="Year (e.g., 1992)">
                        <input type="text" id="case-volume" placeholder="Volume (e.g., 175)">
                    </div>
                    <div class="input-group input-row">
                        <input type="text" id="case-reporter" placeholder="Reporter (e.g., CLR)">
                        <input type="text" id="case-page" placeholder="Page (e.g., 1)">
                    </div>
                    <div class="input-group input-row">
                        <input type="text" id="case-court" placeholder="Court (e.g., HCA)">
                        <input type="text" id="case-pinpoint" placeholder="Pinpoint (e.g., [23])">
                    </div>
                </div>

                <!-- Legislation Form -->
                <div id="legislation-form" class="citation-form hidden">
                    <div class="input-group">
                        <input type="text" id="leg-title" placeholder="Act Title (e.g., Competition and Consumer Act)">
                    </div>
                    <div class="input-group input-row">
                        <input type="text" id="leg-year" placeholder="Year (e.g., 2010)">
                        <input type="text" id="leg-jurisdiction" placeholder="Jurisdiction (e.g., Cth)">
                    </div>
                    <div class="input-group">
                        <input type="text" id="leg-section" placeholder="Section (e.g., 18)">
                    </div>
                </div>

                <!-- Journal Form -->
                <div id="journal-form" class="citation-form hidden">
                    <div class="input-group">
                        <input type="text" id="journal-author" placeholder="Author (e.g., John Smith)">
                    </div>
                    <div class="input-group">
                        <input type="text" id="journal-title" placeholder="Article Title">
                    </div>
                    <div class="input-group input-row-3">
                        <input type="text" id="journal-year" placeholder="Year (e.g., 2023)">
                        <input type="text" id="journal-volume" placeholder="Volume (e.g., 45)">
                        <input type="text" id="journal-page" placeholder="Page (e.g., 123)">
                    </div>
                    <div class="input-group input-row">
                        <input type="text" id="journal-name" placeholder="Journal Name">
                        <input type="text" id="journal-pinpoint" placeholder="Pinpoint (optional)">
                    </div>
                </div>

                <!-- Book Form -->
                <div id="book-form" class="citation-form hidden">
                    <div class="input-group">
                        <input type="text" id="book-author" placeholder="Author (e.g., Jane Doe)">
                    </div>
                    <div class="input-group">
                        <input type="text" id="book-title" placeholder="Book Title">
                    </div>
                    <div class="input-group input-row-3">
                        <input type="text" id="book-publisher" placeholder="Publisher">
                        <input type="text" id="book-year" placeholder="Year (e.g., 2023)">
                        <input type="text" id="book-edition" placeholder="Edition (e.g., 2nd)">
                    </div>
                    <div class="input-group">
                        <input type="text" id="book-page" placeholder="Page (optional, e.g., 45)">
                    </div>
                </div>

                <!-- Website Form -->
                <div id="website-form" class="citation-form hidden">
                    <div class="input-group">
                        <input type="text" id="web-author" placeholder="Author (optional)">
                    </div>
                    <div class="input-group">
                        <input type="text" id="web-title" placeholder="Page/Article Title">
                    </div>
                    <div class="input-group">
                        <input type="text" id="web-site" placeholder="Website Name">
                    </div>
                    <div class="input-group input-row">
                        <input type="text" id="web-date" placeholder="Date (e.g., 15 March 2023)">
                        <input type="text" id="web-url" placeholder="URL">
                    </div>
                </div>

                <!-- Government Form -->
                <div id="government-form" class="citation-form hidden">
                    <div class="input-group">
                        <input type="text" id="gov-department" placeholder="Department/Agency">
                    </div>
                    <div class="input-group">
                        <input type="text" id="gov-title" placeholder="Document Title">
                    </div>
                    <div class="input-group input-row">
                        <input type="text" id="gov-type" placeholder="Document Type (e.g., Report)">
                        <input type="text" id="gov-year" placeholder="Year (e.g., 2023)">
                    </div>
                    <div class="input-group">
                        <input type="text" id="gov-location" placeholder="Location (e.g., [23])">
                    </div>
                </div>
            </div>

            <div class="citation-section">
                <h2>Generated Citation</h2>
                <div class="citation-output">
                    <div id="citation-text" class="citation-placeholder">
                        Fill in the fields to generate your AGLC4 citation...
                    </div>
                    <button class="copy-button hidden" id="copy-button">Copy</button>
                </div>
                <div id="copy-success" class="copy-success hidden">Citation copied to clipboard!</div>
                
                <div class="tips-box">
                    <div class="tips-title">💡 Tips for AGLC4</div>
                    <ul class="tips-list">
                        <li>• Use italics for case names and book titles</li>
                        <li>• Include pinpoint references where relevant</li>
                        <li>• Abbreviate court names (e.g., HCA, NSWCA)</li>
                        <li>• Use single quotes for article titles</li>
                        <li>• Double-check all details before submitting</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <script>
        let currentType = 'case';
        
        // Citation generation functions
        function generateCaseCitation() {
            const caseName = document.getElementById('case-name').value;
            const year = document.getElementById('case-year').value;
            const volume = document.getElementById('case-volume').value;
            const reporter = document.getElementById('case-reporter').value;
            const page = document.getElementById('case-page').value;
            const court = document.getElementById('case-court').value;
            const pinpoint = document.getElementById('case-pinpoint').value;
            
            let citation = '';
            if (caseName) {
                citation += caseName;
                if (year) citation += ` (${year})`;
                if (volume && reporter && page) {
                    citation += ` ${volume} ${reporter} ${page}`;
                }
                if (pinpoint) citation += `, ${pinpoint}`;
                if (court) citation += ` (${court})`;
            }
            return citation;
        }
        
        function generateLegislationCitation() {
            const title = document.getElementById('leg-title').value;
            const year = document.getElementById('leg-year').value;
            const jurisdiction = document.getElementById('leg-jurisdiction').value;
            const section = document.getElementById('leg-section').value;
            
            let citation = '';
            if (title) {
                citation += title;
                if (year) citation += ` ${year}`;
                if (jurisdiction) citation += ` (${jurisdiction})`;
                if (section) citation += ` s ${section}`;
            }
            return citation;
        }
        
        function generateJournalCitation() {
            const author = document.getElementById('journal-author').value;
            const title = document.getElementById('journal-title').value;
            const year = document.getElementById('journal-year').value;
            const volume = document.getElementById('journal-volume').value;
            const journal = document.getElementById('journal-name').value;
            const page = document.getElementById('journal-page').value;
            const pinpoint = document.getElementById('journal-pinpoint').value;
            
            let citation = '';
            if (author) citation += `${author}, `;
            if (title) citation += `'${title}'`;
            if (year && volume && journal && page) {
                citation += ` (${year}) ${volume} ${journal} ${page}`;
            }
            if (pinpoint) citation += `, ${pinpoint}`;
            
            return citation;
        }
        
        function generateBookCitation() {
            const author = document.getElementById('book-author').value;
            const title = document.getElementById('book-title').value;
            const publisher = document.getElementById('book-publisher').value;
            const year = document.getElementById('book-year').value;
            const edition = document.getElementById('book-edition').value;
            const page = document.getElementById('book-page').value;
            
            let citation = '';
            if (author) citation += `${author}, `;
            if (title) citation += title;
            if (edition && edition !== '1') citation += ` (${edition} ed, `;
            else if (publisher || year) citation += ` (`;
            if (publisher) citation += publisher;
            if (year) citation += `${publisher ? ', ' : ''}${year}`;
            if (edition && edition !== '1') citation += `)`;
            else if (publisher || year) citation += `)`;
            if (page) citation += ` ${page}`;
            
            return citation;
        }
        
        function generateWebsiteCitation() {
            const author = document.getElementById('web-author').value;
            const title = document.getElementById('web-title').value;
            const website = document.getElementById('web-site').value;
            const date = document.getElementById('web-date').value;
            const url = document.getElementById('web-url').value;
            
            let citation = '';
            if (author) citation += `${author}, `;
            if (title) citation += `'${title}'`;
            if (website) citation += ` on ${website}`;
            if (date) citation += ` (${date})`;
            if (url) citation += ` <${url}>`;
            
            return citation;
        }
        
        function generateGovernmentCitation() {
            const department = document.getElementById('gov-department').value;
            const title = document.getElementById('gov-title').value;
            const type = document.getElementById('gov-type').value;
            const year = document.getElementById('gov-year').value;
            const location = document.getElementById('gov-location').value;
            
            let citation = '';
            if (department) citation += `${department}, `;
            if (title) citation += title;
            if (type) citation += ` (${type}`;
            if (year) citation += `${type ? ', ' : '('}${year}`;
            if (type || year) citation += `)`;
            if (location) citation += ` ${location}`;
            
            return citation;
        }
        
        function updateCitation() {
            let citation = '';
            
            switch (currentType) {
                case 'case':
                    citation = generateCaseCitation();
                    break;
                case 'legislation':
                    citation = generateLegislationCitation();
                    break;
                case 'journal':
                    citation = generateJournalCitation();
                    break;
                case 'book':
                    citation = generateBookCitation();
                    break;
                case 'website':
                    citation = generateWebsiteCitation();
                    break;
                case 'government':
                    citation = generateGovernmentCitation();
                    break;
            }
            
            const citationElement = document.getElementById('citation-text');
            const copyButton = document.getElementById('copy-button');
            
            if (citation.trim()) {
                citationElement.textContent = citation;
                citationElement.className = '';
                copyButton.classList.remove('hidden');
            } else {
                citationElement.textContent = 'Fill in the fields to generate your AGLC4 citation...';
                citationElement.className = 'citation-placeholder';
                copyButton.classList.add('hidden');
            }
        }
        
        // Event listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Type button event listeners
            document.querySelectorAll('.type-button').forEach(button => {
                button.addEventListener('click', function() {
                    // Remove active class from all buttons
                    document.querySelectorAll('.type-button').forEach(btn => btn.classList.remove('active'));
                    // Add active class to clicked button
                    this.classList.add('active');
                    
                    // Hide all forms
                    document.querySelectorAll('.citation-form').forEach(form => form.classList.add('hidden'));
                    
                    // Show selected form
                    currentType = this.dataset.type;
                    document.getElementById(currentType + '-form').classList.remove('hidden');
                    
                    // Clear citation
                    updateCitation();
                });
            });
            
            // Input event listeners
            document.addEventListener('input', updateCitation);
            
            // Copy button event listener
            document.getElementById('copy-button').addEventListener('click', function() {
                const citation = document.getElementById('citation-text').textContent;
                navigator.clipboard.writeText(citation).then(function() {
                    const successMessage = document.getElementById('copy-success');
                    successMessage.classList.remove('hidden');
                    setTimeout(() => successMessage.classList.add('hidden'), 2000);
                });
            });
        });
    </script>
</body>
</html>
