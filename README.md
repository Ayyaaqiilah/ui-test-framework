# UI Test Framework – Cucumber + Selenium + Java + Gradle

## Deskripsi
Proyek ini adalah kerangka kerja otomasi pengujian UI web menggunakan **Cucumber**, **Selenium**, **Java**, dan **Gradle**.  
Framework ini mengimplementasikan **Page Object Model (POM)** dan **Gherkin syntax** untuk menulis test case yang mudah dibaca.

Website yang diuji: [https://www.saucedemo.com/](https://www.saucedemo.com/)

## Tujuan
Framework ini dirancang untuk mempermudah penulisan dan eksekusi test otomatis untuk aplikasi berbasis web, serta menghasilkan laporan pengujian yang terstruktur.

## Struktur Proyek
```
src
 ├── main
 │    └── java
 │         └── pages       # Kelas Page Object (LoginPage, dsb)
 └── test
      ├── java
      │     ├── runners   # TestRunner untuk eksekusi Cucumber
      │     └── steps     # Step Definitions (LoginSteps)
      └── resources
            └── features  # File .feature (Gherkin scenarios)
```

## Dependensi
- Java 17+ (kamu pakai JDK 23 tapi kompatibel)
- Gradle 8+
- Selenium 4.21.0
- Cucumber-Java 7.15.0
- Cucumber-JUnit 7.15.0
- WebDriverManager 5.9.2

## Contoh Skenario Gherkin
```gherkin
Feature: Login functionality

  Scenario: Successful login
    Given user is on the login page
    When user enters username "standard_user" and password "secret_sauce"
    And clicks login button
    Then user should be redirected to the products page
```

## Cara Menjalankan Test
### Dari IntelliJ IDEA
1. Buka kelas `TestRunner.java`.
2. Klik tombol **Run**.

### Dari Command Line
```bash
./gradlew clean test
```

## Laporan
Setelah menjalankan test, laporan HTML bisa ditemukan di:
```
build/reports/tests/test/index.html
```
