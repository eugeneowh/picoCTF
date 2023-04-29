Title: Easy1

Points: 150 points

Source: picoCTF2019 Forensics

![image](https://user-images.githubusercontent.com/91729496/235287674-9035f619-1700-472c-9944-ba2a14435006.png)

Downloading the packet capture, we get a pcap file. lets open it with wireshark and see what we can get out of it. The first bulk of it looks like a DNS resolving sequence.

![image](https://user-images.githubusercontent.com/91729496/235287845-02d01b19-8f5b-4add-bbc8-545858578946.png)

Randomly following a UDP stream:

![image](https://user-images.githubusercontent.com/91729496/235287954-e740ec31-7076-49dd-982a-de92338b9aab.png)

After scrolling through the stream, at stream 6, we find the flag!

![image](https://user-images.githubusercontent.com/91729496/235287978-bae39887-8108-40e3-ba0b-dbf7a22d250d.png)
