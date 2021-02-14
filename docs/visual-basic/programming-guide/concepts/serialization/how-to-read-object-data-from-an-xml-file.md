---
description: '자세한 정보: 방법: XML 파일에서 개체 데이터 읽기 (Visual Basic)'
title: '방법: XML 파일에서 개체 데이터 읽기'
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: d281997a0dd96ad6263fe03cea84b3e84005a3ad
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486825"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="53168-103">방법: XML 파일에서 개체 데이터 읽기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53168-103">How to: Read Object Data from an XML File (Visual Basic)</span></span>

<span data-ttu-id="53168-104">이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="53168-104">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53168-105">예제</span><span class="sxs-lookup"><span data-stu-id="53168-105">Example</span></span>  
  
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
  
## <a name="compile-the-code"></a><span data-ttu-id="53168-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="53168-106">Compile the code</span></span>  

 <span data-ttu-id="53168-107">파일 이름 "c:\temp\SerializationOverview.xml"을 serialize된 데이터가 포함된 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="53168-107">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="53168-108">데이터를 serialize 하는 방법에 대 한 자세한 내용은 [방법: XML 파일에 개체 데이터 쓰기 (Visual Basic)](how-to-write-object-data-to-an-xml-file.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53168-108">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="53168-109">클래스에는 매개 변수가 없는 public 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53168-109">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="53168-110">public 속성과 필드만 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="53168-110">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="53168-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="53168-111">Robust Programming</span></span>  

 <span data-ttu-id="53168-112">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="53168-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="53168-113">serialize되는 클래스에 매개 변수가 없는 public 생성자가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="53168-113">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="53168-114">파일의 데이터가 역직렬화할 클래스의 데이터를 나타내지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="53168-114">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="53168-115">파일이 없는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="53168-115">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="53168-116">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="53168-116">.NET Framework Security</span></span>  

 <span data-ttu-id="53168-117">항상 입력을 확인하고, 신뢰할 수 없는 소스의 데이터를 역직렬화하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="53168-117">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="53168-118">다시 생성된 개체는 역직렬화한 코드의 사용 권한으로 로컬 컴퓨터에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="53168-118">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="53168-119">애플리케이션에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53168-119">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53168-120">참조</span><span class="sxs-lookup"><span data-stu-id="53168-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="53168-121">방법: XML 파일에 개체 데이터 쓰기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53168-121">How to: Write Object Data to an XML File (Visual Basic)</span></span>](how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="53168-122">Serialization(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53168-122">Serialization (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="53168-123">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="53168-123">Visual Basic Programming Guide</span></span>](../../index.md)
