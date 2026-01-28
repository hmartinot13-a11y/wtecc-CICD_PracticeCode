# Intro to CI/CD Practice Code

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

This repository contains the practice code for the labs in **IBM-CD0215EN-SkillsNetwork Introduction to CI/CD**

## Contents

- Lab 1: [Build an empty Pipeline](labs/01_base_pipeline/README.md)
- Lab 2: [Adding GitHub Triggers](labs/02_add_git_trigger/README.md)
- Lab 3: [Use Tekton CD Catalog](labs/03_use_tekton_catalog/README.md)
- Lab 4: [Integrate Unit Test Automation](labs/04_unit_test_automation/README.md)
- Lab 5: [Building an Image](labs/05_build_an_image/README.md)
- Lab 6: [Deploy to Kubernetes](labs/06_deploy_to_kubernetes/README.md)

## Instructor

John Rofrano, Senior Technical Staff Member, DevOps Champion, @ IBM Research

## <h3 align="center"> © IBM Corporation 2022. All rights reserved. <h3/>

graph TD
    %% Cluster
    subgraph Cluster["Kubernetes Cluster (Control Plane Managed)"]
        
        %% Node 1
        subgraph Node1["Node 1 (Worker)"]
            subgraph VMGroup1["VM1 | VM2 | VM3"]
                subgraph Pods1["Pods"]
                    PodA["Pod A\n- Container 1\n- Container 2"]
                    PodB["Pod B\n- Container 1"]
                    PodC["Pod C\n- Container 1"]
                end
            end
        end

        %% Node 2
        subgraph Node2["Node 2 (Worker)"]
            subgraph VMGroup2["VM4 | VM5 | VM6"]
                subgraph Pods2["Pods"]
                    PodD["Pod D\n- Container 1\n- Container 2"]
                    PodE["Pod E\n- Container 1"]
                    PodF["Pod F\n- Container 1"]
                end
            end
        end

        %% Node 3
        subgraph Node3["Node 3 (Worker)"]
            subgraph VMGroup3["VM7 | VM8 | VM9"]
                subgraph Pods3["Pods"]
                    PodG["Pod G\n- Container 1\n- Container 2"]
                    PodH["Pod H\n- Container 1"]
                    PodI["Pod I\n- Container 1"]
                end
            end
        end
    end

    %% Connections between nodes
    Node1 --- Node2
    Node2 --- Node3
    Node3 --- Node1
