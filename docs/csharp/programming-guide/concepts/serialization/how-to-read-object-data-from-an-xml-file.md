---
title: XML 파일에서 개체 데이터를 읽는 방법(C#)
description: 이 C# 예제에서는 XmlSerializer 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽습니다.
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 8d607424201cfad08df1c5ffbfb66a114b31886d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178764"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a>XML 파일에서 개체 데이터를 읽는 방법(C#)

이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽습니다.  
  
## <a name="example"></a>예제  
  
```csharp  
public class Book  
{  
    public String title;  
}
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  

파일 이름 "c:\temp\SerializationOverview.xml"을 serialize된 데이터가 포함된 파일 이름으로 바꿉니다. 데이터를 직렬화하는 작업에 대한 자세한 내용은 [XML 파일에 개체 데이터를 쓰는 방법(C#)](./how-to-write-object-data-to-an-xml-file.md)을 참조하세요.
  
 클래스에는 매개 변수가 없는 public 생성자가 있어야 합니다.  
  
 public 속성과 필드만 역직렬화됩니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  

 다음 조건에서 예외가 발생합니다.  
  
- serialize되는 클래스에 매개 변수가 없는 public 생성자가 없는 경우  
  
- 파일의 데이터가 역직렬화할 클래스의 데이터를 나타내지 않는 경우  
  
- 파일이 없는 경우(<xref:System.IO.IOException>)  
  
## <a name="net-security"></a>.NET 보안  

 항상 입력을 확인하고, 신뢰할 수 없는 소스의 데이터를 역직렬화하지 마세요. 다시 생성된 개체는 역직렬화한 코드의 사용 권한으로 로컬 컴퓨터에서 실행됩니다. 애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.IO.StreamWriter>
- [XML 파일에 개체 데이터를 쓰는 방법(C#)](./how-to-write-object-data-to-an-xml-file.md)
- [Serialization(C#)](./index.md)
- [C# 프로그래밍 가이드](../../index.md)
