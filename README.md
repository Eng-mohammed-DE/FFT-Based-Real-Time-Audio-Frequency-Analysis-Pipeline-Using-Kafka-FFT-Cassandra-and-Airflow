# FFT-Based-Real-Time-Audio-Frequency-Analysis-Pipeline-Using-Kafka-FFT-Cassandra-and-Airflow
A real-time audio analysis pipeline captures audio, applies FFT to extract frequency data, streams results via Kafka, and stores them in Cassandra. Airflow orchestrates the process, enabling automated and scalable frequency analytics.

## 📌 Project Overview

The system captures live audio data, applies Fast Fourier Transform (FFT) to analyze frequency components, streams data using Kafka, stores results in Cassandra for fast querying, and orchestrates all tasks using Airflow.

## ⚙️ Tools & Technologies

- **Kafka** – Real-time messaging system for streaming audio data
- **FFT (Python/Numpy)** – Converts time-domain audio signals to frequency domain
- **Apache Cassandra** – NoSQL database for storing frequency data
- **Apache Airflow** – Pipeline orchestration and scheduling
- **Python** – Core language for audio processing, Kafka integration, and FFT

## 🔁 Pipeline Flow

1. **Audio Ingestion**
   - A Python producer captures live audio input (e.g., via `pyaudio`).
   - It sends audio chunks to Kafka topics.

2. **FFT Processing**
   - A Kafka consumer receives audio data.
   - Applies FFT (using NumPy) to extract frequency components.

3. **Data Storage**
   - Transformed frequency data is written to Apache Cassandra.
   - Schema includes timestamp, dominant frequencies, and signal metadata.

4. **Workflow Orchestration**
   - Apache Airflow schedules and monitors tasks like:
     - Audio ingestion
     - FFT processing
     - Cassandra writing
     - Health checks


