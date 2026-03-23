# 🚀 CoinDesk Spring Boot API

**完整功能 Spring Boot 專案：幣別 CRUD + CoinDesk API 串接 + 資料轉換**

[![Maven](https://img.shields.io/badge/Maven-3.9.6-brightgreen.svg)](https://maven.apache.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.7.18-green.svg)](https://spring.io/projects/spring-boot)
[![JDK 8](https://img.shields.io/badge/JDK-1.8-orange.svg)](https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## ✨ 專案功能

### 技術棧
- **Build**: Maven 3.9.6
- **框架**: Spring Boot 2.7.18（JDK 8 相容）
- **資料庫**: H2 In-Memory + Spring Data JPA
- **外部 API**: CoinDesk 匯率 API

### 核心功能
1. **幣別 CRUD API**（查詢/新增/修改/刪除）
2. **CoinDesk API 串接**（原始 JSON）
3. **資料轉換 API**（匯率 + 中文幣名 + 時間格式化）

## 📋 API 文件

| 方法 | 端點 | 說明 | 範例回應 |
|------|------|------|----------|
| `GET` | `/api/currencies` | 查詢所有幣別 | `[{"id":1,"code":"USD","chineseName":"美元","rate":32.5},...]` |
| `GET` | `/api/currencies/{id}` | 查詢單筆 | `{"id":1,"code":"USD","chineseName":"美元","rate":32.5}` |
| `POST` | `/api/currencies` | 新增幣別 | `{"code":"TWD","chineseName":"台幣","rate":1}` |
| `PUT` | `/api/currencies/{id}` | 修改幣別 | 同上 |
| `DELETE` | `/api/currencies/{id}` | 刪除幣別 | `204 No Content` |
| `GET` | `/api/coindesk/raw` | CoinDesk 原始資料 | `{"time":{"updatedISO":"..."},"bpi":{...}}` |
| `GET` | `/api/coindesk/converted` | **轉換結果** | `[{"updateTime":"2024/09/02 15:07:20","code":"USD","chineseName":"美元","rate":57756.298},...]` |
| `GET` | `/h2-console` | **H2 管理介面** | JDBC: `jdbc:h2:mem:testdb` / sa / (空密碼) |

## 🧪 測試結果展示

### 1. 幣別 CRUD 測試
