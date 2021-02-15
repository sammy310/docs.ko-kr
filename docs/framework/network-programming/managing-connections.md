---
title: 연결 관리
description: 데이터 리소스에 HTTP를 사용하는 애플리케이션이 .NET Framework ServicePoint 및 ServicePointManager 클래스를 사용하여 연결을 관리할 수 있는 방법을 알아봅니다.
ms.date: 01/25/2021
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
ms.openlocfilehash: 9ea93c3a9c484fd2a3de58b4d484b1e8445da155
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99548060"
---
# <a name="managing-connections"></a><span data-ttu-id="3c226-103">연결 관리</span><span class="sxs-lookup"><span data-stu-id="3c226-103">Managing Connections</span></span>

<span data-ttu-id="3c226-104">HTTP를 사용하여 데이터 리소스에 연결하는 애플리케이션은 .NET Framework의 <xref:System.Net.ServicePoint> 및 <xref:System.Net.ServicePointManager> 클래스를 사용하여 인터넷에 대한 연결을 관리하고 최적의 규모 및 성능을 달성하도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-104">Applications that use HTTP to connect to data resources can use the .NET Framework's <xref:System.Net.ServicePoint> and <xref:System.Net.ServicePointManager> classes to manage connections to the Internet and to help them achieve optimum scale and performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="3c226-105">`ServicePoint` 및 `ServicePointManager`는 .NET Core, .NET 5 이상 버전에서 레거시로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-105">`ServicePoint` and `ServicePointManager` are considered legacy on .NET Core, .NET 5, and later versions.</span></span> <span data-ttu-id="3c226-106">대부분의 속성 및 메서드는 이러한 버전에서 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-106">Most of their properties and methods are not implemented in these versions.</span></span> <span data-ttu-id="3c226-107">구현된 경우에는 `HttpClient` 네트워킹 API에 대한 어떤 것도 영향을 주거나 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-107">When they are implemented, they don't affect or track anything about `HttpClient` networking APIs.</span></span>
  
 <span data-ttu-id="3c226-108">**ServicePoint** 클래스는 애플리케이션이 인터넷 리소스에 액세스하기 위해 연결할 수 있는 엔드포인트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-108">The **ServicePoint** class provides an application with an endpoint to which the application can connect to access Internet resources.</span></span> <span data-ttu-id="3c226-109">각 **ServicePoint** 에는 성능을 향상시키기 위해 연결 간 최적화 정보를 공유하여 인터넷 서버와의 연결을 최적화시킬 수 있는 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-109">Each **ServicePoint** contains information that helps optimize connections with an Internet server by sharing optimization information between connections to improve performance.</span></span>  
  
 <span data-ttu-id="3c226-110">각 **ServicePoint** 는 URI(Uniform Resource Identifier)로 식별되며 URI의 구성표 식별자 및 호스트 조각에 따라 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-110">Each **ServicePoint** is identified by a Uniform Resource Identifier (URI) and is categorized according to the scheme identifier and host fragments of the URI.</span></span> <span data-ttu-id="3c226-111">예를 들어 동일한 **ServicePoint** 인스턴스에는 동일한 구성표 식별자(http) 및 호스트 조각(`www.contoso.com`)이 있으므로 이 인스턴스에서는 URI(`http://www.contoso.com/index.htm` 및 `http://www.contoso.com/news.htm?date=today`)에 요청을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-111">For example, the same **ServicePoint** instance would provide requests to the URIs `http://www.contoso.com/index.htm` and `http://www.contoso.com/news.htm?date=today` since they have the same scheme identifier (http) and host fragments (`www.contoso.com`).</span></span> <span data-ttu-id="3c226-112">애플리케이션이 이미 `www.contoso.com` 서버에 영구적으로 연결되어 있는 경우 해당 연결을 사용하여 두 요청을 모두 검색하므로 두 연결을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-112">If the application already has a persistent connection to the server `www.contoso.com`, it uses that connection to retrieve both requests, avoiding the need to create two connections.</span></span>  
  
 <span data-ttu-id="3c226-113">**ServicePointManager** 는 **ServicePoint** 인스턴스의 생성과 소멸을 관리하는 정적 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-113">**ServicePointManager** is a static class that manages the creation and destruction of **ServicePoint** instances.</span></span> <span data-ttu-id="3c226-114">애플리케이션에서 기존 **ServicePoint** 인스턴스의 컬렉션에 없는 인터넷 리소스를 요청하면 **ServicePointManager** 에서 **ServicePoint** 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-114">The **ServicePointManager** creates a **ServicePoint** when the application requests an Internet resource that is not in the collection of existing **ServicePoint** instances.</span></span> <span data-ttu-id="3c226-115">**ServicePoint** 인스턴스는 최대 유휴 시간이 초과되거나 기존 **ServicePoint** 인스턴스의 수가 애플리케이션의 **ServicePoint** 인스턴스 최대 수를 초과할 때 소멸됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-115">**ServicePoint** instances are destroyed when they have exceeded their maximum idle time or when the number of existing **ServicePoint** instances exceeds the maximum number of **ServicePoint** instances for the application.</span></span> <span data-ttu-id="3c226-116">**ServicePointManager** 에서 <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> 및 <xref:System.Net.ServicePointManager.MaxServicePoints%2A> 속성을 설정하여 유휴 시간의 기본 최대값과 **ServicePoint** 인스턴스의 최대 수를 모두 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-116">You can control both the default maximum idle time and the maximum number of **ServicePoint** instances by setting the <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> and <xref:System.Net.ServicePointManager.MaxServicePoints%2A> properties on the **ServicePointManager**.</span></span>  
  
 <span data-ttu-id="3c226-117">클라이언트와 서버 사이의 연결 수는 애플리케이션 처리량에 상당한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-117">The number of connections between a client and server can have a dramatic impact on application throughput.</span></span> <span data-ttu-id="3c226-118">기본적으로 <xref:System.Net.HttpWebRequest> 클래스를 사용하는 애플리케이션에서는 지정된 서버에 대한 영구적 연결을 최대 2개 사용하지만 애플리케이션별로 최대 연결 수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-118">By default, an application using the <xref:System.Net.HttpWebRequest> class uses a maximum of two persistent connections to a given server, but you can set the maximum number of connections on a per-application basis.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c226-119">HTTP/1.1 사양에 따르면 애플리케이션으로부터의 연결은 서버당 두 개의 연결로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-119">The HTTP/1.1 specification limits the number of connections from an application to two connections per server.</span></span>  
  
 <span data-ttu-id="3c226-120">최적의 연결 수는 애플리케이션이 실행되는 실제 조건에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-120">The optimum number of connections depends on the actual conditions in which the application runs.</span></span> <span data-ttu-id="3c226-121">애플리케이션에 사용 가능한 연결 수를 늘려도 애플리케이션 성능에 영향을 미치지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-121">Increasing the number of connections available to the application may not affect application performance.</span></span> <span data-ttu-id="3c226-122">연결이 추가되는 경우 미치는 영향을 판별하려면 연결 수를 변경하면서 성능 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-122">To determine the impact of more connections, run performance tests while varying the number of connections.</span></span> <span data-ttu-id="3c226-123">다음 코드 샘플에 표시된 대로 애플리케이션 초기화 시 **ServicePointManager** 클래스의 정적 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 속성을 변경하여 해당 애플리케이션에서 사용하는 연결 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-123">You can change the number of connections that an application uses by changing the static <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> property on the **ServicePointManager** class at application initialization, as shown in the following code sample.</span></span>  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 <span data-ttu-id="3c226-124">**ServicePointManager.DefaultConnectionLimit** 속성을 변경해도 이전에 초기화된 **ServicePoint** 인스턴스에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-124">Changing the **ServicePointManager.DefaultConnectionLimit** property does not affect previously initialized **ServicePoint** instances.</span></span> <span data-ttu-id="3c226-125">다음 코드에서는 `http://www.contoso.com` 서버의 기존 **ServicePoint** 에 대한 연결 한계를 `newLimit`에 저장된 값으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3c226-125">The following code demonstrates changing the connection limit on an existing **ServicePoint** for the server `http://www.contoso.com` to the value stored in `newLimit`.</span></span>  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c226-126">참조</span><span class="sxs-lookup"><span data-stu-id="3c226-126">See also</span></span>

- [<span data-ttu-id="3c226-127">연결 그룹화</span><span class="sxs-lookup"><span data-stu-id="3c226-127">Connection Grouping</span></span>](connection-grouping.md)
- [<span data-ttu-id="3c226-128">애플리케이션 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="3c226-128">Using Application Protocols</span></span>](using-application-protocols.md)
