# palestineproj.github.io
<html>
<head>
    <title>Email Link with User Input</title>
</head>
<body>
    <p>
        Dear Wayne State Community Members,
        <br><br>
       The Wayne State student body, currently camping out on university grounds to demand divestment, is reaching out to implore your support in urging the Wayne State University administration to meet with us on Wednesday, May 29 at 6pm on the encampment grounds and pass our demands. The situation is urgent, and your voice as a community member is crucial in helping us achieve a just and ethical resolution.
        <br><br>
Wayne State University is currently investing in weapon-manufacturing companies that are responsible for violence and destruction around the world. Disturbingly, these investments often target the families and communities of our own students. By providing funds to these companies, the university is perpetuating violence and contributing to a humanitarian crisis. Students approved a Divestment Resolution in the Fall of 2023. The BDS Resolution can be accessed here: <a href="https://bloximages.newyork1.vip.townnews.com/thesouthend.wayne.edu/content/tncms/assets/v3/editorial/b/f6/bf68657c-7ab3-11ee-a18a-439462851ee0/6545a243728c3.file.pdf" target="_blank">BDS Resolution (PDF)</a>. Since then, students have been met with violence and apathy in requesting this resolution be taken up with administration. The physical assault of their students by campus police and undercover police is a critical issue that is inextricably tied to the Israeli entity— especially through Wayne State University Chief Holt’s delegation trip to Israel. 
        <br><br>
      As members of this community, we have a stake in our university’s actions and a right to insist on ethical guidelines for its investments. We refuse to accept that our tuition and donations are used to support companies that contribute to the suffering of our communities.
        <br><br>
        We want to emphasize that we are law-abiding students exercising our right to peacefully assemble on our university's public property. We are not trespassers. Despite our critical pleas and the unwavering support from students, faculty, the Department of African American Studies, the Graduate Employees' Organizing Committee, and the broader community, the university has ignored our calls to pass the resolution.
        <br><br>
        Wayne State University must follow the example set by its Department of African American Studies, the Graduate Employees' Organizing Committee, the Wayne Academic Union, and the over fifty student organizations, including the Black Student Union and Arab Student Union, all of whom support these demands. It must follow the sentiment reflected by the city of Detroit, the city of Dearborn, the city of Hamtramck, and the Union of Auto-Mobile Workers, and demand a free Palestine. 
        <br><br>
        We ask for your support in urging the administration to meet with us and take immediate action. Together, we can hold our university accountable and ensure that it stands on the side of justice and ethical integrity.
        <br><br>
        Thank you for your solidarity and support.
        <br><br>
        Sincerely,
        <br>
        Members of the Liberation Zone
    </p>

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
            const recipients = 'president@wayne.edu,gx5460@wayne.edu,hp8073@wayne.edu,jenelle.michaels@wayne.edu,lbeale@wayne.edu,bgielczyk@wayne.edu,ar6659@wayne.edu, isnotrealwsu@gmail.com';
            const subject = 'URGENT: Support Pro-Palestinian Encampment and Divest from Israel';

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
            body += 'To review our detailed grievances with the offenses committed and our proposed solutions, please proceed to the complete letter: https://drive.google.com/file/d/1wbuTyeSOdA-iw4Ax8db61oEHx571fU77/view';

            const gmailLink = `https://mail.google.com/mail/?view=cm&fs=1&to=${recipients}&su=${subject}&body=${encodeURIComponent(body)}`;
            const defaultMailAppLink = `mailto:${recipients}?subject=${subject}&body=${encodeURIComponent(body)}`;

            const emailLinks = `
                <p><a href="${gmailLink}" target="_blank">Open in Gmail (Desktop Users) </a></p>
                <p><a href="${defaultMailAppLink}">Open in Default Mail App</a></p>
            `;

            document.getElementById('emailLinks').innerHTML = emailLinks;
        });
    </script>
</body>
</html>
