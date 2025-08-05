---
layout: page
title: performance
permalink: /performance/
description: Sales metrics and key achievements across 5+ years of quota overattainment.
nav: true
nav_order: 2
---

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.performance-nav {
    display: flex;
    border-bottom: 1px solid var(--global-divider-color);
    margin-bottom: 2rem;
}

.nav-tab {
    padding: 0.75rem 1.5rem;
    background: none;
    border: none;
    color: var(--global-text-color-light);
    cursor: pointer;
    transition: all 0.3s ease;
    border-bottom: 2px solid transparent;
    font-size: 0.9rem;
}

.nav-tab.active {
    color: var(--global-theme-color);
    border-bottom-color: var(--global-theme-color);
}

.nav-tab:hover {
    color: var(--global-theme-color);
}

.tab-content {
    display: none;
}

.tab-content.active {
    display: block;
}

.section {
    margin-bottom: 2.5rem;
}

.section-title {
    font-size: 1.25rem;
    font-weight: 400;
    color: var(--global-text-color);
    margin-bottom: 1.5rem;
    border-bottom: 1px solid var(--global-divider-color);
    padding-bottom: 0.5rem;
}

.quota-performance {
    background: var(--global-bg-color);
    border: 1px solid var(--global-divider-color);
    padding: 1.5rem;
}

.performance-item {
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
    font-size: 0.9rem;
}

.performance-item:last-child {
    margin-bottom: 0;
}

.year {
    min-width: 50px;
    font-weight: 500;
    color: var(--global-text-color);
}

.progress-track {
    flex: 1;
    height: 8px;
    background: var(--global-divider-color);
    margin: 0 1rem;
    border-radius: 4px;
    overflow: visible;
    position: relative;
}

.progress-fill {
    height: 100%;
    border-radius: 4px;
    transition: width 2s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    z-index: 1;
}

.progress-fill.over-quota {
    background: linear-gradient(90deg, #10b981, var(--global-theme-color));
    position: relative;
}

.progress-fill.over-quota::after {
    content: '';
    position: absolute;
    right: -2px;
    top: -2px;
    width: calc(var(--overflow) * 1%);
    height: 12px;
    background: linear-gradient(90deg, var(--global-theme-color), #d946ef);
    border-radius: 4px;
}

.progress-fill.under-quota {
    background: linear-gradient(90deg, #f59e0b, #f97316);
}

.percentage {
    min-width: 160px;
    text-align: right;
    font-weight: 600;
    color: var(--global-text-color);
    font-size: 0.85rem;
}

.company-section {
    border: 1px solid var(--global-divider-color);
    background: var(--global-bg-color);
    padding: 2rem;
    margin-bottom: 2rem;
    border-radius: 4px;
}

.company-header {
    display: flex;
    align-items: center;
    margin-bottom: 1.5rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid var(--global-divider-color);
}

.company-logo {
    width: 50px;
    height: 50px;
    background: var(--global-theme-color);
    border-radius: 4px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: 700;
    margin-right: 1rem;
    font-size: 1.5rem;
}

.company-info h3 {
    font-size: 1.1rem;
    font-weight: 500;
    color: var(--global-text-color);
    margin-bottom: 0.25rem;
}

.company-info .tenure {
    color: var(--global-text-color-light);
    font-size: 0.875rem;
}

.company-metrics {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 1rem;
    margin-bottom: 1.5rem;
}

.company-metric {
    text-align: center;
    padding: 1rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 4px;
    transition: all 0.3s ease;
}

.company-metric:hover {
    border-color: var(--global-theme-color);
    transform: translateY(-2px);
}

.company-metric-value {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--global-theme-color);
    margin-bottom: 0.25rem;
}

.company-metric-label {
    color: var(--global-text-color-light);
    font-size: 0.8rem;
}

.achievements-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
}

.achievement {
    padding: 1.25rem;
    border: 1px solid var(--global-divider-color);
    background: var(--global-bg-color);
    transition: all 0.3s ease;
    border-radius: 4px;
}

.achievement:hover {
    border-color: var(--global-theme-color);
    box-shadow: 0 4px 12px rgba(181, 9, 172, 0.15);
    transform: translateY(-4px);
}

.achievement-title {
    font-weight: 500;
    color: var(--global-text-color);
    margin-bottom: 0.5rem;
    font-size: 0.95rem;
}

.achievement-desc {
    color: var(--global-text-color-light);
    font-size: 0.875rem;
    line-height: 1.5;
}

.charts-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
}

