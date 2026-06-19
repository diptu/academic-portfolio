---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2022-10-24
type: landing

sections:
  # Profile summary: name, identity tagline (profile.role), and research statement
  # (profile.bio). Deliberately using `resume-biography` (not `-3`) here — it does
  # not auto-render education/interests, which now have their own dedicated pages
  # (Education, Research Interests) per the IA below.
  - block: resume-biography
    content:
      username: admin
      text: ''
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: md
      avatar:
        size: medium
        shape: circle

  - block: markdown
    id: resume-cta
    content:
      title: 'Curriculum Vitae'
      subtitle: ''
      text: |-
        Academic recruiters, research labs, and engineering managers can view my full credentials, publications, and professional history in the downloadable resume below.

        <a href="/uploads/resume.pdf" target="_blank" rel="noopener" download class="inline-flex items-center px-6 py-3 bg-primary-600 hover:bg-primary-500 text-white font-medium rounded-xl shadow-lg shadow-primary-500/25 hover:shadow-xl hover:shadow-primary-500/30 transition-all">Download CV / Resume (PDF)</a>
    design:
      columns: '1'

  - block: markdown
    id: contact
    content:
      title: 'Get in Touch'
      subtitle: ''
      text: |-
        Fellow researchers, academic recruiters, and engineering collaborators are welcome to reach out directly.

        <div class="flex flex-wrap gap-4 mt-2">
        <a href="https://www.linkedin.com/in/diptu/" target="_blank" rel="noopener noreferrer" class="inline-flex items-center px-6 py-3 bg-secondary-600 hover:bg-secondary-500 text-white font-medium rounded-xl shadow-lg shadow-secondary-500/25 hover:shadow-xl hover:shadow-secondary-500/30 transition-all">Message on LinkedIn</a>
        <a href="mailto:diptunazmulalam@gmail.com" target="_blank" rel="noopener noreferrer" class="inline-flex items-center px-6 py-3 bg-primary-600 hover:bg-primary-500 text-white font-medium rounded-xl shadow-lg shadow-primary-500/25 hover:shadow-xl hover:shadow-primary-500/30 transition-all">Send an Email</a>
        </div>
    design:
      columns: '1'
---
