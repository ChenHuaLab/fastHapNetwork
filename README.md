fastHapNetwork
=========================
a fast and scalable program for constructing haplotype network for large-sample sequence data sets


Description
=========================
* fastHapNetwork is a fast and scalable program for constructing haplotype networks for large samples <br>
* fastHapNetwork can implement the minimum joint network (MJN) and the Templeton-Crandall-Sing (TCS) algorithms <br>
* The implementation in single-thread mode is much faster than the existing softwares <br>
* Furthermore, fastHapNetwork enables multi-threaded mode with good scalability


Quick start guide
========================
    1. download the software and grant execution permissions
       chmod +x fastHapNetwork_linux

    2. run the test data (Example/Test1000.phy.gz) with mjn algorithm
       ./fastHapNetwork_linux mjn -i Example/Test1000.phy.gz -t 8 -o Test1000.graph


Usage
========================
    fastHapNetwork [Options]
    
    Options:
        original_tcs        original TCS algorithm (Clement et al. 2002)
        modified_tcs        optimization of TCS implementated by PopART (Leigh and Bryant, 2015)
        msn                 optimization of MSN implementated by PopART
        mjn                 optimization of MJN implementated by PopART
         

Options
========================

### original_tcs

    usage: fastHapNetwork original_tcs [arguments]

    input:
        -i    input phylip format file
    options:
        -t    (int)thread number(default:8)
        -a    (int)is mark the sites which contains ambiguous base, 1:mask, 0:not(default:0)
        -m    (int)is merge intermediate vertex, 1:merge, 0:not:(default:0)
    output:
        -o    output graph file
            

### modified_tcs

    usage: fastHapNetwork modified_tcs [arguments]
    
    input:
        -i    input phylip format file
    options:
        -t    (int)thread number(default:8)
    output:
        -o    output graph file
            
            
### msn

    usage: fastHapNetwork msn [arguments]
         
    input:
        -i    input phylip format file
    options:
        -e    (int)epsilon(default:0)
    output:
        -o    output graph file
            
            
### mjn

    usage: fastHapNetwork mjn [arguments]
         
    input:
        -i    input phylip format file
    options:
        -t    (int)thread number(default:8)
        -e    (int)epsilon(default:0)
    output:
        -o    output graph file
