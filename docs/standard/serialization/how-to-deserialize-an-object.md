---
title: XmlSerializer를 사용하여 개체를 역직렬화하는 방법
description: 개체를 역직렬화하는 방법을 알아봅니다. 전송 형식은 스트림 또는 파일 개체를 만들지 여부를 결정합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: e08ae0d77539219223650fd3bcbd1bcee4df2739
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379109"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a><span data-ttu-id="437d0-104">XmlSerializer를 사용하여 개체를 역직렬화하는 방법</span><span class="sxs-lookup"><span data-stu-id="437d0-104">How to deserialize an object using XmlSerializer</span></span>

<span data-ttu-id="437d0-105">개체를 역직렬화할 때는 전송 형식에 따라 스트림을 만들지 파일 개체를 만들지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="437d0-105">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="437d0-106">전송 형식이 결정된 뒤에는 필요에 따라 <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 또는 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="437d0-106">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>

## <a name="to-deserialize-an-object"></a><span data-ttu-id="437d0-107">개체를 역직렬화하려면</span><span class="sxs-lookup"><span data-stu-id="437d0-107">To deserialize an object</span></span>

1. <span data-ttu-id="437d0-108">역직렬화할 개체의 형식을 사용하여 <xref:System.Xml.Serialization.XmlSerializer>를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="437d0-108">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>

1. <span data-ttu-id="437d0-109">개체의 복제본을 생성할 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="437d0-109">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="437d0-110">역직렬화할 때는 개체에서 파일을 역직렬화(스트림에서 역직렬화할 수도 있음)하는 다음 예제와 같이 반환된 개체를 원래의 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="437d0-110">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="437d0-111">참조</span><span class="sxs-lookup"><span data-stu-id="437d0-111">See also</span></span>

- [<span data-ttu-id="437d0-112">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="437d0-112">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="437d0-113">방법: 개체 직렬화</span><span class="sxs-lookup"><span data-stu-id="437d0-113">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
