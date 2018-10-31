# Define Management Zones in Dynatrace to create Access Control

[Management Zones](https://www.dynatrace.com/news/blog/grant-fine-grained-access-rights-using-management-zones-beta/) allow you to define who is going to see and who has access to what type of Fullstack data. There are many ways to slice your environment and it will depend on your organizational structure & processes.
This lab assumes that there are following teams:
* a Frontend Team responsible for FRONTEND services
* a Dev Team responsible for the whole Development Environment
* an Architecture Team responsible for Development & Staging
* an Operations Team responsible for all Infrastructure (=all Hosts)
* a Business Team responsible for all applications

Based on this assumption, you will learn how to create Management Zones that will give each team access to the data they are supposed to see. 

## Step 1: Create Management Zone for Frontend Team
1. Go to **Settings**, **Management zones**, and click on **Create management zones**.
1. Set the name of the management zone: `Frontend Services`.
1. **Add new rule** for frontend service:
    * Rule applies to: `Services` 
    * Condition on `SERVICE_TYPE` equals `FRONTEND`
1. Select **Apply to underlying process groups of matching services**.
1. **Save** and test the Management Zone in the Smartscape View.

## Step 2: Create Management Zone for Dev Team
1. Go to **Settings**, **Management zones**, and click on **Create management zones**.
1. Set the name of the management zone: `Dev Team`.
1. **Add new rule** for frontend service:
    * Rule applies to: `Services` 
    * Condition on `Kubernetes` equals `dev`
1. Select **Apply to underlying process groups of matching services**.
1. **Save** and test the Management Zone in the Smartscape View.

## Step 3: Create Management Zone for Architect Team
1. Go to **Settings**, **Management zones**, and click on **Create management zones**.
1. Set the name of the management zone: `Architect Team`.
1. **Add new rule** for frontend service:
    * Rule applies to: `Services` 
    * Condition on `Kubernetes` equals `dev`
1. Select **Apply to underlying process groups of matching services**.
1. **Add new rule** for frontend service:
    * Rule applies to: `Services` 
    * Condition on `Kubernetes` equals `staging`
1. Select **Apply to underlying process groups of matching services**.
1. **Save** and test the Management Zone in the Smartscape View.

## Step 4: Create Management Zone for Operations Team
Create a Management Zone for all HOSTS & Processes.

## Step 5: (optional) Create Management Zone for Business Team
Create a Management Zone that covers all Web Applications.