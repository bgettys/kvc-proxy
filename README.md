# kvc-proxy

A sidecar proxy designed to create the appearance of a single virtual Kafka cluster from multiple clusters.

## Overview

The kvc-proxy is a sidecar proxy that lives alongside another process, either in the same network namespace (Docker/Kubernetes) or on the same bare metal/VM host. The service being proxied remains oblivious to the proxy's existence.

**Key Features:**
- Connects to multiple Kafka clusters
- Presents a unified virtual cluster interface to the proxied service
- Makes all operations appear as though they're happening on a single cluster

## Building

### Prerequisites
- C++23 compatible compiler (GCC 11+, Clang 14+, or MSVC 2022+)
- CMake 3.20 or higher

### Build Instructions

#### Linux/macOS

```bash
# Create build directory
mkdir build && cd build

# Configure the project
cmake ..

# Build the project
make

# Run the executable
./bin/kvc-proxy
```

#### Windows

##### Using Visual Studio

```cmd
# Create build directory
mkdir build
cd build

# Configure the project (generates Visual Studio solution)
cmake ..

# Build the project
cmake --build . --config Debug

# Run the executable
bin\Debug\kvc-proxy.exe
```

##### Using Command Line (MinGW/MSYS2)

```bash
# Create build directory
mkdir build && cd build

# Configure the project
cmake .. -G "MinGW Makefiles"

# Build the project
mingw32-make

# Run the executable
bin/kvc-proxy.exe
```

##### Using PowerShell

```powershell
# Create build directory
mkdir build
cd build

# Configure the project
cmake ..

# Build the project
cmake --build .

# Run the executable
.\bin\Debug\kvc-proxy.exe
```

### Alternative build with specific build type

#### Linux/macOS
```bash
# Debug build
cmake -DCMAKE_BUILD_TYPE=Debug ..
make

# Release build
cmake -DCMAKE_BUILD_TYPE=Release ..
make
```

#### Windows
```cmd
# Debug build
cmake --build . --config Debug

# Release build
cmake --build . --config Release
```

## Project Structure

```
kvc-proxy/
├── CMakeLists.txt
├── README.md
├── .gitignore
├── src/
│   └── main.cpp
└── include/
    └── (header files will go here)
```

## License

This project is licensed under the Unlicense - see the LICENSE file for details. 