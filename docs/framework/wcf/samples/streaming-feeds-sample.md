---
description: '자세한 정보: 스트리밍 피드 샘플'
title: 스트리밍 피드 샘플
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: 1de295391316396d6c454496d34d8b82ad8129d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668749"
---
# <a name="streaming-feeds-sample"></a><span data-ttu-id="ec851-103">스트리밍 피드 샘플</span><span class="sxs-lookup"><span data-stu-id="ec851-103">Streaming Feeds Sample</span></span>

<span data-ttu-id="ec851-104">이 샘플에서는 많은 수의 항목이 포함된 배포 피드를 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-104">This sample demonstrates how to manage syndication feeds that contain large numbers of items.</span></span> <span data-ttu-id="ec851-105">서버에서 이 샘플은 항목을 네트워크 스트림에 쓰기 바로 전까지 피드 내에 개별 <xref:System.ServiceModel.Syndication.SyndicationItem> 개체를 만드는 동작을 지연시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-105">On the server, the sample demonstrates how to delay the creation of individual <xref:System.ServiceModel.Syndication.SyndicationItem> objects within the feed until immediately before the item is written to the network stream.</span></span>  
  
 <span data-ttu-id="ec851-106">클라이언트에서 이 샘플은 사용자 지정 배포 피드 포맷터를 사용하여 읽고 있는 피드가 메모리에 완전히 버퍼링되지 않도록 네트워크 스트림에서 개별 항목을 읽을 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-106">On the client, the sample shows how a custom syndication feed formatter can be used to read individual items from the network stream so that the feed being read is never fully buffered into memory.</span></span>  
  
 <span data-ttu-id="ec851-107">배포 API의 스트리밍 기능을 가장 잘 보여 주기 위해 이 샘플에서는 서버가 매우 많은 수의 항목이 포함된 피드를 노출하는 경우와 같이 실제로 드문 시나리오를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-107">To best demonstrate the streaming capability of the syndication API, this sample uses a somewhat unlikely scenario in which the server exposes a feed that contains an infinite number of items.</span></span> <span data-ttu-id="ec851-108">이 경우 서버는 클라이언트가 피드에서 지정된 수의 항목(기본값: 10개)을 읽었다고 확인할 때까지 계속해서 피드에 새 항목을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-108">In this case, the server continues generating new items into the feed until it determines that the client has read a specified number of items from the feed (by default, 10).</span></span> <span data-ttu-id="ec851-109">단순성을 위해 클라이언트와 서버는 모두 동일한 프로세스로 구현되며 공유 `ItemCounter` 개체를 사용하여 클라이언트가 생성한 항목의 수를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-109">For simplicity, both the client and the server are implemented in the same process and use a shared `ItemCounter` object to keep track of how many items the client has produced.</span></span> <span data-ttu-id="ec851-110">`ItemCounter` 형식은 샘플 시나리오를 간단히 종료할 목적으로만 사용되며 설명하려는 패턴의 핵심 요소는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-110">The `ItemCounter` type exists only for the purpose of allowing the sample scenario to terminate cleanly, and is not a core element of the pattern being demonstrated.</span></span>  
  
 <span data-ttu-id="ec851-111">이 데모에서는 키워드 구문을 사용 하 여 Visual c # 반복기를 사용 `yield return` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-111">The demonstration makes use of Visual C# iterators (using the `yield return` keyword construct).</span></span> <span data-ttu-id="ec851-112">반복기에 대 한 자세한 내용은 MSDN의 "반복기 사용" 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec851-112">For more information about iterators, see the "Using Iterators" topic on MSDN.</span></span>  
  
## <a name="service"></a><span data-ttu-id="ec851-113">서비스</span><span class="sxs-lookup"><span data-stu-id="ec851-113">Service</span></span>  

 <span data-ttu-id="ec851-114">이 서비스는 다음 코드에서와 같이 하나의 작업으로 구성된 기본 <xref:System.ServiceModel.Web.WebGetAttribute> 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-114">The service implements a basic <xref:System.ServiceModel.Web.WebGetAttribute> contract that consists of one operation, as shown in the following code.</span></span>  
  
