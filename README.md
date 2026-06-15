# PAIRS UAV System (ROS 2)

The **PAIRS UAV System** is a control, estimation, and simulation stack for
multirotor aerial vehicles.
We build it to support safe, replicable real-world experimental validation of
research in planning, control, estimation, computer vision, and tracking.

This is the **ros2** branch (ROS 2 Jazzy, ament_cmake). For the ROS 1 Noetic
version, see the [`ros1` branch](https://github.com/pairs-lab/pairs_uav_system/tree/ros1).

## System properties

The system is

* built on the [Robot Operating System 2](https://www.ros.org/) Jazzy,
* meant to be executed entirely onboard on a companion computer,
* able to control underactuated multirotor helicopters,
* composed of control, state estimation, mapping, and planning pipelines.

## Documentation

The system is a research-oriented platform that evolves rapidly. Each package
carries its own README; we keep the launch files and the code itself readable so
they double as documentation.

## Installation

### From the PAIRS apt repository (recommended)

1. Install ROS 2 Jazzy and configure your environment per the ROS 2 docs.

2. Add the signed PAIRS repository:
```bash
curl -fsSL https://thanhnguyencanh.github.io/apt/KEY.gpg | sudo gpg --dearmor -o /usr/share/keyrings/pairs.gpg
echo "deb [signed-by=/usr/share/keyrings/pairs.gpg] https://thanhnguyencanh.github.io/apt jazzy main" \
  | sudo tee /etc/apt/sources.list.d/pairs.list
sudo apt update
```

3. Install the full PAIRS UAV System:
```bash
sudo apt install ros-jazzy-pairs-uav-system-full
```

4. Start the example simulation session:
```bash
cd /opt/ros/jazzy/share/pairs_multirotor_simulator/tmux/pairs_one_drone
./start.sh
```

## System components

| Main metapackages       | Contents               | Repository                                                                  | Package                            |
|-------------------------|------------------------|-----------------------------------------------------------------------------|------------------------------------|
| PAIRS UAV System        | UAV Core & UAV Modules | [pairs_uav_system](https://github.com/pairs-lab/pairs_uav_system/tree/ros2) | `ros-jazzy-pairs-uav-system`       |
| PAIRS UAV System - Full | All of the below       | [pairs_uav_system](https://github.com/pairs-lab/pairs_uav_system/tree/ros2) | `ros-jazzy-pairs-uav-system-full`  |

| Optional Modules & metapackages | Repository                                                                                             | Package                                     |
|---------------------------------|--------------------------------------------------------------------------------------------------------|---------------------------------------------|
| UAV Core                        | [pairs_uav_core](https://github.com/pairs-lab/pairs_uav_core/tree/ros2)                                 | `ros-jazzy-pairs-uav-core`                  |
| UAV Modules                     | [pairs_uav_modules](https://github.com/pairs-lab/pairs_uav_modules/tree/ros2)                           | `ros-jazzy-pairs-uav-modules`               |
| Octomap Mapping+Planning        | [pairs_octomap_mapping_planning](https://github.com/pairs-lab/pairs_octomap_mapping_planning/tree/ros2) | `ros-jazzy-pairs-octomap-mapping-planning`  |
| OpenVINS Core                   | [pairs_open_vins_core](https://github.com/pairs-lab/pairs_open_vins_core/tree/ros2)                     | `ros-jazzy-pairs-open-vins-core`            |
| PointLIO Core                   | [pairs_point_lio_core](https://github.com/pairs-lab/pairs_point_lio_core/tree/ros2)                     | `ros-jazzy-pairs-point-lio-core`            |
| Precise Landing                 | [pairs_precise_landing](https://github.com/pairs-lab/pairs_precise_landing/tree/ros2)                   | `ros-jazzy-pairs-precise-landing`           |

| Simulators                 | Repository                                                                                                | Package                                     |
|----------------------------|-----------------------------------------------------------------------------------------------------------|---------------------------------------------|
| PAIRS Multirotor Simulator | [pairs_multirotor_simulator](https://github.com/pairs-lab/pairs_multirotor_simulator/tree/ros2)           | `ros-jazzy-pairs-multirotor-simulator`      |
| FlightForge Simulator      | [pairs_uav_flightforge_simulator](https://github.com/pairs-lab/pairs_uav_flightforge_simulator/tree/ros2) | `ros-jazzy-pairs-uav-flightforge-simulator` |
| Gazebo Simulator           | [pairs_uav_gazebo_simulation](https://github.com/pairs-lab/pairs_uav_gazebo_simulation/tree/ros2)         | `ros-jazzy-pairs-uav-gazebo-simulator`      |

| Hardware API plugins | Repository                                                                                | Package                             |
|----------------------|-------------------------------------------------------------------------------------------|-------------------------------------|
| PX4 API              | [pairs_uav_px4_api](https://github.com/pairs-lab/pairs_uav_px4_api/tree/ros2)             | `ros-jazzy-pairs-uav-px4-api`       |
| DJI Tello API        | [pairs_uav_dji_tello_api](https://github.com/pairs-lab/pairs_uav_dji_tello_api/tree/ros2) | `ros-jazzy-pairs-uav-dji-tello-api` |

## Example packages

| Examples                 | Repository                                                                                              |
|--------------------------|---------------------------------------------------------------------------------------------------------|
| Core examples            | [pairs_core_examples](https://github.com/pairs-lab/pairs_core_examples/tree/ros2)                       |
| Computer Vision examples | [pairs_computer_vision_examples](https://github.com/pairs-lab/pairs_computer_vision_examples/tree/ros2) |

## Backwards compatibility and updates

We do not guarantee backward compatibility at any time. The platform evolves
according to the needs of the PAIRS group, and updates may not be compatible
with users' local configs, simulation worlds, or tmux sessions. When a change
requires user action, we will open an issue in this repository labeled
**users-read-me**.

# Disclaimer

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
