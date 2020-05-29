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
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a>XmlSerializer를 사용하여 개체를 역직렬화하는 방법

개체를 역직렬화할 때는 전송 형식에 따라 스트림을 만들지 파일 개체를 만들지 여부가 결정됩니다. 전송 형식이 결정된 뒤에는 필요에 따라 <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 또는 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출할 수 있습니다.

## <a name="to-deserialize-an-object"></a>개체를 역직렬화하려면

1. 역직렬화할 개체의 형식을 사용하여 <xref:System.Xml.Serialization.XmlSerializer>를 생성합니다.

1. 개체의 복제본을 생성할 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출합니다. 역직렬화할 때는 개체에서 파일을 역직렬화(스트림에서 역직렬화할 수도 있음)하는 다음 예제와 같이 반환된 개체를 원래의 형식으로 캐스팅해야 합니다.

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

## <a name="see-also"></a>참조

- [XML serialization 소개](introducing-xml-serialization.md)
- [방법: 개체 직렬화](how-to-serialize-an-object.md)
