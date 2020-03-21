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
# <a name="datacontractjsonserializer-sample"></a><span data-ttu-id="a7327-102">데이터계약Json 직렬화기 샘플</span><span class="sxs-lookup"><span data-stu-id="a7327-102">DataContractJsonSerializer sample</span></span>

> [!NOTE]
> <span data-ttu-id="a7327-103">이 샘플은 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-103">This sample is for <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="a7327-104">JSON을 직렬화하고 역직해제하는 대부분의 시나리오의 경우 [System.Text.Json 네임스페이스의](../../../standard/serialization/system-text-json-overview.md)API를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-104">For most scenarios that involve serializing and deserializing JSON, we recommend the APIs in the [System.Text.Json namespace](../../../standard/serialization/system-text-json-overview.md).</span></span>

<span data-ttu-id="a7327-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 <xref:System.Runtime.Serialization.DataContractSerializer>와 동일한 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="a7327-106">JSON 데이터 형식은 AJAX(Asynchronous JavaScript and XML) 스타일 웹 애플리케이션을 작성하는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="a7327-107">WCF(Windows 통신 재단)의 AJAX 지원은 스크립트 관리자 컨트롤을 통해 ASP.NET AJAX와 함께 사용하도록 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-107">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="a7327-108">ASP.NET AJAX와 Windows 통신 재단(WCF)을 사용하는 방법의 예는 [AJAX 샘플을](ajax.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7327-108">For examples of how to use Windows Communication Foundation (WCF) with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
<span data-ttu-id="a7327-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
<span data-ttu-id="a7327-110">샘플에서는 `Person` 데이터 계약을 사용하여 serialization 및 deserialization을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

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

 <span data-ttu-id="a7327-111">`Person` 형식의 인스턴스를 JSON으로 serialize하려면 먼저 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 만들고 `WriteObject` 메서드를 사용하여 스트림에 JSON 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="a7327-112">메모리 스트림에는 유효한 JSON 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-112">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="a7327-113">샘플에서는 JSON 데이터에서 개체로의 역직렬화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="a7327-114">그 후에 스트림을 되감고 `ReadObject`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-114">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="a7327-115">`p2` 개체를 확인하면 JSON 데이터가 올바르게 역직렬화된 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a7327-116">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a7327-117">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a7327-117">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a7327-118">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a7327-119">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-119">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a7327-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a7327-120">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="a7327-121">Windows 통신 기초 샘플 빌드에 설명된 대로 솔루션 JsonSerialization.sln을 [빌드합니다.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="a7327-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="a7327-122">결과 콘솔 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7327-122">Run the resulting console application.</span></span>  
