# BharatFormshubgov
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>India GovForms Hub | Official Directory & Assistant</title>
    <style>
        :root {
            --primary: #0a3d62;
            --primary-light: #3c6382;
            --accent: #e67e22;
            --success: #27ae60;
            --danger: #eb4d4b;
            --bg: #f5f6fa;
            --card: #ffffff;
            --text: #2f3542;
            --text-muted: #747d8c;
            --border: #dcdde1;
            --white: #ffffff;
        }

        [data-theme="dark"] {
            --bg: #1e272e;
            --card: #2f3542;
            --text: #f1f2f6;
            --text-muted: #a4b0be;
            --border: #57606f;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background-color: var(--bg); color: var(--text); transition: 0.3s; line-height: 1.6; }

        /* --- Global Disclaimer --- */
        .disclaimer-bar {
            background: #fff3cd; color: #856404; text-align: center;
            padding: 8px 15px; font-size: 0.85rem; font-weight: bold;
            border-bottom: 1px solid #ffeeba; position: sticky; top: 0; z-index: 1100;
        }

        /* --- Header & Nav --- */
        header { background: var(--primary); color: white; padding: 10px 0; position: sticky; top: 35px; z-index: 1000; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        .nav-container { max-width: 1200px; margin: 0 auto; padding: 0 20px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; }
        .logo { font-size: 1.5rem; font-weight: bold; display: flex; align-items: center; gap: 10px; cursor: pointer; }
        .logo span { color: var(--accent); }
        
        .search-box { flex: 1; margin: 10px 20px; min-width: 250px; position: relative; }
        .search-box input { width: 100%; padding: 10px 15px; border-radius: 4px; border: none; outline: none; }

        .nav-utils { display: flex; gap: 15px; align-items: center; }
        .btn-icon { background: none; border: 1px solid rgba(255,255,255,0.3); color: white; padding: 5px 10px; cursor: pointer; border-radius: 4px; }

        /* --- Tabs --- */
        .tabs-container { background: var(--card); border-bottom: 1px solid var(--border); overflow-x: auto; }
        .tabs { max-width: 1200px; margin: 0 auto; display: flex; }
        .tab-btn { padding: 15px 20px; border: none; background: none; color: var(--text-muted); cursor: pointer; font-weight: 600; white-space: nowrap; border-bottom: 3px solid transparent; }
        .tab-btn.active { color: var(--primary); border-bottom-color: var(--primary); }

        /* --- Main Content --- */
        main { max-width: 1200px; margin: 20px auto; padding: 0 20px; min-height: 70vh; }
        .section { display: none; animation: fadeIn 0.3s ease; }
        .section.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* --- Grid & Cards --- */
        .filters { display: flex; gap: 10px; margin-bottom: 20px; flex-wrap: wrap; }
        .filters select { padding: 8px; border: 1px solid var(--border); border-radius: 4px; background: var(--card); color: var(--text); }
        
        .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(350px, 1fr)); gap: 20px; }
        .card { background: var(--card); border: 1px solid var(--border); border-radius: 8px; padding: 20px; display: flex; flex-direction: column; transition: 0.2s; }
        .card:hover { transform: translateY(-3px); box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        .card-header { display: flex; justify-content: space-between; margin-bottom: 10px; }
        .badge { font-size: 0.7rem; padding: 3px 8px; border-radius: 12px; font-weight: bold; text-transform: uppercase; }
        .badge-central { background: #e3f2fd; color: #1565c0; }
        .badge-state { background: #f1f8e9; color: #2e7d32; }
        
        .card h3 { margin-bottom: 10px; font-size: 1.1rem; }
        .card p { font-size: 0.9rem; color: var(--text-muted); flex: 1; margin-bottom: 15px; }
        
        .url-validator { font-size: 0.75rem; margin-bottom: 15px; padding: 5px; border-radius: 4px; }
        .valid-gov { background: rgba(39, 174, 96, 0.1); color: var(--success); }
        .unknown-gov { background: rgba(235, 77, 75, 0.1); color: var(--danger); }

        .card-actions { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .btn { padding: 10px; border: none; border-radius: 4px; cursor: pointer; font-weight: 600; text-align: center; text-decoration: none; font-size: 0.85rem; }
        .btn-full { grid-column: span 2; }
        .btn-gov { background: var(--primary); color: white; }
        .btn-sec { background: var(--bg); color: var(--text); border: 1px solid var(--border); }
        .btn-accent { background: var(--accent); color: white; }

        /* --- Assistant Form --- */
        .assistant-box { max-width: 800px; margin: 0 auto; background: var(--card); padding: 30px; border-radius: 8px; border: 1px solid var(--border); }
        .input-group { margin-bottom: 15px; }
        .input-group label { display: block; margin-bottom: 5px; font-weight: 600; }
        .input-group input, .input-group select, .input-group textarea { width: 100%; padding: 10px; border: 1px solid var(--border); border-radius: 4px; background: var(--bg); color: var(--text); }
        .preview-area { margin-top: 20px; padding: 20px; background: #f8f9fa; border: 1px dashed #ccc; color: #333; }

        /* --- Footer --- */
        footer { background: var(--primary); color: white; padding: 40px 20px; text-align: center; margin-top: 50px; }
        .safety-tips { background: rgba(255,255,255,0.1); padding: 20px; border-radius: 8px; max-width: 800px; margin: 0 auto 20px; text-align: left; }
        
        @media (max-width: 768px) {
            .nav-container { flex-direction: column; }
            .grid { grid-template-columns: 1fr; }
            .card-actions { grid-template-columns: 1fr; }
            .btn-full { grid-column: auto; }
        }
    </style>
</head>
<body>

<div class="disclaimer-bar">
    ⚠️ NOT AN OFFICIAL GOVERNMENT WEBSITE. We provide links & guidance only. Never share OTPs.
</div>

<header>
    <div class="nav-container">
        <div class="logo" onclick="showSection('all-forms')">Bharat<span>Forms</span>Hub</div>
        <div class="search-box">
            <input type="text" id="searchInput" placeholder="Search forms (e.g. PAN, Aadhar, Ration Card...)" oninput="filterForms()">
        </div>
        <div class="nav-utils">
            <button class="btn-icon" onclick="toggleDarkMode()">🌓</button>
            <select id="langSelect" class="btn-icon" style="background:var(--primary-light)">
                <option value="en">English</option>
                <option value="hi">हिंदी</option>
            </select>
        </div>
    </div>
</header>

<nav class="tabs-container">
    <div class="tabs">
        <button class="tab-btn active" onclick="showSection('all-forms', this)">All Forms</button>
        <button class="tab-btn" onclick="showSection('assistant', this)">Form Assistant</button>
        <button class="tab-btn" onclick="showSection('checklist', this)">Documents Checklist</button>
        <button class="tab-btn" onclick="showSection('status', this)">Track Status</button>
        <button class="tab-btn" onclick="showSection('help', this)">Help</button>
    </div>
</nav>

<main>
    <section id="all-forms" class="section active">
        <div class="filters">
            <select id="filterCategory" onchange="filterForms()">
                <option value="">All Categories</option>
                <option value="Personal Identity">Personal Identity</option>
                <option value="Travel">Travel & Transport</option>
                <option value="Financial">Financial & Tax</option>
                <option value="Social Welfare">Social Welfare</option>
            </select>
            <select id="filterType" onchange="filterForms()">
                <option value="">Central & State</option>
                <option value="Central">Central Govt</option>
                <option value="State">State Govt</option>
            </select>
        </div>
        <div class="grid" id="formsGrid">
            </div>
    </section>

    <section id="assistant" class="section">
        <div class="assistant-box">
            <h2 style="margin-bottom:10px">Form Preparation Assistant</h2>
            <p style="color:var(--text-muted); margin-bottom:20px">Fill your details below to generate a summary. You can copy this information to paste into official portals.</p>
            
            <div class="input-group">
                <label>Target Form</label>
                <select id="targetFormSelect">
                    <option value="">Select a form to load requirements...</option>
                </select>
            </div>
            
            <div id="dynamicFields">
                <div class="input-group"><label>Full Name (as per ID)</label><input type="text" id="asst_name"></div>
                <div class="input-group"><label>Date of Birth</label><input type="date" id="asst_dob"></div>
                <div class="input-group"><label>Address</label><textarea id="asst_addr"></textarea></div>
                <div class="input-group"><label>Aadhar Number (Last 4 digits for ref)</label><input type="text" maxlength="4" id="asst_id"></div>
            </div>

            <div class="card-actions">
                <button class="btn btn-accent" onclick="generateSummary()">Generate Fill-Summary</button>
                <button class="btn btn-sec" onclick="saveProfile()">Save to My Profile (Local)</button>
            </div>

            <div id="summaryPreview" class="preview-area" style="display:none">
                <h4 id="summaryTitle">Summary</h4>
                <div id="summaryContent" style="margin:15px 0; font-family:monospace; font-size:0.9rem"></div>
                <button class="btn btn-sec" onclick="printSummary()">Print Summary</button>
                <button class="btn btn-sec" onclick="copySummary()">Copy Text</button>
            </div>
        </div>
    </section>

    <section id="checklist" class="section">
        <div class="assistant-box">
            <h2>Essential Documents Checklist</h2>
            <p style="margin-bottom:20px">Tick off the documents you have ready before starting your application.</p>
            <div id="checklistItems">
                </div>
            <button class="btn btn-accent" style="margin-top:20px" onclick="window.print()">Print Checklist</button>
        </div>
    </section>

    <section id="status" class="section">
        <div class="assistant-box">
            <h2>Track Application Status</h2>
            <p>Select the service type to get the official tracking link.</p>
            <div class="input-group" style="margin-top:20px">
                <label>Service Category</label>
                <select id="trackSelect" onchange="updateTrackLink()">
                    <option value="">-- Select Service --</option>
                    <option value="https://passportindia.gov.in/AppOnlineProject/statusTracker/trackStatusInpNew">Passport Status</option>
                    <option value="https://tin.tin.nsdl.com/pantan/StatusTrack.html">PAN Card Status</option>
                    <option value="https://myaadhaar.uidai.gov.in/CheckAadhaarStatus">Aadhar Update Status</option>
                    <option value="https://voters.eci.gov.in/track-application">Voter ID Status</option>
                </select>
            </div>
            <div id="trackGuidance" style="display:none; padding:20px; background:var(--bg); border-radius:8px">
                <p><strong>Guidance:</strong> Keep your Acknowledgement Number or Enrollment ID ready. Click the button below to visit the 100% official tracking portal.</p>
                <a id="trackLinkBtn" href="#" target="_blank" class="btn btn-gov btn-full" style="display:inline-block; margin-top:15px">Go to Official Tracking Page</a>
            </div>
        </div>
    </section>

    <section id="help" class="section">
        <div class="assistant-box">
            <h2>Need Help?</h2>
            <p>Steps to use BharatFormsHub safely:</p>
            <ol style="margin:20px 0; padding-left:20px">
                <li>Search for your desired form in the <strong>All Forms</strong> tab.</li>
                <li>Click <strong>Checklist</strong> to see what documents are needed.</li>
                <li>Use the <strong>Assistant</strong> to type out your details so you don't make mistakes while filling.</li>
                <li>Click <strong>Open Official Website</strong> to go to the government portal.</li>
                <li>Copy details from your assistant summary to the official site.</li>
            </ol>
            <div style="background:var(--danger); color:white; padding:15px; border-radius:4px">
                <strong>Safety Tip:</strong> We NEVER ask for your full Aadhar, Bank Passwords, or OTP. If a link doesn't end in .gov.in or .nic.in, be extremely cautious.
            </div>
        </div>
    </section>
</main>

<footer>
    <div class="safety-tips">
        <h4>🛡️ Cyber Safety for Citizens</h4>
        <ul>
            <li>Always check the URL. Official Indian government sites end in <strong>.gov.in</strong></li>
            <li>Do not pay any "service fee" on third-party websites for free government forms.</li>
            <li>Keep your mobile number linked with Aadhar for easy OTP verification on official sites.</li>
        </ul>
    </div>
    <p>Powered by <strong>Satyam Web Design</strong></p>
    <p style="font-size:0.8rem; margin-top:10px; opacity:0.8">This project provides a unified interface for all major Indian Government Facilities.</p>
</footer>

<script>
    // --- Data Layer ---
    const forms = [
        { id: 1, name: "Aadhar Card - Address Update", category: "Personal Identity", type: "Central", url: "https://myaadhaar.uidai.gov.in/", desc: "Update your residential address online with valid proof.", docs: ["Aadhar Number", "Registered Mobile", "Address Proof PDF"] },
        { id: 2, name: "PAN Card - New / Correction", category: "Financial", type: "Central", url: "https://www.onlineservices.nsdl.com/paam/endUserRegisterContact.html", desc: "Apply for new PAN or changes in existing PAN card.", docs: ["ID Proof", "DOB Proof", "Photo", "Signature"] },
        { id: 3, name: "Voter ID - New Registration", category: "Personal Identity", type: "Central", url: "https://voters.eci.gov.in/", desc: "Register as a new voter (Form 6) for upcoming elections.", docs: ["Age Proof", "Address Proof", "Passport Photo"] },
        { id: 4, name: "Passport Seva - Fresh Application", category: "Travel", type: "Central", url: "https://www.passportindia.gov.in/", desc: "Online application for fresh or reissue of Indian Passport.", docs: ["Birth Proof", "Address Proof", "Non-ECR Proof"] },
        { id: 5, name: "Driving License (Sarathi)", category: "Travel", type: "Central", url: "https://sarathi.parivahan.gov.in/", desc: "Learner License, Permanent DL, and Renewal services.", docs: ["Age Proof", "Address Proof", "Learner License No."] },
        { id: 6, name: "Income Tax Return (ITR)", category: "Financial", type: "Central", url: "https://www.incometax.gov.in/", desc: "File your annual income tax returns for individuals and businesses.", docs: ["Form 16", "Bank Statements", "Investment Proofs"] },
        { id: 7, name: "PM Kisan Samman Nidhi", category: "Social Welfare", type: "Central", url: "https://pmkisan.gov.in/", desc: "Check status or register for farmer benefits.", docs: ["Land Documents", "Aadhar Card", "Bank Account"] },
        { id: 8, name: "Ration Card - State Portal", category: "Social Welfare", type: "State", url: "https://nfsa.gov.in/portal/ration_card_state_portals_aa", desc: "Find your state-specific ration card portal.", docs: ["Family Photo", "Income Certificate", "Address Proof"] },
        { id: 9, name: "Digital Gujarat - Scholarship", category: "Social Welfare", type: "State", url: "https://www.digitalgujarat.gov.in/", desc: "Apply for various state scholarships for students.", docs: ["Caste Certificate", "Income Certificate", "Marksheets"] },
        { id: 10, name: "UP e-District Services", category: "Social Welfare", type: "State", url: "https://edistrict.up.gov.in/", desc: "Caste, Income, Domicile certificates for Uttar Pradesh.", docs: ["Self Declaration", "Ration Card", "Identity Proof"] },
        { id: 11, name: "PF (EPFO) - UAN Member Portal", category: "Financial", type: "Central", url: "https://unifiedportal-mem.epfindia.gov.in/", desc: "Check PF balance, update KYC, or withdraw PF online.", docs: ["UAN Number", "Aadhar linked Mobile", "Bank KYC"] },
        { id: 12, name: "GST Registration / Filing", category: "Financial", type: "Central", url: "https://www.gst.gov.in/", desc: "Official portal for Goods and Services Tax compliance.", docs: ["PAN of Business", "Address Proof", "Bank Account"] },
        { id: 13, name: "E-Shram Card Registration", category: "Social Welfare", type: "Central", url: "https://eshram.gov.in/", desc: "National Database of Unorganized Workers.", docs: ["Aadhar", "Bank Account", "Mobile Number"] },
        { id: 14, name: "Ayushman Bharat (PM-JAY)", category: "Social Welfare", type: "Central", url: "https://setu.pmjay.gov.in/", desc: "Apply for Golden Card for free medical treatment.", docs: ["Ration Card", "Aadhar", "HHID Number"] },
        { id: 15, name: "Birth / Death Certificate", category: "Personal Identity", type: "Central", url: "https://crsorgi.gov.in/", desc: "Civil Registration System of India.", docs: ["Hospital Slip", "ID of Parents", "Affidavit"] },
        { id: 16, name: "Vehicle RC - Vahan Portal", category: "Travel", type: "Central", url: "https://vahan.parivahan.gov.in/", desc: "Registration Certificate services for motor vehicles.", docs: ["Chassis Number", "Insurance Copy", "ID Proof"] },
        { id: 17, name: "Udyam Registration (MSME)", category: "Financial", type: "Central", url: "https://udyamregistration.gov.in/", desc: "Free registration for Small and Medium Enterprises.", docs: ["Aadhar Number", "GSTIN (if applicable)", "PAN"] },
        { id: 18, name: "Consumer Complaint (e-Daakhil)", category: "Social Welfare", type: "Central", url: "https://edaakhil.nic.in/", desc: "File consumer court complaints online.", docs: ["Invoice", "Proof of Transaction", "Notice Copy"] },
        { id: 19, name: "Ladli Behna Yojana (MP)", category: "Social Welfare", type: "State", url: "https://cmladlibehna.mp.gov.in/", desc: "State specific welfare scheme for women in MP.", docs: ["Samagra ID", "Aadhar", "Mobile"] },
        { id: 20, name: "NREGA - Job Card", category: "Social Welfare", type: "Central", url: "https://nrega.nic.in/", desc: "Check job card list or application details.", docs: ["Family Details", "Photo", "Bank Account"] }
    ];

    // --- UI Logic ---
    function init() {
        populateForms(forms);
        populateChecklist();
        populateAssistantDropdown();
    }

    function populateForms(data) {
        const grid = document.getElementById('formsGrid');
        grid.innerHTML = '';
        data.forEach(form => {
            const isGov = form.url.includes('.gov.in') || form.url.includes('.nic.in');
            const card = document.createElement('div');
            card.className = 'card';
            card.innerHTML = `
                <div class="card-header">
                    <span class="badge badge-${form.type.toLowerCase()}">${form.type}</span>
                    <span style="font-size:1.2rem; cursor:pointer" onclick="toggleFav(${form.id})">⭐</span>
                </div>
                <h3>${form.name}</h3>
                <p>${form.desc}</p>
                <div class="url-validator ${isGov ? 'valid-gov' : 'unknown-gov'}">
                    ${isGov ? '✓ Official Govt Link' : '⚠ External/Third Party'}
                </div>
                <div class="card-actions">
                    <a href="${form.url}" target="_blank" class="btn btn-gov btn-full">Open Official Website</a>
                    <button class="btn btn-sec" onclick="showDocs(${form.id})">Checklist</button>
                    <button class="btn btn-accent" onclick="loadInAssistant(${form.id})">Assistant</button>
                </div>
            `;
            grid.appendChild(card);
        });
    }

    function filterForms() {
        const query = document.getElementById('searchInput').value.toLowerCase();
        const cat = document.getElementById('filterCategory').value;
        const type = document.getElementById('filterType').value;

        const filtered = forms.filter(f => {
            const matchQuery = f.name.toLowerCase().includes(query) || f.desc.toLowerCase().includes(query);
            const matchCat = cat === "" || f.category === cat;
            const matchType = type === "" || f.type === type;
            return matchQuery && matchCat && matchType;
        });
        populateForms(filtered);
    }

    function showSection(sectionId, btn) {
        document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
        document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
        document.getElementById(sectionId).classList.add('active');
        if(btn) btn.classList.add('active');
    }

    // --- Assistant Logic ---
    function populateAssistantDropdown() {
        const select = document.getElementById('targetFormSelect');
        forms.forEach(f => {
            const opt = document.createElement('option');
            opt.value = f.id;
            opt.textContent = f.name;
            select.appendChild(opt);
        });
    }

    function generateSummary() {
        const name = document.getElementById('asst_name').value;
        const dob = document.getElementById('asst_dob').value;
        const addr = document.getElementById('asst_addr').value;
        const idLast = document.getElementById('asst_id').value;
        
        if(!name || !dob) {
            alert("Please fill basic details!");
            return;
        }

        const content = `
            FORM PREPARATION DATA:
            Full Name: ${name}
            D.O.B: ${dob}
            Address: ${addr}
            Aadhar (Ref): XXXX-XXXX-${idLast}
            Generated on: ${new Date().toLocaleDateString()}
        `;
        document.getElementById('summaryContent').innerText = content;
        document.getElementById('summaryPreview').style.display = 'block';
    }

    function loadInAssistant(id) {
        showSection('assistant', document.querySelectorAll('.tab-btn')[1]);
        document.getElementById('targetFormSelect').value = id;
    }

    // --- Checklist Logic ---
    function populateChecklist() {
        const container = document.getElementById('checklistItems');
        const items = ["Aadhar Card", "PAN Card", "Voter ID", "Ration Card", "Income Certificate", "Caste Certificate", "Domicile Certificate", "Passport Sized Photos (4)", "Bank Passbook"];
        container.innerHTML = items.map(item => `
            <div style="margin-bottom:10px; display:flex; align-items:center; gap:10px">
                <input type="checkbox" style="width:20px; height:20px">
                <label>${item}</label>
            </div>
        `).join('');
    }

    function showDocs(id) {
        const form = forms.find(f => f.id === id);
        alert(`Required Documents for ${form.name}:\n\n- ${form.docs.join('\n- ')}`);
    }

    // --- Status Logic ---
    function updateTrackLink() {
        const val = document.getElementById('trackSelect').value;
        const box = document.getElementById('trackGuidance');
        const link = document.getElementById('trackLinkBtn');
        if(val) {
            box.style.display = 'block';
            link.href = val;
        } else {
            box.style.display = 'none';
        }
    }

    function toggleDarkMode() {
        document.body.dataset.theme = document.body.dataset.theme === 'dark' ? 'light' : 'dark';
    }

    function copySummary() {
        const text = document.getElementById('summaryContent').innerText;
        navigator.clipboard.writeText(text);
        alert("Summary copied! Now paste it into the official form.");
    }

    window.onload = init;
</script>

</body>
</html>
