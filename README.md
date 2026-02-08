# LandslideX: Vulnerability Assessment & Risk Monitor

**LandslideX** is a machine-learning-powered geospatial platform designed to identify and monitor landslide-prone regions in Tamil Nadu. By integrating **Google Earth Engine (GEE)** with **TensorFlow**, the project analyzes historical terrain data and precipitation patterns to generate a static vulnerability heatmap, enabling long-term disaster planning and risk awareness.

## Key Features

* **Vulnerability Assessment Map:** Visualizes high, medium, and low-risk zones across Tamil Nadu using a standardized Red/Yellow/Green color-coding scheme.
* **Historical Data Mode:** Analyzes 10+ years of satellite and meteorological records (SRTM, CHIRPS) to determine baseline susceptibility without requiring real-time API keys.
* **Virtual Risk Simulation:** A built-in simulator that generates random environmental scenarios (slope, rainfall, soil moisture) to demonstrate model triggers and system alerts.
* **Satellite Hybrid Interface:** High-resolution satellite views layered with street-level infrastructure data to identify vulnerable roads and buildings.
* **Model Confidence Reporting:** Displays a real-time confidence score for predictions based on the underlying dataset quality.

##  Tech Stack

* **Backend:** Python (FastAPI), TensorFlow (.h5 model).
* **Geospatial Processing:** Google Earth Engine (GEE) Python API.
* **Frontend:** React.js, Leaflet.js (for interactive mapping).
* **Data Sources:** * **SRTM:** Digital Elevation Models (DEM) for slope analysis.
* **CHIRPS/GPM:** Historical precipitation peak tracking.
* **Sentinel-2:** Land cover and vegetation indexing (NDVI).



##  Installation & Setup

### Prerequisites

* Python 3.10+ (Python 3.11 recommended for long-term support).
* A Google Cloud Project with **Earth Engine API** enabled.

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/LandslideX.git
cd LandslideX

```

### 2. Set Up Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

```

### 3. Install Dependencies

```bash
pip install -r requirements.txt

```

### 4. Authenticate Google Earth Engine

```bash
earthengine authenticate

```

### 5. Run the Application

```bash
# Start the FastAPI Backend
uvicorn backend.main:app --reload

# In a separate terminal, start the Frontend
cd frontend
npm install
npm start

```

## Data Methodology

The prediction engine utilizes a supervised learning approach, weighting topographic factors against historical triggers:

* **Static Risk:** Calculated using slope intensity; areas  are prioritized for high susceptibility.
* **Historical Trigger:** Integrated CHIRPS daily peak data to identify zones where heavy rains frequently exceed ground saturation thresholds.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the Project.
2. Create your Feature Branch (`git checkout -b feature/NewFeature`).
3. Commit your Changes (`git commit -m 'Add NewFeature'`).
4. Push to the Branch (`git push origin feature/NewFeature`).
5. Open a Pull Request.
