---
title: XML 파일에 개체 데이터를 쓰는 방법(C#)
description: 이 C# 예제에서는 XmlSerializer 클래스를 사용하여 클래스의 개체를 XML 파일에 씁니다. 코드를 컴파일하는 방법을 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: c88a85f8bc65a195f404dab6aa39675bac7e4f84
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303129"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="6e3a3-104">XML 파일에 개체 데이터를 쓰는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="6e3a3-104">How to write object data to an XML file (C#)</span></span>
<span data-ttu-id="6e3a3-105">이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 XML 파일에 클래스의 개체를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a3-105">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e3a3-106">예제</span><span class="sxs-lookup"><span data-stu-id="6e3a3-106">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e3a3-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6e3a3-107">Compiling the Code</span></span>  
 <span data-ttu-id="6e3a3-108">직렬화되는 클래스에는 매개 변수가 없는 공용 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a3-108">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6e3a3-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6e3a3-109">Robust Programming</span></span>  
 <span data-ttu-id="6e3a3-110">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a3-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="6e3a3-111">serialize되는 클래스에 매개 변수가 없는 public 생성자가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="6e3a3-111">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="6e3a3-112">파일이 있지만 읽기 전용인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="6e3a3-112">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="6e3a3-113">경로가 너무 긴 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="6e3a3-113">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="6e3a3-114">디스크가 꽉 찬 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="6e3a3-114">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="6e3a3-115">.NET 보안</span><span class="sxs-lookup"><span data-stu-id="6e3a3-115">.NET Security</span></span>  
 <span data-ttu-id="6e3a3-116">이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a3-116">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="6e3a3-117">애플리케이션에서 파일을 만들어야 하는 경우 해당 애플리케이션에 폴더에 대한 `Create` 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a3-117">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="6e3a3-118">파일이 이미 있는 경우 애플리케이션에 더 낮은 권한인 `Write` 권한만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a3-118">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="6e3a3-119">가능한 경우 배포하는 동안 파일을 만들고, 폴더에 대한 `Create` 권한 대신 단일 파일에 대해 `Read` 권한만 부여하는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="6e3a3-119">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3a3-120">참조</span><span class="sxs-lookup"><span data-stu-id="6e3a3-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="6e3a3-121">XML 파일에서 개체 데이터를 읽는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="6e3a3-121">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="6e3a3-122">Serialization(C#)</span><span class="sxs-lookup"><span data-stu-id="6e3a3-122">Serialization (C#)</span></span>](./index.md)