.chart-container {
    background: var(--global-bg-color);
    border: 1px solid var(--global-divider-color);
    border-radius: 8px;
    padding: 1.5rem;
    transition: all 0.3s ease;
}

.chart-container:hover {
    border-color: var(--global-theme-color);
    box-shadow: 0 4px 12px rgba(181, 9, 172, 0.15);
    transform: translateY(-2px);
}

.chart-container h4 {
    font-size: 1rem;
    font-weight: 500;
    color: var(--global-text-color);
    margin-bottom: 1rem;
    text-align: center;
}

.chart {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
}

.chart-bar {
    height: 40px;
    border-radius: 6px;
    display: flex;
    align-items: center;
    padding: 0 1rem;
    position: relative;
    transition: all 0.3s ease;
    overflow: hidden;
}

.chart-bar:hover {
    transform: scale(1.02);
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}

.chart-label {
    color: white;
    font-weight: 600;
    font-size: 0.85rem;
    text-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);
    z-index: 2;
    position: relative;
}

@media (max-width: 768px) {
    .achievements-grid {
        grid-template-columns: 1fr;
    }
    
    .charts-grid {
        grid-template-columns: 1fr;
    }
    
    .performance-nav {
        overflow-x: auto;
        white-space: nowrap;
    }
    
    .nav-tab {
        flex-shrink: 0;
    }
    
    /* Mobile progress bar fixes */
    .performance-item {
        flex-direction: column;
        align-items: flex-start;
        gap: 0.75rem;
        margin-bottom: 2rem;
        padding: 1rem;
        background: var(--global-card-bg-color);
        border: 1px solid var(--global-divider-color);
        border-radius: 8px;
        transition: all 0.3s ease;
    }
    
    .performance-item:hover {
        border-color: var(--global-theme-color);
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        transform: translateY(-1px);
    }
    
    .year {
        min-width: auto;
        font-size: 1.1rem;
        font-weight: 600;
        color: var(--global-theme-color);
        margin-bottom: 0.25rem;
    }
    
    .progress-track {
        width: 100%;
        margin: 0;
        height: 20px;
        border-radius: 10px;
        background: var(--global-divider-color);
        position: relative;
        overflow: visible;
    }
    
    .progress-fill {
        border-radius: 10px;
        height: 20px;
    }
    
    .progress-fill.over-quota::after {
        height: 24px;
        top: -2px;
        border-radius: 12px;
    }
    
    .percentage {
        min-width: auto;
        text-align: left;
        font-size: 1rem;
        width: 100%;
        font-weight: 500;
        color: var(--global-text-color);
        line-height: 1.4;
    }
    
    .company-metrics {
        grid-template-columns: repeat(2, 1fr);
        gap: 0.75rem;
    }
    
    .company-metric {
        padding: 0.75rem;
    }
    
    .company-metric-value {
        font-size: 1.25rem;
    }
    
    .company-metric-label {
        font-size: 0.75rem;
    }
    
    .company-section {
        padding: 1.5rem;
        margin-bottom: 1.5rem;
    }
    
    .company-header {
        flex-direction: column;
        text-align: center;
        gap: 1rem;
    }
    
    .company-logo {
        margin-right: 0;
        margin-bottom: 0.5rem;
    }
}

@media (max-width: 480px) {
    .performance-item {
        margin-bottom: 2rem;
        padding: 1.25rem;
    }
    
    .progress-track {
        height: 24px;
        border-radius: 12px;
    }
    
    .progress-fill {
        border-radius: 12px;
        height: 24px;
    }
    
    .progress-fill.over-quota::after {
        height: 28px;
        top: -2px;
        border-radius: 14px;
    }
    
    .percentage {
        font-size: 0.95rem;
        line-height: 1.5;
        margin-top: 0.5rem;
    }
    
    .year {
        font-size: 1.2rem;
    }
    
    .company-metrics {
        grid-template-columns: 1fr;
        gap: 0.5rem;
    }
    
    .company-metric {
        padding: 1rem;
    }
    
    .company-metric-value {
        font-size: 1.5rem;
    }
    
    .nav-tab {
        padding: 0.5rem 1rem;
        font-size: 0.8rem;
    }
    
    .section-title {
        font-size: 1.1rem;
    }
    
    .achievement {
        padding: 1rem;
    }
    
    .achievement-title {
        font-size: 0.9rem;
    }
    
    .achievement-desc {
        font-size: 0.8rem;
    }
}
</style>

