# Jenkins CI/CD Pipeline Demo

Bu proje, **Jenkins** kullanarak Python projesi için Continuous Integration ve Continuous Delivery (CI/CD) sürecini göstermektedir.  
Pipeline, Jenkinsfile üzerinden çalıştırılabilir ve proje build, test ve deploy adımlarını otomatikleştirir.

---

## 📦 İçerik

- `Jenkinsfile` – Pipeline tanımı  
- `app/` – Python uygulama dosyaları  
- `tests/` – Pytest ile yazılmış basit testler  
- `README.md` – Proje açıklaması

---

## ⚙️ Gereksinimler

- [Jenkins](https://www.jenkins.io/download/) kurulu olmalı  
- [Python 3.9+](https://www.python.org/)  
- [Docker](https://www.docker.com/) (opsiyonel, Jenkins agent olarak kullanmak için)

---

## 🚀 Kurulum ve Çalıştırma

### 1. Jenkins kurulumu
- Jenkins’i bilgisayarınıza veya sunucuya kurun.  
- Web arayüzüne gidin: `http://localhost:8080`

### 2. Projeyi Jenkins’e ekleyin
- Yeni bir pipeline job oluşturun.  
- Pipeline script olarak repo URL’sini verin veya `Jenkinsfile` kullanın:
```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python -m pip install --upgrade pip'
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest tests/'
            }
        }
    }
}
3. Pipeline’ı çalıştırın
Jenkins web arayüzünde Build Now butonuna tıklayın
Adımların başarıyla geçtiğini kontrol edin

🧪 Testler
Testleri manuel olarak çalıştırmak için:

cd tests
pytest
