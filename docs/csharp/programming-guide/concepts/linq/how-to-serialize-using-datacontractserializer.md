---
title: DataContractSerializer를 사용하여 직렬화하는 방법(C#)
description: DataContractSerializer를 사용하여 개체를 직렬화하는 방법을 알아봅니다. 개체를 만들고 텍스트 파일로 직렬화한 다음 역직렬화하는 예제를 살펴봅니다.
ms.date: 07/20/2015
ms.assetid: 3320ecbf-cdbe-480e-979c-2c14bbef9988
ms.openlocfilehash: b713f36cde594f7cd7011073345d33c6f46585e0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301530"
---
# <a name="how-to-serialize-using-datacontractserializer-c"></a><span data-ttu-id="292e7-104">DataContractSerializer를 사용하여 직렬화하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="292e7-104">How to serialize using DataContractSerializer (C#)</span></span>
<span data-ttu-id="292e7-105">이 항목에서는 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 직렬화하고 역직렬화하는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="292e7-105">This topic shows an example that serializes and deserializes using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="292e7-106">예제</span><span class="sxs-lookup"><span data-stu-id="292e7-106">Example</span></span>  
 <span data-ttu-id="292e7-107">다음 예제에서는 <xref:System.Xml.Linq.XElement> 개체가 포함된 많은 개체를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="292e7-107">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="292e7-108">텍스트 파일로 개체를 직렬화하고 텍스트 파일에서 개체를 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="292e7-108">It then serializes them to text files, and then deserializes them from the text files.</span></span>  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Linq;  
using System.IO;  
using System.Runtime.Serialization;  
  
public class XLinqTest  
{  
    public static void Main()  
    {  
        Test<XElement>(CreateXElement());  
        Test<XElementContainer>(new XElementContainer());  
        Test<XElementNullContainer>(new XElementNullContainer());  
    }  
  
    public static void Test<T>(T obj)  
    {  
        DataContractSerializer s = new DataContractSerializer(typeof(T));  
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Create))  
        {  
            Console.WriteLine("Testing for type: {0}", typeof(T));
            s.WriteObject(fs, obj);  
        }  
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Open))  
        {  
            object s2 = s.ReadObject(fs);  
            if (s2 == null)  
                Console.WriteLine("  Deserialized object is null (Nothing in VB)");  
            else  
                Console.WriteLine("  Deserialized type: {0}", s2.GetType());  
        }  
    }  
  
    public static XElement CreateXElement()  
    {  
        return new XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"));  
    }  
}  
  
[DataContract]  
public class XElementContainer  
{  
    [DataMember]  
    public XElement member;  
  
    public XElementContainer()  
    {  
        member = XLinqTest.CreateXElement();  
    }  
}  
  
[DataContract]  
public class XElementNullContainer  
{  
    [DataMember]  
    public XElement member;  
  
    public XElementNullContainer()  
    {  
        member = null;  
    }  
}  
```  
  
 <span data-ttu-id="292e7-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="292e7-109">This example produces the following output:</span></span>  
  
```output  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
```  