<div class="performance-nav">
    <button class="nav-tab active" onclick="showTab('summary')">executive summary</button>
    <button class="nav-tab" onclick="showTab('tipalti')">tipalti performance</button>
    <button class="nav-tab" onclick="showTab('promotus')">promotus track record</button>
</div>

<!-- Executive Summary Tab -->
<div id="summary" class="tab-content active">
    <div class="company-section">
        <div class="company-header">
            <div class="company-logo">★</div>
            <div class="company-info">
                <h3>Career Performance Overview</h3>
                <p class="tenure">2019 - Present | Enterprise SaaS Sales Excellence</p>
            </div>
        </div>
        
        <div class="company-metrics">
            <div class="company-metric">
                <div class="company-metric-value">$2.35M</div>
                <div class="company-metric-label">lifetime ARR</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">127%</div>
                <div class="company-metric-label">avg quota attainment</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">$60K</div>
                <div class="company-metric-label">avg deal size</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">6+</div>
                <div class="company-metric-label">years of excellence</div>
            </div>
        </div>
        
        <div class="section">
            <h2 class="section-title">5-year quota performance</h2>
            <div class="quota-performance">

                <div class="performance-item">
                    <span class="year">2023</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 60;"></div>
                    </div>
                    <span class="percentage">160% // Sept // $720K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2022</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 10;"></div>
                    </div>
                    <span class="percentage">110% // Nov // $495K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2021</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 35;"></div>
                    </div>
                    <span class="percentage">135% // Oct // $608K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2020</span>
                    <div class="progress-track">
                        <div class="progress-fill under-quota" style="width: 90%;"></div>
                    </div>
                    <span class="percentage">90% // Ramping // $406K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2019</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 100;"></div>
                    </div>
                    <span class="percentage">200% // Aug // First Year</span>
                </div>
            </div>
        </div>
        
        <div class="achievements-grid">
            <div class="achievement">
                <div class="achievement-title">Consistent Overperformance</div>
                <div class="achievement-desc">Achieved 127% average quota attainment over 6 years, with 5 out of 6 years exceeding target. Generated $2.35M+ in total ARR across finance automation and AI/ML solutions.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Mid-Market Deal Excellence</div>
                <div class="achievement-desc">Specialized in complex, multi-stakeholder deals averaging $60K. Successfully navigated 2-6 month evaluation cycles with growing mid-market organizations.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Strategic Growth Driver</div>
                <div class="achievement-desc">Self-sourced 60-70% of pipeline through disciplined multi-channel outreach. Built strategic alliances generating 25% of pipeline while maintaining 90% forecast accuracy.</div>
            </div>
        </div>
    </div>
</div>

<!-- Tipalti Performance Tab -->
<div id="tipalti" class="tab-content">
    <div class="company-section">
        <div class="company-header">
            <div class="company-logo">T</div>
            <div class="company-info">
                <h3>Tipalti - Commercial Account Executive</h3>
                <p class="tenure">April 2024 - Present | Finance Automation Platform</p>
            </div>
        </div>
        
        <div class="company-metrics">
            <div class="company-metric">
                <div class="company-metric-value">$150K</div>
                <div class="company-metric-label">ARR closed</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">4+</div>
                <div class="company-metric-label">qualified opps/quarter</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">60-70%</div>
                <div class="company-metric-label">self-sourced pipeline</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">90%</div>
                <div class="company-metric-label">forecast accuracy</div>
            </div>
        </div>
        
        <div class="achievements-grid">
            <div class="achievement">
                <div class="achievement-title">Competitive Market Success</div>
                <div class="achievement-desc">$150K ARR closed during tenure, navigating a competitive vendor landscape with Bill.com, Ramp, and other established players in the finance automation space.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Pipeline Generation Excellence</div>
                <div class="achievement-desc">Consistently delivered 4+ qualified opportunities per quarter, meeting pipeline goals for a mid-market territory through disciplined multi-channel outreach.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Self-Sourcing Mastery</div>
                <div class="achievement-desc">Self-sourced 60–70% of pipeline through disciplined multi-channel outreach, off-cycle calls, and partner-led introductions.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Complex Deal Management</div>
                <div class="achievement-desc">Managed complex sales cycles spanning 2–6 months with 4–7 key stakeholders per deal, ensuring thorough evaluation and stakeholder alignment.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Strategic Alliance Impact</div>
                <div class="achievement-desc">Contributed to 25% of pipeline via alliance partnerships with NetSuite consulting firms, leveraging partner relationships for mutual success.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Pipeline Coverage Excellence</div>
                <div class="achievement-desc">Maintained 2.5x pipeline coverage consistently to support forecast accuracy and quota attainment, ensuring reliable revenue projections.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Forecast Accuracy</div>
                <div class="achievement-desc">Achieved and maintained 90% forecast accuracy, ensuring reliable revenue projections and planning for the organization.</div>
            </div>
        </div>
    </div>
