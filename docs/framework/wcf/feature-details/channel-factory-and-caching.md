---
title: 채널 팩터리 및 캐싱
ms.date: 03/30/2017
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
ms.openlocfilehash: 3914ba74337bd959558348c191a897c79a32da52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784308"
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="a4293-102">채널 팩터리 및 캐싱</span><span class="sxs-lookup"><span data-stu-id="a4293-102">Channel Factory and Caching</span></span>
<span data-ttu-id="a4293-103">WCF 클라이언트 응용 프로그램에서는 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 WCF 서비스와의 통신 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-103">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="a4293-104"><xref:System.ServiceModel.ChannelFactory%601> 인스턴스를 만들 때는 다음 작업이 필요하기 때문에 약간의 오버헤드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-104">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>  
  
- <span data-ttu-id="a4293-105">생성 된 <xref:System.ServiceModel.Description.ContractDescription> 트리</span><span class="sxs-lookup"><span data-stu-id="a4293-105">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>  
  
- <span data-ttu-id="a4293-106">필요한 모든 CLR 형식 반영</span><span class="sxs-lookup"><span data-stu-id="a4293-106">Reflecting all of the required CLR types</span></span>  
  
- <span data-ttu-id="a4293-107">채널 스택 생성</span><span class="sxs-lookup"><span data-stu-id="a4293-107">Constructing the channel stack</span></span>  
  
- <span data-ttu-id="a4293-108">리소스 삭제</span><span class="sxs-lookup"><span data-stu-id="a4293-108">Disposing of resources</span></span>  
  
 <span data-ttu-id="a4293-109">이 오버헤드를 최소화하기 위해 사용자가 WCF 클라이언트 프록시를 사용할 때 WCF가 채널 팩터리를 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-109">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="a4293-110"><xref:System.ServiceModel.ChannelFactory%601> 클래스를 직접 사용하면 채널 팩터리 생성을 직접 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-110">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>  
  
 <span data-ttu-id="a4293-111">사용 하 여 생성 된 WCF 클라이언트 프록시 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 에서 파생 된 <xref:System.ServiceModel.ClientBase%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-111">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="a4293-112"><xref:System.ServiceModel.ClientBase%601>는 채널 팩터리 캐싱 동작을 정의하는 정적 <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-112"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="a4293-113">캐시 설정은 특정 형식에 대해 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-113">Cache settings are made for a specific type.</span></span> <span data-ttu-id="a4293-114">예를 들어, 설정 `ClientBase<ITest>.CacheSettings` 아래에 정의 된 값 중 하나에 해당 프록시/ClientBase 형식의 영향이 `ITest`합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-114">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="a4293-115">특정 <xref:System.ServiceModel.ClientBase%601>에 대한 캐시 설정은 첫 번째 프록시/ClientBase 인스턴스가 만들어지는 즉시 변경할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-115">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>  
  
## <a name="specifying-caching-behavior"></a><span data-ttu-id="a4293-116">캐싱 동작 지정</span><span class="sxs-lookup"><span data-stu-id="a4293-116">Specifying Caching Behavior</span></span>  
 <span data-ttu-id="a4293-117">캐싱 동작은 <xref:System.ServiceModel.ClientBase%601.CacheSetting> 속성을 다음 값 중 하나로 설정하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-117">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>  
  
|<span data-ttu-id="a4293-118">캐시 설정 값</span><span class="sxs-lookup"><span data-stu-id="a4293-118">Cache Setting Value</span></span>|<span data-ttu-id="a4293-119">설명</span><span class="sxs-lookup"><span data-stu-id="a4293-119">Description</span></span>|  
|-------------------------|-----------------|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="a4293-120">응용 프로그램 도메인 안의 모든 <xref:System.ServiceModel.ClientBase%601> 인스턴스가 캐싱에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-120">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="a4293-121">개발자는 캐싱에 대해 보안 상의 문제가 없는 것으로 판단했습니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-121">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="a4293-122">캐시 되지 꺼집니다 "보안과 관련 된" 경우에 속성 <xref:System.ServiceModel.ClientBase%601> 액세스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-122">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="a4293-123">"보안과 관련 된" 속성을 <xref:System.ServiceModel.ClientBase%601> 됩니다 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> 고 <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-123">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|  
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="a4293-124">구성 파일에 정의된 엔드포인트에서 만든 <xref:System.ServiceModel.ClientBase%601> 인스턴스만 응용 프로그램 도메인 안의 캐싱에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-124">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="a4293-125">해당 응용 프로그램 도메인에서 프로그래밍 방식으로 생성된 모든 <xref:System.ServiceModel.ClientBase%601> 인스턴스는 캐싱에 참여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-125">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="a4293-126">또한 캐싱을 사용 하지 것입니다 인스턴스에 대 한 <xref:System.ServiceModel.ClientBase%601> 면 "보안과 관련 된" 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-126">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="a4293-127">해당 응용 프로그램 도메인 안에서 특정 형식의 <xref:System.ServiceModel.ClientBase%601>의 모든 인스턴스에 대한 캐싱이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-127">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|  
  
 <span data-ttu-id="a4293-128">다음 코드 조각에서는 <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-128">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="a4293-129">위 코드에서 `TestClient`의 모든 인스턴스는 같은 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-129">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>  
  
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
  
 <span data-ttu-id="a4293-130">위 예제에서 `TestClient`의 모든 인스턴스는 #4 인스턴스를 제외하고 같은 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-130">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="a4293-131">인스턴스 #4는 전용으로 특수하게 만들어진 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-131">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="a4293-132">이 설정은 특정 엔드포인트가 같은 채널 팩터리 형식(이 경우 `ITest`)의 다른 엔드포인트와 다른 보안 설정이 필요한 시나리오에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-132">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>  
  
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
  
 <span data-ttu-id="a4293-133">위 예제에서 `TestClient`의 모든 인스턴스는 다른 채널 팩터리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-133">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="a4293-134">이는 각 엔드포인트가 다른 보안 요구사항을 가지고 있고 캐시하는 의미가 없을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4293-134">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4293-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4293-135">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601>
- [<span data-ttu-id="a4293-136">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="a4293-136">Building Clients</span></span>](../../../../docs/framework/wcf/building-clients.md)
- [<span data-ttu-id="a4293-137">클라이언트</span><span class="sxs-lookup"><span data-stu-id="a4293-137">Clients</span></span>](../../../../docs/framework/wcf/feature-details/clients.md)
- [<span data-ttu-id="a4293-138">WCF 클라이언트를 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="a4293-138">Accessing Services Using a WCF Client</span></span>](../../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)
- [<span data-ttu-id="a4293-139">방법: ChannelFactory 사용</span><span class="sxs-lookup"><span data-stu-id="a4293-139">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
