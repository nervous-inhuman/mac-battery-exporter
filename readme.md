# macOS Battery Exporter

A [Prometheus](https://prometheus.io/) exporter for monitoring battery metrics on a macOS system. 


## Installation
On your Prometheus server host:

### Using pip
1. [Create a virtual environment](https://packaging.python.org/tutorials/installing-packages/#creating-virtual-environments) using python3.7 or higher
2. Install the dependencies via `pip install -r requirements.txt`

## Usage
`python3 mac_battery_exporter.py` 

## Prometheus Configuration
Add the following to your `prometheus.yml`:
```yaml
scrape_configs:
  - job_name: 'mac_battery_exporter'
    static_configs:
      - targets:
        - mac_device_ip:8333
```

## Exported Metrics
| Metric name                                           | Description                                               |
|:------------------------------------------------------|:----------------------------------------------------------|
| `sppower_battery_cycle_count`                         | Cycle Count                                               |
| `sppower_battery_fully_charged`                       | Fully Charged (1 or 0)                                    |
| `sppower_battery_is_charging`                         | Charging (1 or 0)                                         |
| `sppower_battery_current_capacity`                    | Charge Remaining (mAh)                                    |
| `sppower_battery_max_capacity`                        | Full Charge Capacity (mAh)                                |
| `sppower_current_amperage`                            | Amperage (mA)                                             |
| `sppower_current_voltage`                             | Voltage (mV)                                              |

## Contributing / Development
Pull requests are welcome!
