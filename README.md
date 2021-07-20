\documentclass[journal, 12pt]{IEEEtran}

\onecolumn
\usepackage{amsfonts}
\usepackage{amsmath}
\usepackage{array}
\usepackage{bm}
\usepackage{caption}
\usepackage{color}
\usepackage{diagbox}
\usepackage{float}
\usepackage{graphicx}
\usepackage{lineno}
\usepackage{mathrsfs}
\usepackage{multirow}
\usepackage{setspace}
\usepackage{stfloats}\usepackage[lined,boxed,commentsnumbered, ruled]{algorithm2e}


\DeclareMathOperator*{\argmax}{\argmin}
\hyphenation{op-tical net-works semi-conduc-tor}

\doublespacing

\begin{document}
	

\title{The Analysis of the Structure, Reproducibility and Replicability of 'Seamless WiFi Backscater Communication'}

\author{Jiahao Ren \\
	 College of Control Science and Engineering\\
	 China University of Petroleum (East China), Qingdao 266580, China\\ 
	 renjiahao20@163.com}

\maketitle
\onehalfspacing
\section{Structure}
First of all, in the abstract, the author briefly introduces the main innovative contributions of the background scattering communication technology, and summarizes the performance improvement of the technology compared with the previous technology. In the first part of the text, the introduction introduces the contributions of predecessors in detail, and lists the advantages and disadvantages of the previous technology, then leads to their own innovation points, and introduces in detail the aspects of innovation. In the second part, the background part introduces the relevant communication technology principles involved in the background scattering in detail. The third part, the design summary part is a detailed introduction of the author's specific improvement work on the existing technology. In the fourth part, the author analyzes the feasibility of the subject and makes an experimental exploration. In the fifth part, the main synchronization problems are analyzed and studied, which proves the feasibility of synchronization in theory. The sixth part is to explore other non core issues in the subject, to ensure the integrity of issues related to the subject. In the seventh part, the hardware and software are designed. Finally, experiments are carried out to verify the excellent performance of the proposed background scattering technique.
\section{Reproducibility and Replicability}
WiFi backscatter communication has the potential to enable battery-free sensors which can transmit data using a WiFi network. In order for WiFi backscatter systems to be practical they should be compatible with existing WiFi networks without any hardware or software modifications. Moreover, they should work with networks that use encryption. In this paper, we present WiTAG which achieves these requirements, making the implementation and deployment of WiFi backscatter communication more practical. In contrast with existing systems which utilize the physical layer for backscatter communication, we take a different approach by leveraging features of the MAC layer to communicate. WiTAG is designed to send data by selectively interfering with subframes (MPDUs) in an aggregated frame (A-MPDU). This enables standard compliant communication using modern, open or encrypted 802.11n and 802.11ac networks without requiring hardware or software modifications to any devices. We implement WiTAG using of-the-shelf components and evaluate its performance in line-of-sight and non-line-of-sight scenarios. We show that WiTAG achieves a throughput of up to 4 Kbps without impacting other devices in the network.
\subparagraph{}
There are two key innovations in this paper：
\subparagraph{}
1) MAC-Layer Backscatter Communication: WiTAG introduces a new backscatter communication mechanism which utilizes MAC-layer “frame aggregation” available in 802.11n and 802.11ac standards. These standards place multiple MAC-layer data units (subframes) in a large PHY-layer packet (aggregated frame) to improve throughput, as shown in Figure 1. In WiTAG, a WiFi device sends an aggregated frame to an AP in the network using a physical rate that is likely to be successfully received. This frame acts as a query for the tag (e.g., IoT sensor). The tag embeds its data into the aggregated frame by selectively corrupting some subframes. Then, the AP sends a block ACK back to the transmitting WiFi device, indicating which subframes have or have not been successfully received. The WiFi device extracts the data being communicated by the tag from the bits in the block ACK. Subframes that are not corrupted by the tag are received successfully (represented by a 1 in the block ACK) and those that are corrupted are not received successfully (represented by a 0 in the block ACK).
\subparagraph{}
2) Passive Subframe Corrupting: WiTAG’s second innovation is a technique to passively corrupt subframes. Note that an active radio which has a transmitter can easily corrupt a subframe by transmitting an interfering signal. However, a backscatter tag is a passive device and does not have a transmitter. To solve this problem, we design a backscatter tag which can modify the wireless channel during the transmission of a subframe, hence corrupting that subframe. Because frame aggregation performs channel estimation only once at the beginning of the aggregated frame, modifying the channel during the transmission of a subframe corrupts the subframe, therefore, it cannot be decoded.
\subsection{Reproducibility}
Research shows that the main reason why the research results can not be reproduced is that we can not find the correct data or computer code to draw the original conclusion, or the code lacks key functions, or some variables in the data. 
\subparagraph{}
In this paper, the author has done a lot of experiments around these two core innovation points, and basically introduced the experimental conditions and experimental process, but the introduction is not detailed. This situation mainly exists in the hardware and software design: first, the author designed a circuit board that meets the experimental requirements, although the author explained that the circuit board (Figure 1) is simple in design and does not have confidentiality. However, it does not provide the design requirements and circuit diagram of the circuit board, which makes it very difficult for us to reproduce the experiments conducted by the author and obtain similar experimental data.
\subparagraph{}
On the other hand, the author to implement WiTAG, the author have developed a C program that runs on a WiFi device that generates query packets. We have made no changes to the hardware or driver of the WiFi device. The WiTAG software has two main components: 1) a query packet generator and 2) the tag’s message tracker and decoder. In our implementation, these two components are executed in two separate threads. However, the author has not been able to provide specific source code. If we write our own code, it will inevitably be different from the author's idea, so it is difficult to achieve the same effect as the author's experiment, and it will eventually affect the reproduction of the experiment.
\subsection{Replicability}
Replicability is faced with the same problem, the author did not provide enough detailed process to complete the replication, so it is relatively difficult to complete the replication experiment.
\subparagraph{}
Reproducibility of scientific research results is an effective way to test the accuracy of scientific research results. For example, in the field of life sciences, reproducible results mean that similar studies are conducted by research groups in different laboratories with similar experimental designs, and the final results should be roughly the same. However, as more and more papers are published, the reappearance crisis has gradually attracted people's attention. According to the results of a questionnaire published by Nature magazine, 70\% of the respondents said that they had been unable to reproduce other people's research results. If so many research results can not be reproduced, it is a great waste of scientific research resources.

The source code of this article is available at: https://github.com/MasonRen/R-R.git.


\end{document}
