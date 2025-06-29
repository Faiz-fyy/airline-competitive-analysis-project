# Malaysia Airlines Competitive Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue) ![Machine Learning](https://img.shields.io/badge/ML-Classification-orange) ![NLP](https://img.shields.io/badge/NLP-Sentiment_Analysis-red) ![Industry](https://img.shields.io/badge/Industry-Aviation-green)

**Statistical analysis and natural language processing for airline competitive analysis using hypothesis testing and sentiment analysis**

*NDT Engineering to Data Science portfolio - Statistical testing and NLP techniques for competitive benchmarking*

## Project Overview

This project analyzes competitive positioning for Malaysia Airlines against Qatar Airways, Singapore Airlines, and Emirates using statistical testing and natural language processing techniques on 8,137 airline reviews from 2013-2025. The analysis quantifies service gaps across 6 dimensions and validates findings through sentiment analysis, completing the portfolio progression from engineering analytics to comprehensive statistical and NLP applications.

**Achievement: 97.2% data quality with -0.89 point competitive gap identification using ANOVA testing and sentiment validation**

## Business Problem

Malaysia Airlines faces competitive pressure from premium global carriers without systematic performance benchmarking. Traditional competitive analysis relies on limited operational metrics without customer sentiment integration. Understanding service gaps and customer language patterns is essential for strategic positioning and resource allocation in the competitive aviation market.

### Dataset Characteristics
- 8,137 reviews across 4 premium carriers over 12 years (2013-2025)
- Distribution: Malaysia Airlines (1,471), Qatar Airways (2,600), Singapore Airlines (1,648), Emirates (2,418)
- Metrics: Overall rating, seating comfort, staff service, food quality, entertainment, value for money
- Coverage: Travel class, routes, aircraft types, temporal data, review text
- Quality: 97.2% usable data after preprocessing and standardization

### Data Governance Framework
- Missing data recovery from 26% to 2.3% final loss
- Aircraft standardization (671 variants → 13 categories)
- Route categorization with regional mapping
- Temporal analysis across pre/post-COVID periods

## Technical Approach

### Data Processing Pipeline
**Stage 1: Data Wrangling & Understanding**
- Quality assessment with systematic missing data recovery
- Aircraft and route standardization protocols
- Temporal categorization (Historical, Pre-COVID, Post-COVID)
- Quality scoring framework achieving 97.2% data reliability

**Stage 2: Statistical Analysis Framework**
- One-way ANOVA testing across service dimensions
- Cohen's d effect size calculations for practical significance
- Multiple regression modeling for service impact assessment
- A380 retirement causal analysis with t-testing

**Stage 3: NLP Analysis Implementation**
- VADER sentiment analysis on review text
- TF-IDF analysis for airline-specific language patterns
- Bigram network analysis for relationship mapping
- Aspect-based sentiment extraction for service dimensions

### Model Performance Comparison

| Analysis Type | Key Finding | Statistical Validation |
|---------------|-------------|----------------------|
| Competitive Gap | -0.89 points vs top 3 competitors | All services p<0.05 (ANOVA) |
| Service Priority | Value for Money β=1.470 highest impact | R²=0.832 regression model |
| Sentiment Analysis | 0.215 vs 0.369 industry average | Point-biserial r=-0.154 |
| Effect Sizes | Medium effects vs Qatar (d≥0.5) | Cohen's d interpretation |

## Key Technical Components

### Statistical Testing Framework
**ANOVA Implementation:**
```python
def competitive_anova_analysis(df, airlines):
    for service in service_dimensions:
        groups = [df[df['airline']==airline][service] for airline in airlines]
        f_stat, p_value = f_oneway(*groups)
        eta_squared = calculate_effect_size(groups)
```

**Effect Size Analysis:**
- Entertainment gap: -0.96 (Large effect size)
- Food Quality gap: -0.82 (Medium effect size)  
- Staff Service gap: -0.77 (Medium effect size)
- Seating Comfort gap: -0.65 (Medium effect size)

### NLP Pipeline Implementation
**Text Processing:**
```python
def advanced_text_preprocessing(df):
    sia = SentimentIntensityAnalyzer()
    df['sentiment_score'] = df['review'].apply(lambda x: sia.polarity_scores(str(x))['compound'])
    df['bigrams'] = df['review_clean'].apply(extract_bigrams)
```

