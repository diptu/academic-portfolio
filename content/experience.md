---
title: 'Experience'
date: 2023-10-24
type: landing

design:
  spacing: '5rem'

# Professional Experience uses the `focus-areas` block (alias: `research-areas`) in its
# `timeline` layout — the same native component used for "Research Direction Path" on the
# Research Interests page: left-aligned cards, an icon badge per node, and a continuous
# vertical line with nodal circles connecting them in chronological order.
#
# Field-mapping note: this block's item schema is `name` / `description` / `icon` only —
# there is no `title`, `company`, `date_start`, or `date_end` key for it to read. Title,
# company, and date range are folded into `name` (its card heading), matching the block's
# own documented convention for timeline items (e.g. "Foundation (2015-2018)").
#
# Icon-pack note: this kit only bundles Hero icons, Devicon, Brands, and Academicons — there
# is no Font Awesome pack, so the requested `server` / `chart-line` / `database` / `brain`
# identifiers were mapped to their nearest real Hero-icon equivalents below (`server` matches
# exactly; the other three are substitutions — see icons used).
#
# Scope note: this page is industrial/professional history only. The academic-prep narrative
# (current research activities, GRE/IELTS, etc.) lives on content/education.md instead.

sections:
  - block: focus-areas
    id: professional-experience
    content:
      title: 'Professional Experience'
      subtitle: ''
      items:
        - name: 'Freelance MLOps Engineer — Carboniq (Remote) · May 2025 – Aug 2025'
          icon: hero/server
          description: |-
            Architected scalable MLOps pipelines using MLflow and Airflow for automated model training and deployment. Built ETL/ELT workflows and multi-tenant REST APIs on PostgreSQL, containerized with Docker. Implemented CI/CD systems to support continuous integration and deployment of ML services.
        - name: 'Product Analyst — Power Ledger (Perth) · Oct 2022 – Feb 2024'
          icon: hero/presentation-chart-line
          description: |-
            Analyzed product usage and energy trading platform data to inform feature and reporting decisions. Automated recurring reporting workflows, reducing manual operations.
        - name: 'Senior Technical Analyst — InsideMaps (Dhaka) · Aug 2021 – Jun 2023'
          icon: hero/circle-stack
          description: |-
            Optimized data pipelines, automated core operations, and established modular workflow reporting architectures.
        - name: 'Junior Data Scientist — Me-Solshare (Dhaka) · Nov 2019 – Aug 2021'
          icon: hero/cpu-chip
          description: |-
            Developed machine learning and time-series forecasting models, designed automated preprocessing pipelines, and delivered dashboard analytics for load planning.
    design:
      layout: timeline

  - block: markdown
    id: technical-skills
    content:
      title: 'Technical Skills & Certifications'
      subtitle: ''
      text: |-
        **Programming:** Python, JavaScript, Rust, C++

        **Machine Learning:** PyTorch, TensorFlow, Scikit-Learn, OpenCV

        **Data Engineering:** Airflow, dbt, Spark, Kafka

        **Backend & DB:** FastAPI, Django, Node.js, Next.js, PostgreSQL, MongoDB, Redis

        **Cloud & DevOps:** Azure, AWS, Docker, Kubernetes, GitHub Actions

        **Certifications:** Deep Learning Specialization (DeepLearning.AI), Machine Learning Specialization (DeepLearning.AI / Stanford)
    design:
      columns: '1'
---
