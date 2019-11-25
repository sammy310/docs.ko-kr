---
title: '방법: XML 파일에서 개체 데이터 읽기'
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: c997af4729a24a6b5bd5b22d0153860cff3282d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346431"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>How to: Read Object Data from an XML File (Visual Basic)
이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽습니다.  
  
## <a name="example"></a>예제  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 파일 이름 "c:\temp\SerializationOverview.xml"을 serialize된 데이터가 포함된 파일 이름으로 바꿉니다. For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
 클래스에는 매개 변수가 없는 public 생성자가 있어야 합니다.  
  
 public 속성과 필드만 역직렬화됩니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
- serialize되는 클래스에 매개 변수가 없는 public 생성자가 없는 경우  
  
- 파일의 데이터가 역직렬화할 클래스의 데이터를 나타내지 않는 경우  
  
- 파일이 없는 경우(<xref:System.IO.IOException>)  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 항상 입력을 확인하고, 신뢰할 수 없는 소스의 데이터를 역직렬화하지 마세요. 다시 생성된 개체는 역직렬화한 코드의 사용 권한으로 로컬 컴퓨터에서 실행됩니다. 애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.IO.StreamWriter>
- [방법: XML 파일에 개체 데이터 쓰기(Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
- [Serialization(Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)
