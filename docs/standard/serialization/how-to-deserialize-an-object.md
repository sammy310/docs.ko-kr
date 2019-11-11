---
title: '방법: 개체 deserialize'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: e1a960d39319beee1c3c257fcd3ade207de11010
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881134"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="c347d-102">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="c347d-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="c347d-103">개체를 deserialize할 때는 전송 형식에 따라 스트림을 만들지 파일 개체를 만들지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c347d-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="c347d-104">전송 형식이 결정된 뒤에는 필요에 따라 <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 또는 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347d-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="c347d-105">개체를 deserialize하려면</span><span class="sxs-lookup"><span data-stu-id="c347d-105">To deserialize an object</span></span>  
  
1. <span data-ttu-id="c347d-106">deserialize할 개체의 형식을 사용하여 <xref:System.Xml.Serialization.XmlSerializer>를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c347d-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2. <span data-ttu-id="c347d-107">개체의 복제본을 생성할 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c347d-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="c347d-108">를 역직렬화 하는 경우 (하지만 해당 스트림에서 deserialize 할 수도) 파일에서 개체를 deserialize 하는 다음 예제와 같이 원래 형식으로 반환된 된 개체를 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347d-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c347d-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="c347d-109">See also</span></span>

- [<span data-ttu-id="c347d-110">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="c347d-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="c347d-111">방법: 개체 serialize</span><span class="sxs-lookup"><span data-stu-id="c347d-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
