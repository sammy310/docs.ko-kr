---
title: 채널 팩터리 및 캐싱
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: 5b8348a98b484ca08e3dbeba141dc49825c8c071
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587367"
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="b6e3e-102">채널 팩터리 및 캐싱</span><span class="sxs-lookup"><span data-stu-id="b6e3e-102">Channel Factory and Caching</span></span>

<span data-ttu-id="b6e3e-103">WCF 클라이언트 애플리케이션에서는 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 WCF 서비스와의 통신 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-103">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="b6e3e-104"><xref:System.ServiceModel.ChannelFactory%601> 인스턴스를 만들 때는 다음 작업이 필요하기 때문에 약간의 오버헤드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-104">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>

- <span data-ttu-id="b6e3e-105"><xref:System.ServiceModel.Description.ContractDescription> 트리 생성</span><span class="sxs-lookup"><span data-stu-id="b6e3e-105">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>

- <span data-ttu-id="b6e3e-106">필요한 모든 CLR 형식 반영</span><span class="sxs-lookup"><span data-stu-id="b6e3e-106">Reflecting all of the required CLR types</span></span>

- <span data-ttu-id="b6e3e-107">채널 스택 생성</span><span class="sxs-lookup"><span data-stu-id="b6e3e-107">Constructing the channel stack</span></span>

- <span data-ttu-id="b6e3e-108">리소스 삭제</span><span class="sxs-lookup"><span data-stu-id="b6e3e-108">Disposing of resources</span></span>

<span data-ttu-id="b6e3e-109">이 오버헤드를 최소화하기 위해 사용자가 WCF 클라이언트 프록시를 사용할 때 WCF가 채널 팩터리를 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-109">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>

> [!TIP]
> <span data-ttu-id="b6e3e-110"><xref:System.ServiceModel.ChannelFactory%601> 클래스를 직접 사용하면 채널 팩터리 생성을 직접 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-110">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>

