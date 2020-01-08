---
title: XmlSerializer를 사용 하 여 개체를 deserialize 하는 방법
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: c24ba466a208fe5abdbf565169c41c4ee3f47482
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559900"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a><span data-ttu-id="2ab59-102">XmlSerializer를 사용 하 여 개체를 deserialize 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2ab59-102">How to deserialize an object using XmlSerializer</span></span>

<span data-ttu-id="2ab59-103">개체를 역직렬화할 때는 전송 형식에 따라 스트림을 만들지 파일 개체를 만들지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab59-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="2ab59-104">전송 형식이 결정된 뒤에는 필요에 따라 <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 또는 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab59-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>

## <a name="to-deserialize-an-object"></a><span data-ttu-id="2ab59-105">개체를 역직렬화하려면</span><span class="sxs-lookup"><span data-stu-id="2ab59-105">To deserialize an object</span></span>

1. <span data-ttu-id="2ab59-106">역직렬화할 개체의 형식을 사용하여 <xref:System.Xml.Serialization.XmlSerializer>를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab59-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>

1. <span data-ttu-id="2ab59-107">개체의 복제본을 생성할 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab59-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="2ab59-108">Deserialize 할 때 다음 예제와 같이 반환 된 개체를 원래 형식으로 캐스팅 해야 합니다 .이 예제에서는 파일에서 개체를 deserialize 합니다 (스트림에서 deserialize 할 수도 있지만).</span><span class="sxs-lookup"><span data-stu-id="2ab59-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>

    ```vb
    ' Construct an instance of the XmlSerializer with the type
    ' of object that is being deserialized.
    Dim mySerializer As New XmlSerializer(GetType(MySerializableClass))
    ' To read the file, create a FileStream.
    Dim myFileStream As New FileStream("myFileName.xml", FileMode.Open)
    ' Call the Deserialize method and cast to the object type.
    Dim myObject = CType( _
    mySerializer.Deserialize(myFileStream), MySerializableClass)
    ```

    ```csharp
    // Construct an instance of the XmlSerializer with the type
    // of object that is being deserialized.
    var mySerializer = new XmlSerializer(typeof(MySerializableClass));
    // To read the file, create a FileStream.
    var myFileStream = new FileStream("myFileName.xml", FileMode.Open);
    // Call the Deserialize method and cast to the object type.
    var myObject = (MySerializableClass) mySerializer.Deserialize(myFileStream)
    ```

## <a name="see-also"></a><span data-ttu-id="2ab59-109">참조</span><span class="sxs-lookup"><span data-stu-id="2ab59-109">See also</span></span>

- [<span data-ttu-id="2ab59-110">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="2ab59-110">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="2ab59-111">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="2ab59-111">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