</div>

<!-- Promotus Track Record Tab -->
<div id="promotus" class="tab-content">
    <div class="company-section">
        <div class="company-header">
            <div class="company-logo">P</div>
            <div class="company-info">
                <h3>Promotus.ai - Account Executive</h3>
                <p class="tenure">February 2019 - February 2024 | AI/ML Marketing Solutions</p>
            </div>
        </div>
        
        <div class="company-metrics">
            <div class="company-metric">
                <div class="company-metric-value">$2.2M</div>
                <div class="company-metric-label">total ARR (5 years)</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">139%</div>
                <div class="company-metric-label">avg quota attainment</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">30%</div>
                <div class="company-metric-label">demo-to-close rate</div>
            </div>
            <div class="company-metric">
                <div class="company-metric-value">90%</div>
                <div class="company-metric-label">forecast accuracy</div>
            </div>
        </div>
        
        <div class="section">
            <h2 class="section-title">5-year quota performance</h2>
            <div class="quota-performance">
                <div class="performance-item">
                    <span class="year">2023</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 60;"></div>
                    </div>
                    <span class="percentage">160% // Sept // $720K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2022</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 10;"></div>
                    </div>
                    <span class="percentage">110% // Nov // $495K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2021</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 35;"></div>
                    </div>
                    <span class="percentage">135% // Oct // $608K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2020</span>
                    <div class="progress-track">
                        <div class="progress-fill under-quota" style="width: 90%;"></div>
                    </div>
                    <span class="percentage">90% // Ramping // $406K</span>
                </div>
                <div class="performance-item">
                    <span class="year">2019</span>
                    <div class="progress-track">
                        <div class="progress-fill over-quota" style="width: 100%; --overflow: 100;"></div>
                    </div>
                    <span class="percentage">200% // Aug // 143 Opps</span>
                </div>
            </div>
        </div>
        
        <div class="achievements-grid">
            <div class="achievement">
                <div class="achievement-title">Mid-Market Deal Excellence</div>
                <div class="achievement-desc">Orchestrated complex AI/ML implementations for growing mid-market accounts. Partnered with Sales Engineers on 350+ technical demonstrations, achieving ≈30% demo-to-close conversion rate.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Sales Operations Excellence</div>
                <div class="achievement-desc">Championed Outreach.io adoption, building targeted sequences that increased response rates by 20%. Maintained 2.5x pipeline coverage consistently with ≈90% forecast accuracy.</div>
            </div>
            <div class="achievement">
                <div class="achievement-title">Revenue Team Leadership</div>
                <div class="achievement-desc">Built and led 5-person pod (2 SDRs, 1 CSM, 2 Marketing). Implemented SCRAPPY qualification frameworks, improving team win rate from 18% to 23%.</div>
            </div>
        </div>
    </div>
</div>

<script>
function showTab(tabName) {
    // Hide all tab contents
    const tabContents = document.querySelectorAll('.tab-content');
    tabContents.forEach(content => {
        content.classList.remove('active');
    });
    
    // Remove active class from all nav tabs
    const navTabs = document.querySelectorAll('.nav-tab');
    navTabs.forEach(tab => {
        tab.classList.remove('active');
    });
    
    // Show selected tab content
    document.getElementById(tabName).classList.add('active');
    
    // Add active class to clicked nav tab
    event.target.classList.add('active');
}
</script>