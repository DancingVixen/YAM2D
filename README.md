# GNU-Radio-LRPT-Decoder

This flowgraph is designed for the rtlsdr using GNU radio 3.7.X This has not been tested on an older version and there is no guarantee that it will work. However it should be fairly easy to modify this to work with almost any SDR.

This GNU Radio flow graph provides a real time LRPT Soft-Decision Receiver and Decoder.

The current flowgraph will use 2.4msps mode to prevent lost samples and uses less CPU power. 

# Usage:

1. Load one of the GRC Flowgraph. 

2. Find the Variable block with the label "bitstream_name" and select a location where you want the decoded .s file to be located.

3. Change "/home/user/LRPT" to the directory of your choice. 

4. Execute the flowgraph.

Once the flowgraph has been executed you should see the following:

One of the tabs shows the 137.9 Mhz band FFT graph, The second tab shows a constellation graph of the demodulated bitstream, there should be 4 clusters. The sliders allow you to manually lok on to the QPSK signal but default values should work fine. 

The Flowgraph will continue to write the demodulated soft bits into the ".s" file in your chosen location until you manually stop it. 

When there is no satellite in range the FFT graph will be relatively flat and there will be no noticable patterns in the QPSK constellation graph. 

Once the pass is done, stop the flowgraph and put the .s file into the AMIGOS decoder using the button labeled "72k"

#Test Files

Below are some demodulated files using this GNU radio flowgraph to prove it works. You can also use these 72k .s files to test the AMIGOS decoder.

Google Drive: https://drive.google.com/file/d/1-l3UAdCk58eSImAZAYOuX8TPeLs8ou0y/view

Mega: https://mega.nz/#!S5d0WaRC!urYXNNpImruKyuOAtymZjvab9i9aDiN5gPwEmq3y9_8

Based flowgraph from https://github.com/argilo/sdr-examples
