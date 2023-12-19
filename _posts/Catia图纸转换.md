##Catia图纸转换
#安装Python及转换插件
[https://github.com/evereux/pycatia](https://github.com/evereux/pycatia "链接地址")

```

    #! /usr/bin/python3.9



    Example - Document - 003

    Description:
        Opens a CATIA fila and exports it as STEP. Then closes the file.

    Requirements:
        - CATIA running.
        - Tests already setup.


import os
from pathlib import Path

from pycatia import catia
from pycatia.in_interfaces.document import Document

# path to file to open.
def export_stp(inputFile,outputFile):
    caa = catia()
    # open document
    documents = caa.documents
    documents.open(inputFile)

    document = caa.active_document

    # to export to another support file_format (license permitting).
    new_export_file_name = Path(outputFile)
    document.export_data(new_export_file_name, 'stp', overwrite=True)

    # close document
    document.close()

if ( __name__ == '__main__' )  or  ( __name__ == 'main' ) :
    inputFile = sys.argv[1];
    outputFile = sys.argv[2];
    print("inputFile="+inputFile);
    print("outputFile="+outputFile);
    export_stp(inputFile,outputFile);

```
#将py文件打包成
