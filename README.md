<h1 align="center">Container Security Workshop Lab</h1>

<p align="center">
  by <a href="https://topmate.io/peachycloudsecurity">Anjali &amp; Divyanshu</a> (theshukladuo) at <a href="https://www.youtube.com/@peachycloudsecurity">Peachycloud Security </a>
</p>


<p align="center">
  <img src="https://topmate.io/cdn-cgi/image/width=640,quality=90/https://static.topmate.io/4butNtHixUQEEyRVd1jbyU.png" width="280" alt="Peachy Cloud Security, by The Shukla Duo" />
</p>

<p align="center">
  <a href="https://peachycloudsecurity.com/training/live-bootcamp#all-trainings"><img alt="Trainings" src="https://img.shields.io/badge/Trainings-f0663d?style=for-the-badge&logo=googleclassroom&logoColor=white" /></a>
  <a href="https://www.youtube.com/@peachycloudsecurity"><img alt="YouTube" src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" /></a>
  <a href="https://instagram.com/peachycloudsecurity"><img alt="Instagram" src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" /></a>
  <a href="https://topmate.io/peachycloudsecurity"><img alt="Topmate" src="https://img.shields.io/badge/Topmate-E44332?style=for-the-badge" /></a>
</p>

<p align="center">
  <a href="https://www.bsidesjaipur.in/">
    <img alt="BSides Jaipur 2026" src="https://img.shields.io/badge/BSides-Jaipur%202026-7b1fa2.svg" />
  </a>
  <img alt="Null & BSides Coimbatore 2026" src="https://img.shields.io/badge/Null%20%26%20BSides-Coimbatore%202026-00897b.svg" />
</p>

<p align="center">
  Command line first. Open source tools only.<br/>
  <b><a href="https://containersecurity.peachycloudsecurity.com">https://containersecurity.peachycloudsecurity.com</a></b>

  ·

Hands-on primer on Docker and container security for security, platform, and backend engineers who are comfortable in a Linux shell and need a shared baseline before Kubernetes or deeper cloud work. Day-to-day Docker use helps but is not assumed to be deep. The text rebuilds from how images sit on disk through review, build, runtime risk, scanning, SBOM, and hardening.



### Syllabus


