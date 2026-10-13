<!-- SPDX-License-Identifier: CC-BY-4.0 -->

# Duranta OpenAirInterface Documentation Overview

This page is the entry point to the Duranta OpenAirInterface (OAI) documentation. It
links to general information, tutorials, design documents, images, libraries,
radios, testing and developer tools.

> [!IMPORTANT]
> Keep your repository rebased on `develop`, or read the documentation of the
> version you are using, so that it matches the features available in your
> repository. If you pulled `develop` some time ago, your repository may now be
> behind it.

More general information is available in the
[OpenAirInterface GitLab wiki](https://gitlab.eurecom.fr/oai/openairinterface5g/-/wikis/home).

[[_TOC_]]

## General

- [Feature set](./FEATURE_SET.md): supported features
- [Getting the sources](./GET_SOURCES.md): how to download the sources
- [Building OAI](./BUILD.md): how to build the sources
- [Environment variables](./environment-variables.md): environment variables used by OAI
- [Tuning and security](./tuning_and_security.md): performance and security considerations
- [Supported hardware and operating systems](./Supported_Hardware_Operating_System.md)
- [Key performance indicators](./kpi.md): KPIs of the OAI code base

## Tutorials

### Getting started with 5G

- [OAI 5G core network](./NR_SA_Tutorial_OAI_CN5G.md)
- [OAI gNB with a COTS UE](./NR_SA_Tutorial_COTS_UE.md)
- [OAI NR-UE](./NR_SA_Tutorial_OAI_nrUE.md)
- [Multiple OAI NR-UEs with the RFsimulator](./NR_SA_Tutorial_OAI_multi_UE.md)

### Running OAI

- [Running the gNB](./RUNMODEM.md): simulators, hardware, SDAP and custom DRBs,
  IF setups and arbitrary frequencies, MIMO
- [NR-UE configuration and modes](./runmodem-nrue.md): phy-test, do-ra, noS1
- [Setting the gNB frequency](./gNB_frequency_setup.md)
- [5G NSA setup](./TESTING_OAI_NSA_COTS_UE.md)
- [NTN setup](./ntn-configuration.md)
- [Handover](./handover-tutorial.md)
- [F1-based NR-DC](./nr-dc.md)
- [Positioning reference signal (PRS)](./RUN_NR_PRS.md)
- [E2 agent](../openair2/E2AP/README.md)
- [RT data recording app](./data_recording.md)
- [Packages](./packages.md)

### Functional splits

- [O-RAN 7.2 fronthaul](./ORAN_FHI7.2_Tutorial.md)
- [OAI-VNF and OAI-PNF](./nfapi.md): FAPI/nFAPI split, with general remarks on FAPI/nFAPI
- [NVIDIA Aerial and Foxconn](./Aerial_FAPI_Split_Tutorial.md)

### Hardware acceleration

- [LDPC accelerators (Xilinx T2, Intel ACCs)](./LDPC_OFFLOAD_SETUP.md)
- [NR-UE with the LDPC CUDA accelerator](./NR_SA_Tutorial_OAI_nrUE_GPU_offload.md)
- [GPU-accelerated channel simulation](../openair1/SIMULATION/TOOLS/DOC/gpu_acceleration.md)

### Simulators

- [Physical simulators](./physical-simulators.md)
- [Channel simulator](../openair1/SIMULATION/TOOLS/DOC/channel_simulation.md)
- [L2 simulator](./L2NFAPI.md)
- [4G L1 simulator](./L1SIM.md): we recommend the RFsimulator instead
- [4G device-to-device (D2D) emulator](./d2d_emulator_setup.md)

### Legacy

These documents are unmaintained and no longer valid:

- [L2 simulator without S1](./L2NFAPI_NOS1.md)
- [L2 simulator with S1](./L2NFAPI_S1.md)

## Designs

- [Software architecture](./SW_archi.md): general notes
- [L1 flow graph in the gNB](./SW-archi-graph.md)
- [L1 threads in the NR-UE](./nr-ue-design.md)
- [gNB MAC](./MAC/mac-usage.md)
- [gNB RRC](./RRC/rrc-usage.md)
- [E1 design](./E1AP/E1-design.md)
- [F1 design](./F1AP/F1-design.md)
- [GTP-U design](./GTP/gtp-design.md)
- [NR nFAPI](./NR_NFAPI_archi.md): how NR nFAPI works
- [NRPPa call flow](./NRPPA/NRPPA-call-flow.md)
- [UE 5G NAS](./5Gnas.md)
- [Analog beamforming](./analog_beamforming.md)
- [UL MIMO](./UL_MIMO.md)

## Building and running from images

- [Building images](../docker/README.md)
- [5G with the RFsimulator](../ci-scripts/yaml_files/5g_rfsimulator/README.md)
- [4G with the RFsimulator](../ci-scripts/yaml_files/4g_rfsimulator_fdd_05MHz/README.md)
- [Physical simulators in OpenShift](../openshift/README.md)

## Libraries

### General

- [T tracer](../common/utils/T/DOC/T.md): generic tracing tool (VCD, Wireshark,
  GUI, recording for later analysis)
- [OPT](../openair2/UTIL/OPT/README.txt): tracing to Wireshark
- [Configuration module](../common/config/DOC/config.md)
- [Logging module](../common/utils/LOG/DOC/log.md)
- [Shared object loader](../common/utils/DOC/loader.md)
- [Thread pool](../common/utils/threadPool/thread-pool.md): used in L1
- [LDPC implementation](../openair1/PHY/CODING/DOC/LDPCImplementation.md): built as a shared library
- [Time management](./time_management.md)

### Radios

Radio drivers under `radio/` with their own documentation. The other SDRs
(AW2S, LimeSDR, ...) have none.

- [RFsimulator](../radio/rfsimulator/README.md)
- [USRP](../radio/USRP/README.md)
- [BladeRF](../radio/BLADERF/README.md)
- [I/Q player](../radio/iqplayer/DOC/iqrecordplayer_usage.md): driver usage
- [I/Q record and replay](./iqrecordplayer_usage.md): general documentation
- [O-RAN 7.2 fronthaul driver (fhi_72)](../radio/fhi_72/README.md)
- [vrtsim](../radio/vrtsim/README.md): shared memory radio interface
- [RF emulator](../radio/emulator/README.md)
- [ZeroMQ (zmq)](../radio/zmq/README.md)

### Special-purpose libraries

- [Scopes](../openair1/PHY/TOOLS/readme.md): xForms and imgui based scopes
- [Telnet server](../common/utils/telnetsrv/DOC/telnethelp.md): monitoring and control
- [Web server](../common/utils/websrv/DOC/websrv.md)

## Testing

- [Unit tests](./UnitTests.md): unit testing setup
- Component tests (in `tests/`):
    - [CU-UP tester](../tests/nr-cuup/README.md)
    - [CU-NRPPa tester](../tests/nr-cu-nrppa/README.md)
    - [UE NAS tester](../tests/nr-ue-nas-simulator/README.md)
- [Test benches](./TESTBenches.md): CI setup and links to pipelines
- [CI framework](../ci-scripts/README.md): custom framework to run end-to-end tests

## Developer tools

- [Contribution guidelines](./code-style-contrib.md): working practices, code style and review process
- [Git guide](./git-guide.md): commit signing, branch management, submodules,
  recovering from mistakes, reusing conflict resolutions (rerere)
- [Cross-compilation](./cross-compile.md): cross-compiling OAI for ARM
- [clang-format](./clang-format.md): code formatting
- [Formatting check](../tools/formatting/README.md): detects clang-format errors
- [cppcheck](../tools/cppcheck/README.md): static code analysis
- [Sanitizers](./dev_tools/sanitizers.md): running with ASan, UBSan, MSan and TSan
- [include-what-you-use (iwyu)](../tools/iwyu/README.md): detects `#include` errors
- [Docker development environment](../tools/docker-dev-env/README.md): Ubuntu 24 based
- [Performance monitoring](./dev_tools/performance_monitoring.md): tools to monitor the computing performance of OAI
- [Documentation best practices](./doc_best_practices.md)
