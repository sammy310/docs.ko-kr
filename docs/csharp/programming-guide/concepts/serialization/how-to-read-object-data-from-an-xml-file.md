---
title: XML 파일에서 개체 데이터를 읽는 방법(C#)
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 2da5919c11ed2d6e43f4f9fc406f43e3ed48060f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346429"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="1b8c1-102">XML 파일에서 개체 데이터를 읽는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="1b8c1-102">How to read object data from an XML file (C#)</span></span>
<span data-ttu-id="1b8c1-103">이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b8c1-104">예제</span><span class="sxs-lookup"><span data-stu-id="1b8c1-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="1b8c1-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1b8c1-105">Compiling the Code</span></span>  
<span data-ttu-id="1b8c1-106">파일 이름 "c:\temp\SerializationOverview.xml"을 serialize된 데이터가 포함된 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="1b8c1-107">데이터를 직렬화하는 작업에 대한 자세한 내용은 [XML 파일에 개체 데이터를 쓰는 방법(C#)](./how-to-write-object-data-to-an-xml-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-107">For more information about serializing data, see [How to write object data to an XML file (C#)](./how-to-write-object-data-to-an-xml-file.md).</span></span>
  
 <span data-ttu-id="1b8c1-108">클래스에는 매개 변수가 없는 public 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="1b8c1-109">public 속성과 필드만 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1b8c1-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1b8c1-110">Robust Programming</span></span>  
 <span data-ttu-id="1b8c1-111">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="1b8c1-112">serialize되는 클래스에 매개 변수가 없는 public 생성자가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="1b8c1-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="1b8c1-113">파일의 데이터가 역직렬화할 클래스의 데이터를 나타내지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="1b8c1-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="1b8c1-114">파일이 없는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="1b8c1-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1b8c1-115">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="1b8c1-115">.NET Framework Security</span></span>  
 <span data-ttu-id="1b8c1-116">항상 입력을 확인하고, 신뢰할 수 없는 소스의 데이터를 역직렬화하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="1b8c1-117">다시 생성된 개체는 역직렬화한 코드의 사용 권한으로 로컬 컴퓨터에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="1b8c1-118">애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8c1-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8c1-119">참조</span><span class="sxs-lookup"><span data-stu-id="1b8c1-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="1b8c1-120">XML 파일에 개체 데이터를 쓰는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="1b8c1-120">How to write object data to an XML file (C#)</span></span>](./how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="1b8c1-121">Serialization(C#)</span><span class="sxs-lookup"><span data-stu-id="1b8c1-121">Serialization (C#)</span></span>](./index.md)
- [<span data-ttu-id="1b8c1-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1b8c1-122">C# Programming Guide</span></span>](../../index.md)