```csharp  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 <span data-ttu-id="ec851-115">이 서비스는 다음 코드에서와 같이 `ItemGenerator` 클래스에서 반복기를 사용하여 <xref:System.ServiceModel.Syndication.SyndicationItem> 인스턴스의 무한 스트림을 만드는 방식으로 이 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-115">The service implements this contract by using an `ItemGenerator` class to create a potentially infinite stream of <xref:System.ServiceModel.Syndication.SyndicationItem> instances using an iterator, as shown in the following code.</span></span>  
  
```csharp
class ItemGenerator  
{  
    public IEnumerable<SyndicationItem> GenerateItems()  
    {  
        while (counter.GetCount() < maxItemsRead)  
        {  
            itemsReturned++;  
            yield return CreateNextItem();  
        }  
  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="ec851-116">서비스 구현에서 피드를 만들면 버퍼링된 항목 컬렉션 대신 `ItemGenerator.GenerateItems()`의 출력이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-116">When the service implementation creates the feed, the output of `ItemGenerator.GenerateItems()` is used instead of a buffered collection of items.</span></span>  
  
```csharp
public Atom10FeedFormatter StreamedFeed()  
{  
    SyndicationFeed feed = new SyndicationFeed("Streamed feed", "Feed to test streaming", null);  
    //Generate an infinite stream of items. Both the client and the service share  
    //a reference to the ItemCounter, which allows the sample to terminate  
    //execution after the client has read 10 items from the stream  
    ItemGenerator itemGenerator = new ItemGenerator(this.counter, 10);  
  
    feed.Items = itemGenerator.GenerateItems();  
    return feed.GetAtom10Formatter();  
}  
```  
  
 <span data-ttu-id="ec851-117">결과적으로 항목 스트림은 메모리에 완전히 버퍼링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-117">As a result, the item stream is never fully buffered into memory.</span></span> <span data-ttu-id="ec851-118">메서드 내의 문에 중단점을 설정 하 `yield return` `ItemGenerator.GenerateItems()` 고 서비스가 메서드의 결과를 반환한 후 처음으로이 중단점이 발생 하는 것을 확인 하 여이 동작을 관찰할 수 있습니다 `StreamedFeed()` .</span><span class="sxs-lookup"><span data-stu-id="ec851-118">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of the `ItemGenerator.GenerateItems()` method and noting that this breakpoint is encountered for the first time after the service has returned the result of the `StreamedFeed()` method.</span></span>  
  
## <a name="client"></a><span data-ttu-id="ec851-119">클라이언트</span><span class="sxs-lookup"><span data-stu-id="ec851-119">Client</span></span>  

 <span data-ttu-id="ec851-120">이 샘플의 클라이언트는 피드에 있는 개별 항목을 메모리에 버퍼링하는 대신 이 항목의 구체화를 지연시키는 사용자 지정 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-120">The client in this sample uses a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementation that delays the materialization of individual items in the feed instead of buffering them into memory.</span></span> <span data-ttu-id="ec851-121">사용자 지정 `StreamedAtom10FeedFormatter` 인스턴스는 다음과 같이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-121">The custom `StreamedAtom10FeedFormatter` instance is used as follows.</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 <span data-ttu-id="ec851-122">일반적으로 네트워크에서 피드의 전체 콘텐츠를 읽고 메모리에 버퍼링할 때까지는 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29>에 대한 호출이 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-122">Normally, a call to <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> does not return until the entire contents of the feed have been read from the network and buffered into memory.</span></span> <span data-ttu-id="ec851-123">반면 `StreamedAtom10FeedFormatter` 개체는 다음 코드에서와 같이 <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29>를 재정의하고 버퍼링된 컬렉션 대신 반복기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-123">However, the `StreamedAtom10FeedFormatter` object overrides <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> to return an iterator instead of a buffered collection, as shown in the following code.</span></span>  
  
```csharp  
protected override IEnumerable<SyndicationItem> ReadItems(XmlReader reader, SyndicationFeed feed, out bool areAllItemsRead)  
{  
    areAllItemsRead = false;  
    return DelayReadItems(reader, feed);  
}  
  
private IEnumerable<SyndicationItem> DelayReadItems(XmlReader reader, SyndicationFeed feed)  
{  
    while (reader.IsStartElement("entry", "http://www.w3.org/2005/Atom"))  
    {  
        yield return this.ReadItem(reader, feed);  
    }  
  
    reader.ReadEndElement();  
}  
```  
  
 <span data-ttu-id="ec851-124">따라서 `ReadItems()`의 결과를 이동하는 클라이언트 애플리케이션에서 사용 준비를 마칠 때까지는 네트워크에서 각 항목을 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-124">As a result, each item is not read from the network until the client application traversing the results of `ReadItems()` is ready to use it.</span></span> <span data-ttu-id="ec851-125">의 내부 문에 중단점을 설정 하 고에 대 한 `yield return` `StreamedAtom10FeedFormatter.DelayReadItems()` 호출이 완료 된 후 처음으로이 중단점이 발생 하는 것을 확인 하 여이 동작을 관찰할 수 있습니다 `ReadFrom()` .</span><span class="sxs-lookup"><span data-stu-id="ec851-125">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of `StreamedAtom10FeedFormatter.DelayReadItems()` and noticing that this breakpoint is encountered for the first time after the call to `ReadFrom()` completes.</span></span>  
  
 <span data-ttu-id="ec851-126">다음 지침에서는 샘플을 빌드하고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-126">The following instructions show how to build and run the sample.</span></span> <span data-ttu-id="ec851-127">클라이언트에서 10개의 항목을 읽고 나면 서버에서 항목 생성을 중지하지만 출력에는 클라이언트에서 10개 항목보다 훨씬 많은 항목을 읽는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-127">Note that although the server stops generating items after the client has read 10 items, the output shows that the client reads significantly more than 10 items.</span></span> <span data-ttu-id="ec851-128">이는 샘플에서 사용되는 네트워킹 바인딩에서 데이터를 4KB 단위의 세그먼트로 전송하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-128">This is because the networking binding used by the sample transmits data in four-kilobyte (KB) segments.</span></span> <span data-ttu-id="ec851-129">따라서 클라이언트는 한 항목을 읽을 기회가 생기기도 전에 4KB의 항목 데이터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-129">As such, the client receives 4KB of item data before it has the opportunity to read even one item.</span></span> <span data-ttu-id="ec851-130">이는 정상적인 동작입니다. 스트리밍된 HTTP 데이터를 적절한 크기의 세그먼트로 보내면 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-130">This is normal behavior (sending streamed HTTP data in reasonably-sized segments increases performance).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ec851-131">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ec851-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ec851-132">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ec851-133">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ec851-134">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ec851-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ec851-135">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ec851-136">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ec851-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ec851-137">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec851-138">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec851-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a><span data-ttu-id="ec851-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec851-139">See also</span></span>

- [<span data-ttu-id="ec851-140">독립형 진단 피드</span><span class="sxs-lookup"><span data-stu-id="ec851-140">Stand-Alone Diagnostics Feed</span></span>](stand-alone-diagnostics-feed-sample.md)
