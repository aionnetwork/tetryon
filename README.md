# Tetryon Test-Network

At the Open Application Network (OAN), we've made a serious commitment to develop features into the platform that enable developers in expressing privacy-preserving on-chain computations. As a first step towards that end, we introduce the Tetryon Test-Network, an incubator for prototype implementations of privacy-preserving primitives and applications.  

This initial release of Tetryon enables users to employ on-chain SNARK verification within AVM-smart-contract-systems, by leveraging a [modified ZoKrates toolchain](https://github.com/aionnetwork/zokrates-avm). This is made possible by non-intrusive modifications in the AVM that expose to smart contracts operations over the Alt-Bn 128 elliptical curve. 

## Where's the Code?

This repository will exclusively be used to [distribute releases](https://github.com/aionnetwork/tetryon/releases) for Tetryon test-network-compatible kernels, since components for the Tetryon test-network are currently domicile across several repositories: 

* A modified ZoKrates toolchain is maintained in a [public fork](https://github.com/aionnetwork/zokrates-avm) in the [github.com/aionnetwork](https://github.com/aionnetwork) organization. Modifications to ZoKrates are limited to:
    * Enabling the generation of SNARK verification AVM contracts.
* A modified AVM implementation is maintained in a [public fork](https://github.com/ali-sharif/avm/tree/tetryon) of the AVM project. Modifications to the AVM are limited to: 
    * Implementation of addition, multiplication and pairing operations over the [Alt-Bn 128](https://github.com/aionnetwork/bn128-jni) curve. 
* A modified OAN kernel is maintained on the Java implementation's [tetryon branch](https://github.com/aionnetwork/aion/tree/tetryon). Modifications to the OAN kernel are limited to:
    * Unity hard-fork is disabled for the Tetryon network (Tetryon is a PoW-only network to simplify test-network management)
    * The Alt-Bn 128-enabled AVM is used to process all transaction on the network.
    
 ### Operational Notes: 
 * Only the modified Java kernel released [here](https://github.com/aionnetwork/tetryon/releases) should be used to connect to the Tetryon test network. Please do not attempt to connect to the Tetryon network using the mainline releases for the Rust or Java kernels. 
 * This prototype implementation has only been tested on the following configuration: (AMD64, >Ubuntu 18.04, >JDK10). The implementation is currently Linux platform-dependent (mostly to reduce verification overhead). 
 * Key Tetryon test-network configuration parameters are provided here for reference: 
    * The genesis file for the Tetryon network can found [here](https://github.com/aionnetwork/aion/blob/tetryon/config/tetryon/genesis.json).
    * Tetryon Test-net network ID is `29`.
    * Foundation-maintained seed nodes can be configured as: 
      ```
      <nodes>
        <node>p2p://a5010411-8c7e-496c-9c4e-c89318280274@52.234.132.113:30303</node>
        <node>p2p://772b4219-8669-4f70-ad03-c1fa97376d05@35.228.227.5:30303</node>
      </nodes>
      ```

 ## How Do I Use This?  
 
For starters, you can experiment with the [Tetryon sandbox](https://github.com/aionnetwork/tetryon-bench), which demonstrates how to interact with the various system components from both Java and Javascript environments.
 
With respect to the Tetryon Public Test Network, 
 * The Dashboard for the public network is live at [http://tetryon.theoan.com](http://tetryon.theoan.com). 
 * *Coming Soon*: Documentation and tutorials on Tetryon will soon be made available on our [documentation portal](https://developer.theoan.com/docs/custom-kits).
 * *Coming Soon*: A Coin Faucet will be live soon, to request public test-network coins.
 