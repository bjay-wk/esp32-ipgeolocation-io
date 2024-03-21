# esp32-ipgeolocation-io

ipgeolocation io Api for espidf.

[Loaction by ipgeolocation.io](ipgeolocation.io)

## How to Add to you project
### Using platformio

- Add `https://github.com/bjay-wk/esp32-ipgeolocation-io.git` to `lib_deps`in `platformio.ini`.
- In the CMakeLists.txt in your root you have to add before project(...):
  ```cmake
  get_filename_component(configName "${CMAKE_BINARY_DIR}" NAME)
  FILE(GLOB_RECURSE kconfigs_pio_lib_deps ${CMAKE_SOURCE_DIR}/.pio/libdeps/${configName}/*/Kconfig)
  list(APPEND kconfigs ${kconfigs_pio_lib_deps})
  ```

### Using Espidf
In `src/idf_component.yml` of your project add

```yaml
esp32-ipgeolocation-io:
  git: https://github.com/bjay-wk/esp32-ipgeolocation-io.git
```

And in `src/CMakeLists.txt` of your project

```make
idf_component_register(...
    REQUIRES esp32-ipgeolocation-io
    ...
)
```

### Run Menuconfig to add you api key

Retreive your API key [here](https://app.ipgeolocation.io/login)

Then in menuconfig copy your key in :
- Component config > Ip Geolocation Io > api key