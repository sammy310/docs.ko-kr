---
description: '자세한 정보: 피드 포맷터 (JSON)'
title: 피드 포맷터(JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: 124b0fbf81af2a3f548431f98f6a5d695d737074
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752342"
---
# <a name="feed-formatter-json"></a><span data-ttu-id="453a5-103">피드 포맷터(JSON)</span><span class="sxs-lookup"><span data-stu-id="453a5-103">Feed Formatter (JSON)</span></span>

<span data-ttu-id="453a5-104">이 샘플에서는 사용자 지정 <xref:System.ServiceModel.Syndication.SyndicationFeed> 및 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>를 사용하여 JSON(JavaScript Object Notation) 형식으로 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 클래스의 인스턴스를 serialize하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-104">This sample shows how to serialize an instance of a <xref:System.ServiceModel.Syndication.SyndicationFeed> class in JavaScript Object Notation (JSON) format by using a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> and the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="architecture-of-the-sample"></a><span data-ttu-id="453a5-105">샘플 아키텍처</span><span class="sxs-lookup"><span data-stu-id="453a5-105">Architecture of the Sample</span></span>  

 <span data-ttu-id="453a5-106">이 샘플에서는 `JsonFeedFormatter`에서 상속되는 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>라는 클래스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-106">The sample implements a class named `JsonFeedFormatter` that inherits from <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="453a5-107">`JsonFeedFormatter` 클래스는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 JSON 형식으로 데이터를 읽고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-107">The `JsonFeedFormatter` class relies on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to read and write the data in JSON format.</span></span> <span data-ttu-id="453a5-108">내부적으로 포맷터는 `JsonSyndicationFeed`와 `JsonSyndicationItem`이라는 데이터 계약 형식의 사용자 지정 집합을 사용하여 serializer에 의해 생성되는 JSON 데이터의 형식을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-108">Internally, the formatter uses a custom set of data contract types named `JsonSyndicationFeed` and `JsonSyndicationItem` to control the format of the JSON data produced by the serializer.</span></span> <span data-ttu-id="453a5-109">이러한 구현 정보는 최종 사용자에게 표시되지 않으므로 표준 <xref:System.ServiceModel.Syndication.SyndicationFeed> 및 <xref:System.ServiceModel.Syndication.SyndicationItem> 클래스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-109">These implementation details are hidden from the end user, allowing calls to be made against the standard <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> classes.</span></span>  
  
## <a name="writing-json-feeds"></a><span data-ttu-id="453a5-110">JSON 피드 쓰기</span><span class="sxs-lookup"><span data-stu-id="453a5-110">Writing JSON feeds</span></span>  

 <span data-ttu-id="453a5-111">다음 샘플 코드와 같이 이 샘플에 구현된 `JsonFeedFormatter`를 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>와 함께 사용하여 JSON 피드를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-111">Writing a JSON feed can be accomplished by using the `JsonFeedFormatter` (implemented in this sample) with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> as shown in the following sample code.</span></span>  
  
```csharp  
//Basic feed with sample data  
SyndicationFeed feed = new SyndicationFeed("Custom JSON feed", "A Syndication extensibility sample", null);  
feed.LastUpdatedTime = DateTime.Now;  
feed.Items = from s in new string[] { "hello", "world" }  
select new SyndicationItem()  
{  
    Summary = SyndicationContent.CreatePlaintextContent(s)  
};  
  
//Write the feed out to a MemoryStream in JSON format  
DataContractJsonSerializer writeSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));  
writeSerializer.WriteObject(stream, new JsonFeedFormatter(feed));  
```  
  
## <a name="reading-a-json-feed"></a><span data-ttu-id="453a5-112">JSON 필드 읽기</span><span class="sxs-lookup"><span data-stu-id="453a5-112">Reading a JSON feed</span></span>  

 <span data-ttu-id="453a5-113">다음 코드와 같이<xref:System.ServiceModel.Syndication.SyndicationFeed>를 사용하여 JSON 형식의 데이터 스트림에서 `JsonFeedFormatter`를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-113">Obtaining a <xref:System.ServiceModel.Syndication.SyndicationFeed> from a stream of JSON-formatted data can be accomplished with the `JsonFeedFormatter` as show in the following code.</span></span>  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="453a5-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="453a5-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="453a5-115">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="453a5-116">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="453a5-117">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="453a5-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="453a5-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="453a5-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="453a5-119">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="453a5-120">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="453a5-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="453a5-121">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
