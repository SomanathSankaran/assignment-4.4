# assignment-4.4

 QN 1 Write a Java program to copy a file from HDFS to LFS
 I have used the copytolocal method of Filesystem which take Source path and destination path as its  parameters which is taken from arguments (image:copytolocal)
 output :1.I Have removed the file "COPYFILE" by using -rm from local system and then checked it by listing thef files 
2.then executed my jar file "Hadoop jar copytolocal.jar" and then listed the localsystem by -ls and now my copyfile.txt is copied there

QN 2 Explain the importance and usage of the below terms in details
● DFSInputStream
● DFSOutputStream
● FSDataInputStream
● FSDataOutputStream


FSDataInputStream
• Provides stream (channel) for reading data.
FSDataInputStream wraps the DataInputStream and implements Seekable, PositionedReadable interfaces which provide method like getPos(), seek() method to provide Random Access on HDFS file.
seek() method seek the file to the given offset from the start of the file so that read () will stream from that location whereas getPos() method will return the current position on the InputStream.
Below sample code uses seek (), getPos () and read() method
FSDataInputStream also implements PositionedReadable, which provide read, & readFully method to read part of file content from seek position as mentioned below
read(long position, byte[] buffer, int offset, int length)
DFSInputStream
• Handles communication of the namenode with various datanodes.
• Handles integrity of data contained by the blocks.
• Manages data read activity in case of datanode failure.
• Called internally by FSDataInputStream.
FSDataOutputStream
• Provides stream (channel) for writing data.
Filesystem’s create () method return FSDataOutputStream, which use to create new HDFS file or write the content at the EOF. It doesn’t provide seek because of HDFS limitation to write to content at the EOF only. It wrap Java IO’s DataOutputStream and add method such as getPos() to get the position of the file and write() to write the content at the last position.
DFSOutputStream
• Handles communication of the namenode with various datanodes.
• Called internally by FSDataOutputStream.