- **Setup** covers forking [container-security-workshop-lab](https://github.com/peachycloudsecurity/container-security-workshop-lab), opening **GitHub Codespaces** where that path is used, checking the Docker engine and Compose, and a workspace directory for lab files and build contexts. Tool install paths are handled when each lab first needs them, or in [Environment Setup](https://containersecurity.peachycloudsecurity.com/setup/index.html) for a persistent profile on local Linux.

- **Foundations** contrasts containers with VMs, walks image layers and basic `docker` commands, explains Dockerfile layout and the client or daemon path, runs **Hadolint** and **Dockle** on a deliberately weak Dockerfile sample, then brings up a small **Docker Compose** stack from public images only.

- **Image build and delivery** ties registries, tags, and digests to day-to-day push and pull, then uses two Dockerfiles for the same minimal Python HTTP service so a single-stage tag and a multi-stage slim tag can be compared with `docker images` and a quick run against each tag.

- **Runtime Security** states how namespaces and capabilities are supposed to contain a process, then moves to supervised labs on an **isolated Linux VM** you provide: host bind mounts, `--privileged`, `cap-drop` and selective `cap-add`, and reading the capability fields Docker actually applied.

- **Image audit** links package inventory to CVE databases, installs **Trivy**, scans an upstream image and a lab-built image, and sketches optional output formats and scanner scope for CI-style use.

- **Supply chain** installs **Syft** to emit SBOM output (SPDX JSON in the lab), then runs **Grype** on that file so findings can be refreshed without rebuilding the image each pass.

- **Hardening** walks base image size trade-offs, root versus non-root execution inside the image, dropping capabilities from a default set, and passing secrets at run time instead of storing them in image layers.


## Workshop website

- Workshop:  
[https://containersecurity.peachycloudsecurity.com/](https://containersecurity.peachycloudsecurity.com/)
- Source repository:  
[https://github.com/peachycloudsecurity/container-security-workshop](https://github.com/peachycloudsecurity/container-security-workshop)

## Key takeaways

- Identifying common `Dockerfile` defects and recording findings for security and engineering review.
- Comparing single-stage and multi-stage images for size and maintenance impact.
- Showing host bind mounts and capability settings against default container isolation.
- Running Trivy on an image tag and summarising the report.
- Producing an SBOM with Syft and scanning it with Grype.
- Selecting hardening checks that fit merge request templates.

## Prerequisites

- GitHub account with **Codespaces** enabled.
- Browser that loads **GitHub Codespaces** normally.
- Familiarity with the **Linux command line**.

## Start here

- **Codespaces:** [Lab: Setup GitHub Codespace](https://containersecurity.peachycloudsecurity.com/setup/lab_codespace.html)
- **Local Linux:** [Environment Setup](https://containersecurity.peachycloudsecurity.com/setup/index.html), then [Lab: Workshop workspace](https://containersecurity.peachycloudsecurity.com/setup/lab_environment.html)

> [!WARNING]
> Steps that look like attacks are only for environments you are authorised to test. Do not use them on systems you do not own or lack written permission to assess.

## About us

- Anjali is a seasoned cloud security engineer, experienced in DevSecOps and Kubernetes security (EKS/GKE) as well as AWS, Azure, and GCP security. She is the founder of Container Security Village and Kubernetes Village, communities dedicated to enhancing cloud-native security. As the project lead for OWASP EKS Goat, she focuses on AWS EKS security research and hands-on exploitation paths. Anjali is a recognized AWS Community Builder and actively shares her research through her YouTube channel, @peachycloudsecurity. Her extensive speaking history includes Blackhat USA, Black Hat Spring USA, Black Hat Europe, Nullcon, Seasides Goa, BSides Bangalore, CSA Bangalore, and C0c0n. She has also contributed to the community by volunteering at Cloud Village at DEF CON and various BSides events globally.Reach out at peachycloudsecurity[dot]com

- Divyanshu is a senior security engineer, experienced in Cloud Security, Kubernetes Security, DevSecops, Web Application Pentesting, and Threat Modelling. Reported multiple vulnerabilities to companies like Airbnb, Google, Microsoft, AWS, Apple, Amazon, Samsung, Zomato, Xiaomi, Alibaba, Opera, Protonmail, Mobikwik, etc, and received CVE-2019-8727 CVE-2019-16918, CVE-2019-12278, CVE-2019-14962 for reporting issues. Currently co-lead of OWASP EKS Goat, OWASP GKE Goat, Author of Burp-o-mation and a very-vulnerable-serverless application. Also part of AWS Community Builder for security and Defcon Cloud Village crew member 2020/2021/2022. Delivered talks at events like Blackhat USA,  Europe, Seasides, C0c0n, Nullcon, Brucon, Bsides Bangalore and Bsides Ahmedabad. Also winner of "Cybersecurity samurai 2023" at Bsides Bangalore 2023 & "Cloud Security Champion'' at CSA Bangalore 2023. Reach out at peachycloudsecurity[dot]com

## Disclaimer

- The information, commands, and demonstrations presented in this lab including any course, are intended strictly for educational purposes. Under no circumstances should they be used to compromise or attack any system outside the boundaries of this educational session unless explicit permission has been granted.

    - <b>This course is provided by the instructors independently and is not endorsed by their employers or any other corporate entity. The content does not necessarily reflect the views or policies of any company or professional organization associated with the instructors.</b>

- **Usage of Training Material**: The training material is provided without warranties or guarantees. Participants are responsible for applying the techniques or methods discussed during the training. The trainers and their respective employers or affiliated companies are not liable for any misuse or misapplication of the information provided.

- **Liability**: The trainers, their employers, and any affiliated companies are not responsible for any direct, indirect, incidental, or consequential damages arising from the use of the information provided in this course. No responsibility is assumed for any injury or damage to persons, property, or systems as a result of using or operating any methods, products, instructions, or ideas discussed during the training.

- **Intellectual Property**: This course and all accompanying materials, including slides, worksheets, and documentation, are the intellectual property of the trainers. They are shared under the GPL-3.0 license, which requires that appropriate credit be given to the trainers whenever the materials are used, modified, or redistributed.

- **References**: Some of the labs referenced in this workshop are based on open-source material. Additionally, modifications and fixes have been applied using AI tools such as Amazon Q, ChatGPT, and Gemini.

- **Educational Purpose**: This lab is for educational purposes only. Do not attack or test any website or network without proper authorization. The trainers are not liable or responsible for any misuse.
- **Usage Rights**: Individuals are permitted to use this course for instructional purposes, provided that no fees are charged to the students.



### Contact: **[Peachycloud Security](https://peachycloudsecurity.com)**

## 💝 Support the Project

Your support helps us maintain and improve this workshop, create more educational content, and continue building open-source security resources for the community.

**Ways to Support:**
- **Subscribe on YouTube** - [youtube.com/@peachycloudsecurity](https://www.youtube.com/@peachycloudsecurity)
- **Sponsor via GitHub** - [GitHub Sponsors](https://github.com/sponsors/peachycloudsecurity)
- **Explore Learning Resources** - Access additional tutorials, walkthroughs, and hands-on labs at [peachycloudsecurity.com](https://peachycloudsecurity.com)
- **Connect & Learn** - Connect with us via [Topmate](https://topmate.io/peachycloudsecurity)

> **Looking for personalized guidance?** Get one-on-one mentorship, interview prep, or custom training sessions through our [Topmate](https://topmate.io/peachycloudsecurity) platform.

