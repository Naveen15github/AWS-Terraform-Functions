# AWS-Terraform-Functions

## 📚 Overview

This repository documents my **hands-on learning and implementation of Terraform built-in functions** using real AWS-oriented scenarios.  
The objective of this module was not just to understand syntax, but to **apply functions practically** while building clean, reusable, and production-aware Terraform configurations.

All examples were tested locally using `terraform console`

---

## 🎯 Learning Objectives

By completing this module, I achieved the following:

- Gained strong understanding of **all major Terraform function categories**
- Learned **when and why** to use specific functions
- Practiced **function chaining** for complex transformations
- Used **terraform console** for quick experimentation
- Implemented **validation and error handling**
- Handled **sensitive values securely**
- Built **dynamic and reusable Terraform code**
- Applied functions in **AWS-focused real-world scenarios**

---

## 🧪 Terraform Console Practice

Before implementing assignments, I used the Terraform console extensively to understand function behavior.

```hcl
lower("HELLO WORLD")
max(5, 12, 9)
trim("  hello  ")
chomp("hello\n")
reverse(["a", "b", "c"])
````

Using the console helped me:

* Validate function outputs instantly
* Avoid unnecessary `terraform apply` cycles
* Build confidence before writing `.tf` files

---


## 🚀 Quick Start

```bash
terraform init
terraform plan
terraform apply -auto-approve
terraform output
terraform destroy -auto-approve
```

---

## 📖 Terraform Function Categories Covered

### String Functions

`lower()`, `upper()`, `replace()`, `substr()`, `trim()`, `split()`, `join()`, `chomp()`

### Numeric Functions

`abs()`, `max()`, `min()`, `sum()`, `ceil()`, `floor()`

### Collection Functions

`length()`, `concat()`, `merge()`, `reverse()`, `toset()`, `tolist()`

### Type Conversion

`tonumber()`, `tostring()`, `tobool()`

### File Functions

`file()`, `fileexists()`, `dirname()`, `basename()`

### Date / Time Functions

`timestamp()`, `formatdate()`, `timeadd()`

### Validation Functions

`can()`, `regex()`, `contains()`, `startswith()`, `endswith()`

### Lookup Functions

`lookup()`, `element()`, `index()`

---

## 📁 Repository Structure

```text
.
├── README.md
├── DEMO_GUIDE.md
├── provider.tf
├── backend.tf
├── variables.tf
├── main.tf
└── outputs.tf
```

---

## ✅ Assignment Breakdown

### Assignment 1: Project Naming ⭐

**Goal:** Convert
`"Project ALPHA Resource"` → `project-alpha-resource`

**Functions Used:**
`lower()`, `replace()`

I used chained string functions to standardize naming conventions, which is critical for AWS resource consistency.

---

### Assignment 2: Resource Tagging ⭐

**Goal:** Merge default and environment-specific tags

**Function Used:**
`merge()`

This allowed me to centralize tagging logic and avoid duplication across resources.

---

### Assignment 3: S3 Bucket Naming ⭐⭐

**Goal:** Ensure AWS-compliant bucket names

**Functions Used:**
`substr()`, `replace()`, `lower()`

I sanitized bucket names to avoid uppercase letters, invalid characters, and length issues.

---

### Assignment 4: Security Group Ports ⭐⭐

**Goal:** Convert `"80,443,8080"` into ingress rules

**Functions Used:**
`split()`, `for`, `join()`

This helped me dynamically generate security group rules instead of writing repetitive blocks.

---

### Assignment 5: Environment Lookup ⭐⭐

**Goal:** Select EC2 instance size based on environment

**Function Used:**
`lookup()`

This ensured safe defaults and environment-aware infrastructure.

---

### Assignment 6: Instance Validation ⭐⭐⭐

**Goal:** Validate instance type format

**Functions Used:**
`length()`, `can()`, `regex()`

I enforced strict validation rules to prevent invalid inputs during runtime.

---

### Assignment 7: Backup Configuration ⭐⭐

**Goal:** Validate backup naming and hide sensitive values

**Functions Used:**
`endswith()`, `sensitive()`

Sensitive variables were masked from logs while still being usable internally.

---

### Assignment 8: File Path Processing ⭐⭐

**Goal:** Check file existence and extract directory paths

**Functions Used:**
`fileexists()`, `dirname()`

This is useful for automation workflows dependent on config files.

---

### Assignment 9: Location Management ⭐

**Goal:** Combine region lists and remove duplicates

**Functions Used:**
`concat()`, `toset()`

I handled multi-region data cleanly while avoiding duplication.

---

### Assignment 10: Cost Calculation ⭐⭐

**Goal:** Process costs and credits

**Functions Used:**
`abs()`, `max()`, `sum()`

I used numeric functions along with spread operators for realistic cost calculations.

---

### Assignment 11: Timestamp Management ⭐⭐

**Goal:** Format timestamps for tagging and naming

**Functions Used:**
`timestamp()`, `formatdate()`

This is useful for auditability and versioned resources.

---

### Assignment 12: File Content Handling ⭐⭐⭐

**Goal:** Read JSON config and store secrets

**Functions Used:**
`file()`, `jsondecode()`, `jsonencode()`

This demonstrated real-world secret and configuration handling patterns.

---

## 🧠 Key Learnings

* Terraform functions are **essential for clean IaC**
* `terraform console` is a powerful learning and debugging tool
* Validation prevents costly runtime failures
* Function chaining unlocks complex transformations
* Dynamic blocks + functions = scalable infrastructure
* Sensitive data must be handled intentionally

---

## 🎯 Interview-Ready Summary

> “In this project, I implemented 12 hands-on Terraform assignments focused entirely on built-in functions. I used real AWS scenarios like EC2, S3, security groups, tagging, validation, timestamps, and file handling. I validated inputs, handled sensitive data securely, and used terraform console extensively to test logic before applying infrastructure.”

---

## 📚 References

* Terraform Functions Documentation
* Terraform Console
* AWS Provider Documentation
* DEMO_GUIDE.md

---

