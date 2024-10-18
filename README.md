# H2F_meta
Meta repository of the components of the H2F system.
The aim of this repository is to aggregate all the component parts of the H2F system created at DHBW Mannheim.

## Relations
![Components relations](https://raw.githubusercontent.com/lkzjdnb/H2F_components_graph/master/graph.svg)

## Components description
- ![industrial_bridge](https://github.com/lkzjdnb/industrial_bridge) : Program to periodically fetch data from multiple devices (Modbus/S7) and convert and send it to multiple remotes (Prometheus/InfluxDB)
- ![H2F_control_deploy](https://github.com/lkzjdnb/H2F_control_deploy) : Ansible playbook to deploy a ready to use data collection/interface to a server
- ![grafana_dashboard_convert](https://github.com/lkzjdnb/grafana_dashboard_convert) : Grafana dashboards repository and associated script for downloading/converting
- ![bridge_config](https://github.com/lkzjdnb/bridge_config) : Configuration used for the bridge, and registers definition
- ![H2F_control](https://github.com/lkzjdnb/H2F_control) : Web User Interface (WebUI) to display and control the system (electrolyser/compressor)
- ![compressor_HMI_regs_extract](https://github.com/lkzjdnb/compressor_HMI_regs_extract) : Utilities to extract registers definition from the HyET Electrochemical-Compressor (EHC) PLC
- ![H2F_test_devices](https://github.com/lkzjdnb/H2F_test_devices) : Utility to emulate devices (Modbus/S7/Logo!) packaged as a docker compose
- ![modbus_test_server](https://github.com/lkzjdnb/modbus_test_server) : Simple script to emulate multiple ModBus devices, via TCP or RTU (serial-tty)
- ![snap7_test_server](https://github.com/lkzjdnb/snap7_test_server) : Simple script to emulate one S7 device (PLC or Logo) via TCP
- ![industrial_device](https://github.com/lkzjdnb/industrial_device) : Rust Interface providing unified access to devices using a typical industrial protocol (access to registers, ex. ModBus/S7)
- ![modbus_device](https://github.com/lkzjdnb/modbus_device) : Implementation of the industrial_device interface for communication with ModBus devices over TCP or RTU
- ![S7_devices](https://github.com/lkzjdnb/S7_devices) : Implementation of the industrial_device interface for communication with S7 devices over TCP (ex. S7-1200, Logo!7, Logo!8)
- ![Grafana](https://www.grafana.com) : Open source analytics & monitoring solution
- ![InfluxDB](https://www.influxdata.com) : Open source time-serie database
- ![DHBW_electrolyzer_rs](https://github.com/lkzjdnb/DHBW_electrolyzer_rs) : [Deprecated] Program to fetch data from modbus and send it to a remote. Deprecated in favor of industrial_bridge
- ![modbus_server](https://github.com/lkzjdnb/modbus_server) : [Deprecated] Script to emulate a ModBus device over TCP. Deprecated in favor of modbus_test_server
- ![DHBW_electrolyzer](https://github.com/YoriyoiAlpha/DHBW_electrolyzer) : [Deprecated] Script to fetch data from the electrolyzer and send it to a remote. Deprecated in favor of it's Rust equivalent DHBW_electrolyzer_rs
- ![DHBW_compressor](https://github.com/lkzjdnb/DHBW_compressor) : [Deprecated] Script to fetch data from the compressor and send it to a remote. Deprecated in favor of industrial_bridge
- ![electrolyzer_eta](https://github.com/YoriyoiAlpha/electrolyzer_eta) : Simple program to sweep the production rate of the electrolyzer
- ![DHBW_electrolyzer_dynamics](https://github.com/YoriyoiAlpha/DHBW_electrolyzer_dynamics) : Simple program to sweep the electrolyzer production rate and record it's status to InfluxDB
- ![DHBW_electrolyzer_writer](https://github.com/lkzjdnb/DHBW_electrolyzer_writer) : Example program to write to a register using the modbus_device library
