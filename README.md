<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mansi Thorat - Data Professional</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .resume-container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            position: relative;
        }

        .header {
            background: linear-gradient(135deg, #2c3e50 0%, #3498db 100%);
            color: white;
            padding: 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>') repeat;
            opacity: 0.3;
        }

        .header-content {
            position: relative;
            z-index: 2;
        }

        .name {
            font-size: 3.5em;
            font-weight: 800;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            background: linear-gradient(45deg, #ffffff, #e8f4fd);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .title {
            font-size: 1.3em;
            opacity: 0.9;
            margin-bottom: 20px;
            font-weight: 300;
        }

        .data-visualization {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .data-point {
            background: rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 15px 25px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            transition: transform 0.3s ease;
        }

        .data-point:hover {
            transform: translateY(-5px);
        }

        .data-number {
            font-size: 2em;
            font-weight: bold;
            display: block;
        }

        .data-label {
            font-size: 0.9em;
            opacity: 0.8;
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            padding: 40px;
        }

        .section {
            margin-bottom: 40px;
        }

        .section-title {
            font-size: 1.8em;
            font-weight: 700;
            color: #2c3e50;
            margin-bottom: 20px;
            position: relative;
            padding-left: 20px;
        }

        .section-title::before {
            content: '';
            position: absolute;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 4px;
            height: 30px;
            background: linear-gradient(135deg, #3498db, #2980b9);
            border-radius: 2px;
        }

        .about-text {
            font-size: 1.1em;
            line-height: 1.8;
            color: #34495e;
            text-align: justify;
        }

        .education-item {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 15px;
            border-left: 4px solid #3498db;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .education-item:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.2);
        }

        .degree {
            font-weight: 600;
            color: #2c3e50;
            font-size: 1.1em;
        }

        .institution {
            color: #7f8c8d;
            font-style: italic;
        }

        .project-category {
            margin-bottom: 30px;
        }

        .category-title {
            font-size: 1.4em;
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .category-icon {
            width: 30px;
            height: 30px;
            background: linear-gradient(135deg, #3498db, #2980b9);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .project-item {
            background: white;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 15px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            border-left: 4px solid transparent;
            background-image: linear-gradient(white, white), linear-gradient(135deg, #3498db, #2980b9);
            background-origin: border-box;
            background-clip: content-box, border-box;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .project-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(52, 152, 219, 0.2);
        }

        .project-title {
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 8px;
            font-size: 1.1em;
        }

        .project-description {
            color: #5d6d7e;
            line-height: 1.6;
        }

        .tech-skills {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .tech-category {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 15px;
            padding: 20px;
            border: 2px solid transparent;
            background-image: linear-gradient(135deg, #f8f9fa, #e9ecef), linear-gradient(135deg, #3498db, #2980b9);
            background-origin: border-box;
            background-clip: content-box, border-box;
        }

        .tech-category-title {
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 12px;
        }

        .tech-list {
            color: #5d6d7e;
            line-height: 1.6;
        }

        .differentiators {
            background: linear-gradient(135deg, #2c3e50, #3498db);
            color: white;
            padding: 30px;
            border-radius: 20px;
            margin-top: 30px;
        }

        .differentiators-title {
            font-size: 1.8em;
            font-weight: 700;
            margin-bottom: 20px;
            text-align: center;
        }

        .differentiator-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .differentiator {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.3s ease;
        }

        .differentiator:hover {
            transform: scale(1.05);
        }

        .diff-icon {
            font-size: 2em;
            margin-bottom: 10px;
            display: block;
        }

        .diff-title {
            font-weight: 600;
            margin-bottom: 8px;
        }

        .diff-description {
            font-size: 0.9em;
            opacity: 0.9;
            line-height: 1.5;
        }

        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
                gap: 20px;
                padding: 20px;
            }
            
            .name {
                font-size: 2.5em;
            }
            
            .data-visualization {
                gap: 15px;
            }
            
            .differentiator-grid {
                grid-template-columns: 1fr;
            }
        }

        .floating-elements {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }

        .floating-element {
            position: absolute;
            width: 60px;
            height: 60px;
            background: rgba(52, 152, 219, 0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .floating-element:nth-child(1) { top: 10%; left: 10%; animation-delay: 0s; }
        .floating-element:nth-child(2) { top: 20%; right: 15%; animation-delay: 2s; }
        .floating-element:nth-child(3) { bottom: 30%; left: 20%; animation-delay: 4s; }
        .floating-element:nth-child(4) { bottom: 10%; right: 10%; animation-delay: 1s; }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }
    </style>
</head>
<body>
    <div class="resume-container">
        <div class="floating-elements">
            <div class="floating-element"></div>
            <div class="floating-element"></div>
            <div class="floating-element"></div>
            <div class="floating-element"></div>
        </div>
        
        <div class="header">
            <div class="header-content">
                <h1 class="name">Hi there! 👋 I'm Mansi Thorat</h1>
                <p class="title">Data Engineer | Data Analyst | Business Intelligence Professional</p>
                
                <div class="data-visualization">
                    <div class="data-point">
                        <span class="data-number">10+</span>
                        <span class="data-label">Key Projects</span>
                    </div>
                    <div class="data-point">
                        <span class="data-number">3.2M+</span>
                        <span class="data-label">Records Analyzed</span>
                    </div>
                    <div class="data-point">
                        <span class="data-number">25%</span>
                        <span class="data-label">Data Protection ↑</span>
                    </div>
                    <div class="data-point">
                        <span class="data-number">30%</span>
                        <span class="data-label">Efficiency ↑</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="main-content">
            <div class="left-column">
                <div class="section">
                    <h2 class="section-title">About Me</h2>
                    <p class="about-text">
                        I am a data-driven professional with expertise in <strong>data engineering, analytics, and business intelligence</strong>, passionate about transforming raw data into meaningful insights. With a strong foundation in <strong>Python, SQL, Power BI, Airflow, DBT, and cloud technologies</strong>, I specialize in designing scalable <strong>ETL pipelines, optimizing data workflows, and building interactive dashboards</strong> for strategic decision-making. My diverse experience spans <strong>AI-driven solutions, real-time analytics, and data visualization</strong>, making me a versatile asset in the evolving tech landscape.
                    </p>
                </div>

                <div class="section">
                    <h2 class="section-title">Education</h2>
                    <div class="education-item">
                        <div class="degree">Master of Science in Information Systems</div>
                        <div class="institution">Northeastern University, Boston</div>
                    </div>
                    <div class="education-item">
                        <div class="degree">Bachelor of Engineering in Electronics and Telecommunication</div>
                        <div class="institution">Savitribai Phule Pune University, India</div>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">Technical Expertise</h2>
                    <div class="tech-skills">
                        <div class="tech-category">
                            <div class="tech-category-title">Languages</div>
                            <div class="tech-list">Python, SQL, PySpark</div>
                        </div>
                        <div class="tech-category">
                            <div class="tech-category-title">Data Engineering</div>
                            <div class="tech-list">Apache Airflow, DBT, Snowflake, PostgreSQL, AWS, Docker</div>
                        </div>
                        <div class="tech-category">
                            <div class="tech-category-title">Analytics & Visualization</div>
                            <div class="tech-list">Power BI, Tableau, Seaborn, Matplotlib</div>
                        </div>
                        <div class="tech-category">
                            <div class="tech-category-title">AI & ML</div>
                            <div class="tech-list">GPT-4, LangChain, Pinecone, Scikit-Learn</div>
                        </div>
                        <div class="tech-category">
                            <div class="tech-category-title">Cloud & Big Data</div>
                            <div class="tech-list">AWS (S3, Redshift, Lambda, Bedrock, Glue, EC2), GCP, Azure</div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="right-column">
                <div class="section">
                    <h2 class="section-title">Key Projects & Achievements</h2>
                    
                    <div class="project-category">
                        <h3 class="category-title">
                            <span class="category-icon">🚀</span>
                            Data Engineering & Automation
                        </h3>
                        
                        <div class="project-item">
                            <div class="project-title">Automated Weather Data ETL Pipeline</div>
                            <div class="project-description">
                                Developed an <strong>Apache Airflow</strong>-powered ETL pipeline to fetch real-time weather data via API, transform it, and store it in <strong>PostgreSQL</strong>. Automated scheduling ensured seamless data updates for downstream analytics.
                            </div>
                        </div>
                        
                        <div class="project-item">
                            <div class="project-title">Intelligent Resume Screening with LLM & LangChain</div>
                            <div class="project-description">
                                Engineered an <strong>AI-driven resume screening tool</strong> using <strong>GPT-4 & Pinecone</strong>, streamlining candidate selection via <strong>vector similarity search</strong>. Designed an interactive UI in <strong>Streamlit</strong> to enhance recruiter efficiency.
                            </div>
                        </div>
                    </div>

                    <div class="project-category">
                        <h3 class="category-title">
                            <span class="category-icon">📊</span>
                            Data Analysis & Business Intelligence
                        </h3>
                        
                        <div class="project-item">
                            <div class="project-title">Salary Prediction Feature Analysis</div>
                            <div class="project-description">
                                Conducted <strong>data profiling, feature engineering, and statistical analysis</strong> on 10,000+ records to identify key salary predictors, leveraging multiple ML techniques for insights.
                            </div>
                        </div>
                        
                        <div class="project-item">
                            <div class="project-title">Urban Traffic Crash Data Profiling</div>
                            <div class="project-description">
                                Analyzed <strong>3.2M+ accident records</strong> from major US cities, identifying key risk factors and proposing <strong>data transformation strategies using Talend</strong>.
                            </div>
                        </div>
                        
                        <div class="project-item">
                            <div class="project-title">Integrated Food Safety Analytics</div>
                            <div class="project-description">
                                Designed a <strong>BI solution</strong> for food safety management, improving <strong>data redundancy (-20%) & data protection (+25%)</strong> using <strong>Navicat, Alteryx, Python, SQL Server, Power BI, and Tableau</strong>.
                            </div>
                        </div>
                        
                        <div class="project-item">
                            <div class="project-title">Service Request Analytics</div>
                            <div class="project-description">
                                Led a <strong>cross-functional data initiative</strong>, uncovering <strong>200+ data inconsistencies</strong> and driving a <strong>15% improvement in service response times</strong> via <strong>Power BI & Tableau dashboards</strong>.
                            </div>
                        </div>
                    </div>

                    <div class="project-category">
                        <h3 class="category-title">
                            <span class="category-icon">💡</span>
                            Strategic Data Solutions & AI-driven Insights
                        </h3>
                        
                        <div class="project-item">
                            <div class="project-title">Personal Finance Management System</div>
                            <div class="project-description">
                                Built a <strong>scalable data model</strong> with optimized storage, reducing redundancy by <strong>20%</strong>, and implemented <strong>automated data loading (↑30% efficiency)</strong> using triggers & stored procedures.
                            </div>
                        </div>
                        
                        <div class="project-item">
                            <div class="project-title">Recession Analysis</div>
                            <div class="project-description">
                                Applied <strong>Python-based statistical modeling</strong> to detect recession trends, generating actionable insights for economic forecasting.
                            </div>
                        </div>
                        
                        <div class="project-item">
                            <div class="project-title">Smart COVAX Distribution System</div>
                            <div class="project-description">
                                Designed an AI-driven <strong>vaccine distribution platform</strong>, optimizing supply chain logistics and increasing distribution efficiency by <strong>20%</strong>.
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="differentiators">
            <h2 class="differentiators-title">What Makes Me Different?</h2>
            <div class="differentiator-grid">
                <div class="differentiator">
                    <span class="diff-icon">💡</span>
                    <div class="diff-title">AI-Driven Mindset</div>
                    <div class="diff-description">I blend AI, automation, and data engineering to create intelligent, scalable solutions.</div>
                </div>
                <div class="differentiator">
                    <span class="diff-icon">🚀</span>
                    <div class="diff-title">Full-Stack Data Expertise</div>
                    <div class="diff-description">From ETL pipelines to BI dashboards, I handle end-to-end data workflows.</div>
                </div>
                <div class="differentiator">
                    <span class="diff-icon">📈</span>
                    <div class="diff-title">Business-Centric Approach</div>
                    <div class="diff-description">I don't just process data—I translate it into strategic insights for decision-makers.</div>
                </div>
                <div class="differentiator">
                    <span class="diff-icon">🎯</span>
                    <div class="diff-title">Impact-First Thinking</div>
                    <div class="diff-description">Every data solution I build drives efficiency, automation, and ROI for organizations.</div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