<span data-ttu-id="b6e3e-111">[ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 생성 된 WCF 클라이언트 프록시는에서 파생 됩니다 <xref:System.ServiceModel.ClientBase%601> .</span><span class="sxs-lookup"><span data-stu-id="b6e3e-111">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="b6e3e-112"><xref:System.ServiceModel.ClientBase%601>는 채널 팩터리 캐싱 동작을 정의하는 정적 <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-112"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="b6e3e-113">캐시 설정은 특정 형식에 대해 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-113">Cache settings are made for a specific type.</span></span> <span data-ttu-id="b6e3e-114">예를 들어 아래에 정의 된 값 중 하나로 설정 하면 `ClientBase<ITest>.CacheSettings` 형식의 프록시/ClientBase에만 영향을 줍니다 `ITest` .</span><span class="sxs-lookup"><span data-stu-id="b6e3e-114">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="b6e3e-115">특정 <xref:System.ServiceModel.ClientBase%601>에 대한 캐시 설정은 첫 번째 프록시/ClientBase 인스턴스가 만들어지는 즉시 변경할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-115">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>

## <a name="specifying-caching-behavior"></a><span data-ttu-id="b6e3e-116">캐싱 동작 지정</span><span class="sxs-lookup"><span data-stu-id="b6e3e-116">Specifying Caching Behavior</span></span>

<span data-ttu-id="b6e3e-117">캐싱 동작은 <xref:System.ServiceModel.ClientBase%601.CacheSetting> 속성을 다음 값 중 하나로 설정하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-117">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>

|<span data-ttu-id="b6e3e-118">캐시 설정 값</span><span class="sxs-lookup"><span data-stu-id="b6e3e-118">Cache Setting Value</span></span>|<span data-ttu-id="b6e3e-119">Description</span><span class="sxs-lookup"><span data-stu-id="b6e3e-119">Description</span></span>|
|-------------------------|-----------------|
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="b6e3e-120">응용 프로그램 도메인 안의 모든 <xref:System.ServiceModel.ClientBase%601> 인스턴스가 캐싱에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-120">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="b6e3e-121">개발자는 캐싱에 대해 보안 상의 문제가 없는 것으로 판단했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-121">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="b6e3e-122">에서 "보안에 민감한" 속성에 액세스 하는 경우에도 캐싱이 해제 되지 않습니다 <xref:System.ServiceModel.ClientBase%601> .</span><span class="sxs-lookup"><span data-stu-id="b6e3e-122">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="b6e3e-123">의 "보안에 민감한" 속성은 <xref:System.ServiceModel.ClientBase%601> <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> , <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> 및 <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A> 입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-123">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="b6e3e-124">구성 파일에 정의된 엔드포인트에서 만든 <xref:System.ServiceModel.ClientBase%601> 인스턴스만 응용 프로그램 도메인 안의 캐싱에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-124">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="b6e3e-125">해당 응용 프로그램 도메인에서 프로그래밍 방식으로 생성된 모든 <xref:System.ServiceModel.ClientBase%601> 인스턴스는 캐싱에 참여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-125">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="b6e3e-126">또한 <xref:System.ServiceModel.ClientBase%601> "보안이 중요 한" 속성에 액세스 한 후에는 인스턴스에 대해 캐싱이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-126">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="b6e3e-127">해당 응용 프로그램 도메인 안에서 특정 형식의 <xref:System.ServiceModel.ClientBase%601>의 모든 인스턴스에 대한 캐싱이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-127">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|

<span data-ttu-id="b6e3e-128">다음 코드 조각에서는 <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-128">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase<ITest>.CacheSettings = CacheSettings.AlwaysOn;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient (new BasicHttpBinding(), new EndpointAddress(address)))
         {
            // ...
            proxy.Test(msg);
            // ...
         }
      }
   }
}
// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest { }
```

<span data-ttu-id="b6e3e-129">위 코드에서 `TestClient`의 모든 인스턴스는 같은 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-129">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase.CacheSettings = CacheSettings.Default;
      int i = 1;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))
         {
            if (i == 4)
            {
               ServiceEndpoint endpoint = proxy.Endpoint;
               ... // use endpoint in some way
            }
            proxy.Test(msg);
         }
         i++;
   }
}

// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}
```

<span data-ttu-id="b6e3e-130">위 예제에서 `TestClient`의 모든 인스턴스는 #4 인스턴스를 제외하고 같은 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-130">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="b6e3e-131">인스턴스 #4는 전용으로 특수하게 만들어진 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-131">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="b6e3e-132">이 설정은 특정 엔드포인트가 같은 채널 팩터리 형식(이 경우 `ITest`)의 다른 엔드포인트와 다른 보안 설정이 필요한 시나리오에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-132">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>

```csharp
class Program
{
   static void Main(string[] args)
   {
      ClientBase.CacheSettings = CacheSettings.AlwaysOff;
      foreach (string msg in messages)
      {
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))
         {
            proxy.Test(msg);
         }
      }
   }
}

// Generated by SvcUtil.exe
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}
```

<span data-ttu-id="b6e3e-133">위 예제에서 `TestClient`의 모든 인스턴스는 다른 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-133">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="b6e3e-134">이는 각 엔드포인트가 다른 보안 요구사항을 가지고 있고 캐시하는 의미가 없을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e3e-134">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6e3e-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6e3e-135">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601>
- [<span data-ttu-id="b6e3e-136">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="b6e3e-136">Building Clients</span></span>](../building-clients.md)
- [<span data-ttu-id="b6e3e-137">클라이언트</span><span class="sxs-lookup"><span data-stu-id="b6e3e-137">Clients</span></span>](clients.md)
- [<span data-ttu-id="b6e3e-138">WCF 클라이언트를 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="b6e3e-138">Accessing Services Using a WCF Client</span></span>](../accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="b6e3e-139">방법: ChannelFactory 사용</span><span class="sxs-lookup"><span data-stu-id="b6e3e-139">How to: Use the ChannelFactory</span></span>](how-to-use-the-channelfactory.md)
