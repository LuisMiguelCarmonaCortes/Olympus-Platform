# Olympus — Open-Source Fault-Tolerant Modular Hardware Platform

[![License: OHL-S v2](https://img.shields.io/badge/License-CERN_OHL_S_v2-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active_Development-orange.svg)]()
[![Form Factor](https://img.shields.io/badge/Form_Factor-PC%2F104_(90x96mm)-informational)]()

## Introduction
Olympus is an open-source hardware and software platform designed for study, experimentation, and research in three key areas of advanced embedded systems: **critical systems**, **edge artificial intelligence**, and **fault detection, prediction, and mitigation**.

The project was created with the goal of developing a modular platform that allows the study of how to build systems capable of monitoring their own operation, identifying anomalous behaviors, and reacting to potential faults by combining traditional safety mechanisms with artificial intelligence techniques.

The platform integrates various specialized boards, including a RISC-V-based processing system, a power board, and an FPGA dedicated to supervision functions. This architecture allows experimentation with different processing levels, monitoring mechanisms, workload isolation, and fault recovery strategies.

One of Olympus's main objectives is to research how to train and deploy compact AI models capable of running with limited computational and energy resources to detect anomalies, identify fault-related patterns, and contribute to their prevention or mitigation.

Beyond detection, Olympus aims to serve as an experimental environment to study how to combine these models with deterministic supervision and safety mechanisms, so that AI model decisions can be evaluated and, when appropriate, used to trigger controlled system responses.

---

## Objectives
The primary objectives of the project are:

- **Critical Systems**: Study supervision, isolation, fault tolerance, and recovery architectures in embedded systems.
- **Edge AI**: Research the training, optimization, and deployment of small-scale AI models on resource-constrained platforms.
- **Fault Detection and Prediction**: Develop and evaluate techniques to identify anomalies, recognize pre-fault patterns, and estimate potential system degradation.
- **Mitigation and Recovery**: Experiment with strategies to contain fault effects, reconfigure the system, or trigger recovery mechanisms before an anomaly evolves into a hazardous condition.
- **Reproducible Research**: Provide an open platform to design experiments, inject faults in a controlled manner, gather telemetry, and compare different techniques and algorithms.

---

## Experimentation Platform
Olympus is conceived as a modular platform combining heterogeneous processing, FPGA-based supervision, and specialized expansion boards.

This architecture enables the exploration of various experimental scenarios, such as software hang detection, execution anomalies, power degradation, and other behaviors that may compromise system operation.

The availability of open hardware, firmware, software, and documentation aims to help other developers and researchers reproduce experiments, adapt the platform to their own needs, and develop novel solutions.

---

## Applications & Research
Olympus aims to provide a foundation for research projects, undergraduate and master's theses, and potential PhD dissertations related to:

- On-device anomaly detection using edge AI models.
- Fault prediction from telemetry and time-series data.
- Dataset generation through controlled fault injection.
- Comparison between traditional fault detection techniques and machine learning-based methods.
- Independent FPGA-based supervision and recovery mechanisms.
- Evaluation of latency, power consumption, and reliability of AI models.
- Design of mitigation mechanisms that do not rely solely on machine learning model decisions.

The ultimate objective is not only to detect when a system has failed, but to investigate to what extent certain failure conditions can be anticipated and responded to in a controlled, measurable, and reproducible manner.

---

## Target Audience
Olympus is aimed at embedded systems developers, students, researchers, and professionals interested in open hardware, embedded Linux, real-time operating systems (RTOS), FPGAs, artificial intelligence, and critical systems.

Although the project is primarily oriented toward individuals with some technical background, the documentation is designed to facilitate progressive learning, ranging from hardware bring-up to the development of advanced fault detection and mitigation experiments.

---

## System Documentation
To facilitate the development, integration, and evaluation of the platform, Olympus features structured technical documentation:

- **SRD — System Requirements Document**: Defines the functional, electrical, mechanical, software, and supervision requirements of the system.
- **SAD — System Architecture Document**: Describes the logical and physical architecture, processing components, supervision mechanisms, and inter-board connections.
- **ICD — Interface Control Document**: Specifies electrical and functional interfaces, connectors, buses, and inter-board communication signals.
- **FMEA — Failure Mode and Effects Analysis**: Analyzes anticipated failure modes, their effects, and applicable detection, prevention, or mitigation measures.
- **V&V Plan — Verification and Validation Plan**: Defines verification procedures, integration tests, controlled fault injection, and evaluation of supervision mechanisms.
- **NLnet Proposal and Roadmap**: Outlines development goals, milestones, open deliverables, and expected project outcomes.

---

## Project Philosophy
Olympus is intended to be an open platform for learning, experimentation, and research, rather than a certified safety-ready system for deployment in critical applications.

AI-based detection mechanisms will be studied as complementary tools to conventional supervision and safety mechanisms. Their results must be evaluated experimentally, paying special attention to false positives, false negatives, response times, and behavior under unexpected faults.

The ultimate purpose is to contribute to the development of more observable, resilient, and fault-manageable embedded systems by sharing designs, tools, documentation, and results that can benefit the entire community.