**TF-IDF Analysis:**
- Airline-specific language pattern identification
- Distinctive term extraction for competitive positioning
- Sentiment-weighted importance scoring
- Cross-airline comparative analysis

### Correlation Analysis Results
**Statistical Relationships:**
- Satisfaction vs Turnover: r = -0.39 (highly significant)
- Monthly Hours vs Turnover: Point-biserial correlation validation
- Department effects: Cramér's V association testing
- Travel class performance: Business 30.9% vs Economy 67.9% distribution

## Database Architecture

### Data Quality Framework
```python
def create_data_quality_framework(df):
    # Core data completeness (30%)
    # Service ratings completeness (40%) 
    # Metadata completeness (20%)
    # Text quality (10%)
    df['data_quality_score'] = calculate_weighted_quality()
```

**Quality Distribution:**
- High Quality: 97.2% of final dataset
- Missing data recovery: 26% → 2.3% final loss
- Aircraft standardization: 671 variants → 13 categories
- Route categorization: Regional and hub analysis integration

## Business Intelligence Insights

### Competitive Position Analysis
**Market Ranking:**
- Malaysia Airlines: #3 of 4 premium carriers
- Performance gap: -0.89 points vs competitors
- Statistical significance: All service dimensions p<0.05

**Service Impact Hierarchy:**
1. Value for Money (β=1.470) - highest satisfaction impact
2. Staff Service (β=0.715) - customer interaction focus
3. Seating Comfort (β=0.460) - physical experience factor

### NLP Insights
**Sentiment Performance:**
- Malaysia Airlines: 0.215 sentiment score
- Industry average: 0.369 sentiment score
- Gap: -0.154 points requiring attention

**Language Pattern Analysis:**
- Positive mentions: 'cabin crew' (405 instances)
- Pain points: 'customer service' (115 negative mentions)
- Cultural strength: 'satay' distinctive positive term

### Travel Class Analysis
**Performance Distribution:**
- Business Class: 30.9% passengers, 6.41/10 rating, 65.1% recommendation
- Economy Class: 67.9% passengers, 5.33/10 rating, 52.1% recommendation
- Strategic insight: Business class differentiation vs volume optimization

## Visualizations

**Statistical Analysis Charts:**
- Competitive radar charts for service performance comparison
- Gap analysis with directional performance indicators
- Confusion matrices and performance distribution analysis
- Service impact regression coefficient visualization

**NLP Analysis Outputs:**
- Bigram network graphs with sentiment coloring
- TF-IDF importance charts with competitive distinctiveness
- Multi-quadrant word clouds (positive/negative/competitor patterns)
- Aspect-based sentiment comparative analysis

## Technologies & Architecture

**Statistical Framework:**
- Testing: scipy, statsmodels for ANOVA and regression
- Effect sizes: Cohen's d calculations and interpretation
- Validation: Multiple comparison corrections and assumption testing
- Reproducibility: Fixed random seeds and consistent preprocessing

**NLP Implementation:**
- Sentiment: NLTK VADER for aviation domain analysis
- Text Mining: sklearn TfidfVectorizer and CountVectorizer
- Network Analysis: networkx for bigram relationship mapping
- Visualization: matplotlib, seaborn for statistical charts

**Data Engineering:**
- Processing: pandas, numpy for data manipulation
- Quality: Systematic missing data recovery and standardization
- Validation: Cross-method convergence between statistical and sentiment findings
- Pipeline: Reproducible analysis with complete documentation

## Results & Business Impact

### Statistical Validation
**Hypothesis Testing:**
- All service dimensions show significant competitive differences (p<0.05)
- Effect sizes confirm practical significance beyond statistical significance
- Regression model explains 83.2% of satisfaction variance
- Cross-validation between quantitative and qualitative findings

### Operational Recommendations
**Immediate Actions (0-6 months):**
1. Entertainment system upgrade (largest gap: -0.96 points)
2. Food quality improvement program (-0.82 points gap)
3. Staff service training enhancement (-0.77 points gap)

**Strategic Implementation (6-18 months):**
1. Value for money positioning (highest satisfaction impact)
2. Business class differentiation strategy
3. Seasonal service optimization based on route analysis

