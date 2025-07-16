# pg-to-snowflake-streaming

🚀 A Real-Time Data Pipeline for streaming changes from PostgreSQL to Snowflake using Kafka & Debezium.

## 📌 Overview

This project demonstrates a real-time Change Data Capture (CDC) pipeline built as part of my Data Engineering journey at the **Information Technology Institute (ITI)**.

The pipeline captures live changes from a PostgreSQL database and streams them to Snowflake using Kafka Connect, enabling near real-time analytics.

---

## ⚙️ Tech Stack

- **PostgreSQL** – Source database
- **Debezium** – Captures CDC (Change Data Capture) events from PostgreSQL
- **Apache Kafka** – Message broker to stream the events
- **Kafka Connect Snowflake Sink Connector** – Loads streaming data into Snowflake
- **Snowflake** – Cloud data warehouse for storing and analyzing the streamed data
- **Docker & Docker Compose** – For containerized and reproducible setup
- **Public/Private Key Authentication** – For secure Snowflake access

---

## 🔄 How It Works

1. **Debezium** monitors the PostgreSQL database for insert/update events.
2. The captured changes are published to **Kafka topics**.
3. **Kafka Connect** picks up these messages and sends them to **Snowflake** via the Snowflake Sink Connector.
4. **Data lands in Snowflake** in near real-time, ready for querying and analysis.

---

## 📁 Project Structure

```bash
.
├── docker-compose.yml        # Defines all services (Postgres, Kafka, Connect, etc.)
├── debezium-config           # Configs for Debezium connector
├── snowflake-connector-config # JSON config for Snowflake Sink
├── init.sql                  # Sample data + table creation
└── README.md                 # You're here!
