<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Philosophy Courses | Peterson Academy</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', 'Times New Roman', serif;
            line-height: 1.7;
            color: #2c3e50;
            background: #fafafa;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            color: white;
            padding: 80px 0 100px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><defs><pattern id="grid" width="100" height="100" patternUnits="userSpaceOnUse"><path d="M 100 0 L 0 0 0 100" fill="none" stroke="rgba(255,255,255,0.03)" stroke-width="1"/></pattern></defs><rect width="100%" height="100%" fill="url(%23grid)"/></svg>');
            opacity: 0.3;
        }

        header .container {
            position: relative;
            z-index: 1;
        }

        h1 {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 30px;
            line-height: 1.2;
        }

        .subhead {
            font-size: 1.3rem;
            max-width: 900px;
            margin: 0 auto 40px;
            line-height: 1.8;
            color: white;
            font-family: 'Arial', sans-serif;
        }

        .cta-primary {
            display: inline-block;
            background: #c9302c;
            color: white;
            padding: 18px 50px;
            font-size: 1.2rem;
            text-decoration: none;
            border-radius: 4px;
            font-weight: 600;
            transition: all 0.3s ease;
            margin-bottom: 30px;
            font-family: 'Arial', sans-serif;
        }

        .cta-primary:hover {
            background: #a02622;
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(201, 48, 44, 0.3);
        }

        .proof-bar {
            display: flex;
            justify-content: center;
            gap: 40px;
            flex-wrap: wrap;
            margin-top: 30px;
            font-family: 'Arial', sans-serif;
        }

        .proof-bar li {
            list-style: none;
            font-size: 0.95rem;
            color: white;
        }

        .proof-bar li::before {
            content: '✓ ';
            margin-right: 5px;
            color: #4CAF50;
        }

        /* Main Content */
        main {
            background: white;
        }

        .section {
            padding: 80px 0;
            border-bottom: 1px solid #e0e0e0;
        }

        .section:last-child {
            border-bottom: none;
        }

        .section-alt {
            background: #f8f8f8;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: #1a1a1a;
            font-weight: 600;
        }

        h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #2d2d2d;
            font-weight: 600;
        }

        h4 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: #c9302c;
            font-weight: 600;
        }

        p {
            font-size: 1.1rem;
            margin-bottom: 20px;
            color: #444;
        }

        ul {
            list-style: none;
            margin-bottom: 30px;
        }

        ul li {
            padding: 12px 0 12px 35px;
            position: relative;
            font-size: 1.1rem;
            color: #444;
        }

        ul li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: #c9302c;
            font-weight: bold;
        }

        /* Value Box */
        .value-box {
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            color: white;
            padding: 50px;
            border-radius: 8px;
            margin: 40px 0;
        }

        .value-box h3 {
            color: white;
            margin-bottom: 25px;
        }

        .value-box ul li {
            color: rgba(255, 255, 255, 0.9);
        }

        .value-box ul li::before {
            color: #4CAF50;
        }

        .pricing {
            font-size: 2rem;
            font-weight: 700;
            color: #4CAF50;
            margin-top: 30px;
        }

        /* Course Cards */
        .course-card {
            background: white;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            padding: 40px;
            margin-bottom: 40px;
            transition: all 0.3s ease;
        }

        .course-card:hover {
            border-color: #c9302c;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transform: translateY(-5px);
        }

        .course-card h3 {
            color: #c9302c;
            margin-bottom: 20px;
        }

        .course-card .takeaway {
            background: #f8f8f8;
            padding: 20px;
            border-left: 4px solid #c9302c;
            margin-top: 20px;
            font-style: italic;
        }

        /* FAQ Section */
        .faq-item {
            background: white;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            padding: 35px;
            margin-bottom: 30px;
        }

        .faq-item h3 {
            color: #c9302c;
            margin-bottom: 20px;
        }

        /* Testimonials */
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .testimonial {
            background: white;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            padding: 30px;
            font-style: italic;
            color: #555;
        }

        .testimonial::before {
            content: '"';
            font-size: 3rem;
            color: #c9302c;
            opacity: 0.3;
            line-height: 0;
        }

        /* Closing CTA */
        .closing-cta {
            text-align: center;
            padding: 100px 0;
            background: linear-gradient(135deg, #c9302c 0%, #a02622 100%);
            color: white;
        }

        .closing-cta h2 {
            color: white;
            margin-bottom: 30px;
            font-size: 2.2rem;
        }

        .closing-cta p {
            color: white;
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 40px;
        }

        .cta-secondary {
            display: inline-block;
            background: white;
            color: #c9302c;
            padding: 18px 50px;
            font-size: 1.2rem;
            text-decoration: none;
            border-radius: 4px;
            font-weight: 600;
            transition: all 0.3s ease;
            font-family: 'Arial', sans-serif;
        }

        .cta-secondary:hover {
            background: #f0f0f0;
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .guarantee {
            margin-top: 20px;
            font-size: 0.95rem;
            opacity: 0.9;
        }

        /* Responsive */
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }

            h2 {
                font-size: 1.8rem;
            }

            .subhead {
                font-size: 1.1rem;
            }

            .proof-bar {
                gap: 20px;
            }

            .section {
                padding: 50px 0;
            }

            .course-card,
            .value-box,
            .faq-item {
                padding: 25px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>Online Philosophy Courses for People Who Want to Think Clearly</h1>
            <p class="subhead">
                If you've been searching for <strong>philosophy courses online</strong> because you want more than opinions, 
                you are in the right place. Peterson Academy is built for serious learners who want structure, depth, 
                and intellectual standards that are getting harder to find.
            </p>
            <a href="#" class="cta-primary">Join Peterson Academy</a>
            <ul class="proof-bar">
                <li>$399/year, billed annually</li>
                <li>14-day money-back guarantee</li>
                <li>4 new courses monthly</li>
                <li>67,000+ students enrolled</li>
            </ul>
        </div>
    </header>

    <main>
        <!-- Problem/Solution Section -->
        <section class="section">
            <div class="container">
                <h2>The Problem This Solves</h2>
                <p>You can absorb philosophy like trivia and remain essentially unchanged.</p>
                <p>Or you can study it the way it was meant to be studied, as training for your mind.</p>
                <p>Philosophy is the discipline that teaches you to:</p>
                <ul>
                    <li>detect bad reasoning before it becomes a bad life decision</li>
                    <li>separate what is true from what is merely persuasive</li>
                    <li>speak with clarity instead of vague confidence</li>
                    <li>build a worldview you can defend under pressure</li>
                </ul>
                <p>If you want to <strong>study philosophy online</strong>, the main challenge is not access to content. 
                There is endless content.</p>
                <p>The challenge is finding an education that is coherent, rigorous, and strong enough to improve how you think.</p>
                <p><strong>That is what Peterson Academy is built for.</strong></p>
            </div>
        </section>

        <!-- Value Section -->
        <section class="section section-alt">
            <div class="container">
                <h2>What You're Actually Buying</h2>
                <p>Peterson Academy is an annual membership that gives you access to the full library of courses, 
                plus all new releases.</p>
                <p>You are not buying one class. You are buying a year of serious education and a system you can 
                return to again and again.</p>
                
                <div class="value-box">
                    <h3>What's Included:</h3>
                    <ul>
                        <li>Full access to current and future courses for one year</li>
                        <li>New courses added monthly</li>
                        <li>Optional testing (for learners who want accountability)</li>
                        <li>14-day money-back guarantee</li>
                    </ul>
                    <div class="pricing">Annual tuition: $399/year billed annually</div>
                </div>
            </div>
        </section>

        <!-- Start Here Section -->
        <section class="section">
            <div class="container">
                <h2>Start Here</h2>
                <p>If you are looking for an <strong>intro to philosophy course</strong>, start with the tool that makes 
                everything else easier.</p>
                <p style="font-size: 1.3rem; font-weight: 600; color: #c9302c; margin: 30px 0;">
                    Start with Logic. Then choose your direction: Ancient foundations, Plato, Nietzsche, and the philosophy of religion.
                </p>
                <p>This "track" is designed to meet the intent behind searches like online philosophy courses, philosophy course online, 
                study philosophy online, intro to philosophy course, and yes—philosophy certificate online / philosophy degree online.</p>
                <p><strong>You will not be treated like a child. You will be trained like an adult.</strong></p>
            </div>
        </section>

        <!-- Featured Courses -->
        <section class="section section-alt">
            <div class="container">
                <h2>Featured Courses</h2>

                <!-- Course 1: Logic -->
                <div class="course-card">
                    <h3>1) Logic | Dr. Stephen Hicks</h3>
                    <p>Most people do not lose arguments because they are stupid. They lose because they do not know what an argument is.</p>
                    <p>In <strong>Logic</strong>, a ten-hour course, Dr. Stephen Hicks guides you through the principles and real-world 
                    applications of reasoning, from foundational concepts through advanced logical systems. You learn argument structure, 
                    concept formation, fallacies, syllogisms, and both deductive and inductive logic.</p>
                    <div class="takeaway">
                        <strong>What this gives you:</strong> clearer thinking, clearer writing, and the ability to recognize when a 
                        confident claim is resting on nothing.
                    </div>
                </div>

                <!-- Course 2: Ancient Philosophy -->
                <div class="course-card">
                    <h3>2) Ancient Philosophy | Dr. James Orr</h3>
                    <p>If you want to understand Western thought, you start where it starts.</p>
                    <p>In <strong>Ancient Philosophy</strong>, a seven-hour course, Dr. James Orr explores the foundations of Greek thought, 
                    moving from the Ionian and Eleatic schools through Plato and Aristotle, and into Stoicism and Epicureanism. Along the way, 
                    you track the birth of the big concepts that still shape modern life: metaphysics, epistemology, and ethics.</p>
                    <div class="takeaway">
                        <strong>What this gives you:</strong> a foundation that makes modern debates intelligible.
                    </div>
                </div>

                <!-- Course 3: Plato -->
                <div class="course-card">
                    <h3>3) Plato: The Dawn of Thought | Dr. James Orr</h3>
                    <p>Plato is not "old material." Plato is a live wire running underneath the modern world.</p>
                    <p>In <strong>Plato: The Dawn of Thought</strong>, Dr. Orr explores Plato's intellectual world, the Dialogues, 
                    Socrates' method, and Plato's Theory of Forms. The course covers Plato's vision of the ideal city-state and traces 
                    the afterlife of his ideas through later thinkers and traditions.</p>
                    <div class="takeaway">
                        <strong>What this gives you:</strong> a higher standard for truth, knowledge, and meaning.
                    </div>
                </div>

                <!-- Course 4: Nietzsche -->
                <div class="course-card">
                    <h3>4) Introduction to Nietzsche | Dr. Jordan B. Peterson</h3>
                    <p>Many people search "Nietzsche course" because they feel the modern world is drifting toward cynicism and confusion, 
                    and they want to understand why.</p>
                    <p>In <strong>Introduction to Nietzsche</strong>, an eight-hour course, Dr. Peterson examines Nietzsche's life and 
                    enduring influence. The course covers the will to power, Nietzsche's critique of truth and morality, and the challenge 
                    of affirming life in the face of nihilism.</p>
                    <div class="takeaway">
                        <strong>What this gives you:</strong> clarity about nihilism, morality, and the cost of self-deception.
                    </div>
                </div>

                <!-- Course 5: Philosophy of Religion -->
                <div class="course-card">
                    <h3>5) The Philosophy of Religion | Dr. James Orr</h3>
                    <p>Even people who think they have "moved beyond religion" are often living inside religious assumptions they do not understand.</p>
                    <p>In <strong>The Philosophy of Religion</strong>, an eight-hour course, Dr. Orr examines classic arguments for God's existence, 
                    major challenges like the problem of evil and the Euthyphro dilemma, and the nature of religious experience. The course closes 
                    by examining how religious frameworks address the modern meaning crisis through narrative unity and existential answers.</p>
                    <div class="takeaway">
                        <strong>What this gives you:</strong> a serious grasp of the religious question, whether you are a believer, skeptic, 
                        or somewhere in between.
                    </div>
                </div>
            </div>
        </section>

        <!-- FAQ / Objections -->
        <section class="section">
            <div class="container">
                <h2>Your Questions, Answered</h2>
                
                <div class="faq-item">
                    <h3>"Why is it $399 per year?"</h3>
                    <p>Because the Academy is built to be accessible without diluting standards.</p>
                    <p>One university course can cost more than an entire year of Peterson Academy. Here, $399 buys breadth, depth, 
                    and the ability to study at your own pace across a growing library of serious courses.</p>
                    <p>Also, you do not have to "finish the semester." You can use this immediately. Start tonight with Logic and 
                    feel the difference within the first hour.</p>
                </div>

                <div class="faq-item">
                    <h3>"Is Peterson Academy accredited?"</h3>
                    <p>We are not currently accredited. We are pursuing accreditation in a number of jurisdictions. However, we are not 
                    willing to compromise the technical merits, originality or quality of our education to meet the requirements of any 
                    ideologically compromised "expert" body.</p>
                    <p style="margin-top: 20px;"><strong>Plain-English guidance:</strong><br>
                    If you need an accredited degree for licensure or a formal credential requirement, Peterson Academy may not be the right 
                    tool for that specific job.<br>
                    If you want a serious education that makes you more articulate, more competent, and harder to manipulate, it is exactly 
                    the right tool.</p>
                </div>
            </div>
        </section>

        <!-- Testimonials -->
        <section class="section section-alt">
            <div class="container">
                <h2>What Members Are Saying</h2>
                <div class="testimonial-grid">
                    <div class="testimonial">
                        These courses have fundamentally changed how I approach complex problems. The Logic course alone was worth 
                        the entire membership fee.
                    </div>
                    <div class="testimonial">
                        I've taken philosophy classes at university, but this is different. The instructors don't talk down to you, 
                        and the material is genuinely challenging in the best way.
                    </div>
                    <div class="testimonial">
                        After years of consuming surface-level content, Peterson Academy feels like finally getting access to the real thing. 
                        My thinking has become sharper and more precise.
                    </div>
                    <div class="testimonial">
                        The quality of instruction is extraordinary. Dr. Orr and Dr. Hicks make complex ideas accessible without 
                        dumbing them down. This is education for adults.
                    </div>
                    <div class="testimonial">
                        I can pace myself and revisit lectures as needed. The optional testing keeps me accountable, and the monthly 
                        additions mean I'm always learning something new.
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Closing CTA -->
    <section class="closing-cta">
        <div class="container">
            <h2>Stop Waiting for the "Right Time"</h2>
            <p>If you've been looking for <strong>online philosophy courses</strong> because you know your mind could be sharper, 
            stop waiting for the "right time." The right time is when you notice the cost of confusion.</p>
            <p>Join Peterson Academy today. Start with Logic. Build a mind that can carry weight.</p>
            <a href="#" class="cta-secondary">Join Peterson Academy (Annual Membership)</a>
            <p class="guarantee">14-day money-back guarantee</p>
        </div>
    </section>
</body>
</html>
