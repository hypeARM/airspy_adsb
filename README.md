# sdr-enthusiasts/airspy_adsb

Docker container running AirSpy's `airspy_adsb` receiver. Designed to work in tandem with other sdr-enthusiasts containers. Builds and runs on i386, x86_64, arm64 and arm32v7.

`airspy_adsb` receives ADS-B data, and provides a BEAST socket for other containers to consume BEAST data.

## Environment Variables

| Environment Variable | `airspy_adsb`</br>option | Description | Default |
|----|----|----|----|
| `AIRSPY_ADSB_SERIAL` | `-s` | Device serial number | *unset* |
| `AIRSPY_ADSB_TIMEOUT` | `-t` | Aircraft timeout in seconds | `60` |
| `AIRSPY_ADSB_RF_GAIN` | `-g` | RF gain: `0` to `21` or `auto` | `auto` |
| `AIRSPY_ADSB_FEC_BITS` | `-f` | Forward Error Correction (FEC) bits | `1` |
| `AIRSPY_ADSB_PREAMBLE_FILTER` | `-e` | Preamble filter: `1` to `60` | `4` |
| `AIRSPY_ADSB_CPUTIME_TARGET` | `-C` | CPU processing time target (percentage): `5` to `95` | Disabled</br>*(adjusts preamble filter while running)*|
| `AIRSPY_ADSB_PREAMBLE_FILTER_MAX` | `-E` | Maximum preamble filter when using CPU target: `1` to `60` | `60` |
| `AIRSPY_ADSB_PREAMBLE_FILTER_NONCRC` | `-P` | Non-CRC Preamble filter: `1` to `$AIRSPY_ADSB_PREAMBLE_FILTER` | Disabled |
| `AIRSPY_ADSB_WHITELIST_THRESHOLD` | `-w` | Whitelist threshold: `1` to `20` | `5` |
| `AIRSPY_ADSB_MLAT_FREQ` | `-m` | MLAT frequency in MHz: `12`, `20` or `24` (Airspy R2 only) | *unset* |
| `AIRSPY_ADSB_VERBATIM_MODE` | `-n` | Set to `true` to enable Verbatim mode | *unset* |
| `AIRSPY_ADSB_DX_MODE` | `-x` | Set to `true` to enable DX mode | *unset* |
| `AIRSPY_ADSB_REDUCE_IF_BW` | `-r` | Set to `true` reduce the IF bandwidth to 4 MHz | *unset* |
| `AIRSPY_ADSB_RSSI_MODE` | `-R` | RSSI mode: `snr` (ref = 42 dB), `rms` (default: rms) | `rms` |
| `AIRSPY_ADSB_IGNORE_DF_TYPES` | `-D` | Ignore these DF types (comma separated list) | `24,25,26,27,28,29,30,31` |
| `AIRSPY_ADSB_BIAS_TEE` | `-b` | Set to `true` to enable Bias-Tee | *unset* |
| `AIRSPY_ADSB_BIT_PACKING` | `-p` | Set to `true` to enable Bit Packing | *unset* |
| `AIRSPY_ADSB_VERBOSE` | `-v` | Enable Verbose mode | *unset* |