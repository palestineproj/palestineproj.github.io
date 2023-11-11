# palestineproj.github.io
<html>
<head>
    <title>Email Link with User Input</title>
</head>
<body>
    <form id="emailForm">
        <label for="name">Your Name:</label>
        <input type="text" id="name" required>
        
        <label for="role">Your Role:</label>
        <select id="role">
            <option value="Student">Student</option>
            <option value="Alumni">Alumni</option>
            <option value="Administrator">Administrator</option>
            <option value="Faculty">Faculty</option>
            <option value="Community Member">Community Member</option>
            <option value="Concerned Citizen">Concerned Citizen</option>
        </select>

        <label for="wsuMember">Are you a member of Wayne State University?</label>
        <select id="wsuMember">
            <option value="Yes">Yes</option>
            <option value="No">No</option>
        </select>

        <button type="button" id="generateEmailLinks">Generate Email Links</button>
    </form>

    <div id="emailLinks"></div>

    <script>
        document.getElementById('generateEmailLinks').addEventListener('click', function () {
            const name = document.getElementById('name').value;
            const role = document.getElementById('role').value;
            const wsuMember = document.getElementById('wsuMember').value;
            const recipient = 'zeinabalghanem@gmail.com,hh0816@wayne.edu';
            const subject = 'URGENT: Grievances and Discrimination at Wayne State University';

            let body = `${name}\n${role}\n`;

            if (wsuMember === 'Yes') {
                body += 'Wayne State University\n';
            }

            body += '\nDear Wayne State University Administration,\n\n';
            body += 'I am writing to express my unwavering support for the Student Senate Resolution 2324-03 and to voice serious concerns about recent events at our university. These issues occurred in the wake of the resolution proposal and adoption, pointing to a worrying trend of discrimination and injustice. This grievance letter highlights my concerns to encourage a more inclusive and fair Wayne State University.\n\n';
            body += '1. Concerns Regarding Dean David J. Strauss:\n';
            body += '   - Discriminatory Policy Changes: Dean Strauss\'s policy alterations, timed in a manner that raises questions about their motivation, have the potential to discriminate against specific groups of students.\n';
            body += '   - Suppression of Dissent: His actions have suppressed dissenting voices, hindering open dialogue and stifling the principles of academic freedom that form the bedrock of our institution.\n';
            body += '   - Failure to Uphold University Principles: Dean Strauss\'s actions are at odds with Wayne State University\'s principles.\n';
            body += '   - Coercion and Fear-Mongering: Dean Strauss issuing warnings to students, laden with implications of potential repercussions, raise concerns about the abuse of power and free expression.\n\n';
            body += '2. Abuse of Power Through Email Communication:\n';
            body += '   The email sent by Dean Strauss in the wake of peaceful campus protests demonstrates an abuse of power, perpetuating discrimination and silencing the voices of concerned students.\n\n';
            body += '3. Racist WSU-Facilitated Interfaith Dialogues: The university facilitation in interfaith dialogues, led by Professors Khan and Lupovitch, has led to a one-sided representation that perpetrates harmful, racist rhetoric and disregards the Palestinian perspective, thereby committing a grave injustice.\n\n';
            body += '4. Hurtful Email Following a Peaceful Campus Protest: The email sent to our university community following a peaceful campus protest raises questions about the institutional commitment to respect, justice, and inclusion.\n\n';
            body += '5. Proposed Solutions: The constructive solutions to rectify the harm caused and foster a more inclusive and just environment at Wayne State University.\n\n';
            body += 'To review our detailed grievances with the offenses committed and our proposed solutions, please proceed to the complete letter: https://drive.google.com/file/d/1BhJif4Ete3i28si0lPjaReT6gdU82TVg/view?usp=sharing';

            const gmailLink = `https://mail.google.com/mail/?view=cm&fs=1&to=${recipient}&su=${subject}&body=${encodeURIComponent(body)}`;
            const defaultMailAppLink = `mailto:${recipient}?subject=${subject}&body=${encodeURIComponent(body)}`;

            const emailLinks = `
                <p><a href="${gmailLink}" target="_blank">Open in Gmail</a></p>
                <p><a href="${defaultMailAppLink}">Open in Default Mail App</a></p>
            `;

            document.getElementById('emailLinks').innerHTML = emailLinks;
        });
    </script>
</body>
</html>
