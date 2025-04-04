# 🏆 Web Application Performance Testing  

This project focuses on performance testing of web applications using **JMeter** and **LoadRunner**. It also integrates with **Jenkins** for automated test execution.

---

## 📁 Project Structure  
```
WebApp-Performance-Testing/
│-- jmeter-test-plans/
│   ├── load-test.jmx
│   ├── stress-test.jmx
│-- loadrunner-scripts/
│   ├── load-test.lrs
│   ├── stress-test.lrs
│-- reports/  
│   ├── jmeter-report.html
│   ├── loadrunner-report.html
│-- scripts/
│   ├── jenkins-pipeline.groovy
│-- README.md
```

---

## 🚀 Running JMeter Performance Tests  

### **Load Testing**  
```sh
jmeter -n -t jmeter-test-plans/load-test.jmx -l results.jtl -e -o reports/
```

### **Stress Testing**  
```sh
jmeter -n -t jmeter-test-plans/stress-test.jmx -l results.jtl -e -o reports/
```

---

## 🔥 Running LoadRunner Tests  

### **Load Testing**  
```sh
lr_run -sc loadrunner-scripts/load-test.lrs -result results/
```

### **Stress Testing**  
```sh
lr_run -sc loadrunner-scripts/stress-test.lrs -result results/
```

---

## 🤖 Automating Performance Tests with Jenkins  

### **Jenkins Pipeline Script (`Jenkinsfile`)**  
```groovy
pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/yourusername/WebApp-Performance-Testing.git'
            }
        }
        stage('Execute JMeter Tests') {
            steps {
                sh 'jmeter -n -t jmeter-test-plans/load-test.jmx -l results.jtl -e -o reports/'
            }
        }
        stage('Execute LoadRunner Tests') {
            steps {
                sh 'lr_run -sc loadrunner-scripts/load-test.lrs -result results/'
            }
        }
        stage('Store Reports') {
            steps {
                archiveArtifacts artifacts: 'reports/**', fingerprint: true
            }
        }
    }
}
```

---

## 📌 Steps to Upload to GitHub  

1️⃣ **Go to GitHub** → Click **"New repository."**  
2️⃣ Enter repository name (e.g., `WebApp-Performance-Testing`) → Click **"Create repository."**  
3️⃣ Click **"Add file" → "Upload files."**  
4️⃣ **Drag and drop** your project folder OR manually select each file.  
5️⃣ Add a commit message (e.g., `"Initial upload: Performance testing project"`).  
6️⃣ Click **"Commit changes."**  

✅ **Done! Your project is now on GitHub.** 🎉  

---

## 📊 Key Takeaways  
- **JMeter** for load and stress testing  
- **LoadRunner** for deep system performance analysis  
- **Jenkins** for test automation  
- **Reports generation** to analyze test results  

---

🔗 **Author**: *Your Name*  
🔗 **GitHub Repository**: [Your Repository Link]  

```
🚀 Happy Testing! 🚀
```
