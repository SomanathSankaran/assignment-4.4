# assignment-4.4
FSDataInputStream
• Provides stream (channel) for reading data.
DFSInputStream
• Handles communication of the namenode with various datanodes.
• Handles integrity of data contained by the blocks.
• Manages data read activity in case of datanode failure.
• Called internally by FSDataInputStream.
FSDataOutputStream
• Provides stream (channel) for writing data.
DFSOutputStream
• Handles communication of the namenode with various datanodes.
• Called internally by FSDataOutputStream.
