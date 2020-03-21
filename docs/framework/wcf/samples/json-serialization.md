---
title: 데이터계약Json 직렬화기 샘플
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: d3456582d73640f1802c17d7f29f4931a6f920b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144632"
---
# <a name="datacontractjsonserializer-sample"></a>데이터계약Json 직렬화기 샘플

> [!NOTE]
> 이 샘플은 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>에 대한 것입니다. JSON을 직렬화하고 역직해제하는 대부분의 시나리오의 경우 [System.Text.Json 네임스페이스의](../../../standard/serialization/system-text-json-overview.md)API를 사용하는 것이 좋습니다.

<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 <xref:System.Runtime.Serialization.DataContractSerializer>와 동일한 형식을 지원합니다. JSON 데이터 형식은 AJAX(Asynchronous JavaScript and XML) 스타일 웹 애플리케이션을 작성하는 경우에 특히 유용합니다. WCF(Windows 통신 재단)의 AJAX 지원은 스크립트 관리자 컨트롤을 통해 ASP.NET AJAX와 함께 사용하도록 최적화되어 있습니다. ASP.NET AJAX와 Windows 통신 재단(WCF)을 사용하는 방법의 예는 [AJAX 샘플을](ajax.md)참조하십시오.  
  
이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
샘플에서는 `Person` 데이터 계약을 사용하여 serialization 및 deserialization을 보여 줍니다.  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 `Person` 형식의 인스턴스를 JSON으로 serialize하려면 먼저 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 만들고 `WriteObject` 메서드를 사용하여 스트림에 JSON 데이터를 기록합니다.  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 메모리 스트림에는 유효한 JSON 데이터가 포함되어 있습니다.
  
```json  
{"age":42,"name":"John"}  
```  
  
 샘플에서는 JSON 데이터에서 개체로의 역직렬화를 보여 줍니다. 그 후에 스트림을 되감고 `ReadObject`를 호출합니다.  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 `p2` 개체를 확인하면 JSON 데이터가 올바르게 역직렬화된 것을 알 수 있습니다.  
  
> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1. Windows 통신 기초 샘플 빌드에 설명된 대로 솔루션 JsonSerialization.sln을 [빌드합니다.](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2. 결과 콘솔 애플리케이션을 실행합니다.  
