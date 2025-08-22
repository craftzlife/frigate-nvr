# Frigate-NVR Custom Home Camera System

This project configures a custom home camera system using [Frigate NVR](https://docs.frigate.video), an open-source network video recorder with real-time object detection. It uses Docker to run the standard Frigate image on Linux, with specific configurations for recording streams, live view, and detection models.

## Features

- **Multiple Cameras:** Living room, bedroom, and yard streams preconfigured.
- **Object Detection:** Real-time detection enabled.
- **Recording & Retention:** Motion-based recording with retention policies.
- **Live View:** RTSP streams for each camera.
- **Notifications:** Email alerts for detections.
- **Hardware Acceleration:** Configured for Intel VAAPI and Google Coral.

## Project Structure

- [`docker-compose.yml`](docker-compose.yml): Docker setup for Frigate NVR.
- [`config/config.yml`](config/config.yml): Main Frigate configuration (cameras, streams, detection, recording).

## Quick Start

1. **Clone the repository:**
   ```sh
   git clone https://github.com/craftzlife/frigate-nvr.git
   cd frigate-nvr
   ```

2. **Edit camera RTSP URLs (also password) in [`config/config.yml`](config/config.yml) if needed.**

3. **Start Frigate NVR:**
   ```sh
   docker-compose up -d
   ```

4. **Access the Web UI:**
   - Visit [http://localhost:8971](http://localhost:8971) in your browser.

## Configuration

- **Cameras:** Defined under `cameras:` in [`config/config.yml`](config/config.yml).
- **Detection:** Enabled via `detect:` section.
- **Recording:** Customize retention in `record:` section.
- **Notifications:** Set your email in `notifications:`.

## Hardware Notes

- USB Coral and Intel VAAPI are preconfigured. Adjust device mappings in [`docker-compose.yml`](docker-compose.yml) for your hardware.

## References

- [Frigate Documentation](https://docs.frigate.video)
-