### Business Value
**Competitive Analysis:**
- Quantified performance gaps enabling targeted resource allocation
- Statistical validation providing confidence for strategic decisions
- Customer sentiment analysis revealing operational pain points
- Cross-domain validation between metrics and customer language

**Data-Driven Planning:**
- Priority matrix based on statistical significance and effect sizes
- Resource allocation guidance through regression impact analysis
- Sentiment monitoring framework for ongoing competitive tracking
- Evidence-based positioning against specific competitors

## Project Structure

```
├── notebooks/
│   ├── stage1_data_wrangling.py          # Data quality and standardization
│   ├── stage2_statistical_analysis.py    # ANOVA, effect sizes, regression
│   └── stage3_nlp_analysis.py            # Sentiment analysis and text mining
├── visualizations/                       # Statistical and NLP charts
├── docs/                                # Methodology and validation documentation
└── README.md                            # Project overview
```

## Portfolio Context & Technical Improvement

### Skill Development Progression
**Statistical Improvement:**
1. **Aircraft Hub Inspection:** Basic correlation analysis
2. **Aircraft Flap Analytics:** Database design + risk frameworks
3. **Aircraft X-ray CNN:** Computer vision + confidence scoring
4. **HR Employee Turnover:** Classification modeling + SHAP
5. **Aircraft Rudder Thermal:** Few-shot learning + physics integration
6. **This Project:** Statistical testing + NLP + competitive analysis

## Limitations & Considerations

### Analytical Constraints
**Data Limitations:**
- English-language review bias limiting global customer representation
- Platform-specific user demographics affecting sample composition
- COVID-19 disruption effects on baseline performance comparisons
- Limited operational cost integration for complete competitive picture

**Methodological Considerations:**
- Cross-sectional analysis limitation for causal inference
- Sentiment analysis tool limitations for aviation domain specificity
- TF-IDF parameter sensitivity requiring domain expertise validation
- Effect size interpretation subjectivity requiring business context

### Future Enhancement Opportunities
**Technical Development:**
- Real-time competitive monitoring with API integration
- Multi-language sentiment analysis for global market coverage
- Operational cost integration for comprehensive competitive modeling
- Time series analysis for trend prediction and forecasting

**Business Applications:**
- Automated competitive intelligence dashboards
- Customer sentiment tracking with alert systems
- Strategic planning integration with route and fleet optimization
- Regulatory compliance monitoring through customer feedback analysis

## Validation & Quality Assurance

### Statistical Thoroughness
**Testing Standards:**
- Multiple testing correction consideration for family-wise error control
- Effect size practical significance beyond statistical significance
- Regression assumption validation through residual analysis
- Cross-validation methodology ensuring result reliability

**NLP Validation:**
- Sentiment analysis tool validation against domain expertise
- Bigram network filtering for meaningful relationship identification
- TF-IDF parameter optimization through systematic testing
- Aspect keyword validation through aviation industry knowledge

### Reproducibility Framework
**Quality Standards:**
- Complete random seed control for consistent results
- Systematic data preprocessing with validation checkpoints
- Cross-method validation between statistical and sentiment findings
- Documentation standards enabling independent verification

## Conclusion

This project demonstrates the application of statistical testing and natural language processing to competitive analysis challenges, achieving  performance benchmarking through quantitative analysis validated by qualitative sentiment analysis. The systematic three-stage approach provides reliable competitive insights while maintaining analytical rigor and business relevance.

**Key Methodological Achievements:**
- Statistical testing with effect size interpretation for practical significance
- NLP techniques with network analysis for customer language pattern recognition
- Cross-method validation ensuring finding reliability and confidence
- Business intelligence translation with clear improvement prioritization
- Reproducible analytical pipeline enabling ongoing competitive monitoring

The work establishes a framework for data-driven competitive analysis in the aviation industry, bridging statistical thoroughness with customer sentiment understanding to provide actionable insights for strategic decision-making.

---

**About:** This project completes the NDT Engineering to Data Science portfolio by demonstrating statistical analysis and NLP capabilities applied to business competitive analysis, showcasing cross-domain expertise and analytical improvement suitable for data science roles in competitive intelligence and strategic planning.
