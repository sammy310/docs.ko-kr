---
title: <system.web> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: c8b01ec217fc1b6b91ccf36c8667922b57f26852
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185589"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="5b392-102">\<system.web> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="5b392-102">\<system.web> Element (Web Settings)</span></span>

<span data-ttu-id="5b392-103">ASP.NET 호스팅 계층이 프로세스 전체 동작을 관리 하는 방법에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="5b392-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b392-104">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b392-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5b392-105">Attributes and Elements</span></span>  

<span data-ttu-id="5b392-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b392-107">특성</span><span class="sxs-lookup"><span data-stu-id="5b392-107">Attributes</span></span>  

<span data-ttu-id="5b392-108">없음</span><span class="sxs-lookup"><span data-stu-id="5b392-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b392-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5b392-109">Child Elements</span></span>  
  
|<span data-ttu-id="5b392-110">요소</span><span class="sxs-lookup"><span data-stu-id="5b392-110">Element</span></span>|<span data-ttu-id="5b392-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b392-111">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="5b392-112">aspnet.config 파일의 IIS 응용 프로그램 풀에 대 한 구성 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-112">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b392-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5b392-113">Parent Elements</span></span>  
  
|<span data-ttu-id="5b392-114">요소</span><span class="sxs-lookup"><span data-stu-id="5b392-114">Element</span></span>|<span data-ttu-id="5b392-115">설명</span><span class="sxs-lookup"><span data-stu-id="5b392-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="5b392-116">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용 하는 모든 구성 파일의 루트 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b392-117">설명</span><span class="sxs-lookup"><span data-stu-id="5b392-117">Remarks</span></span>  

<span data-ttu-id="5b392-118">`system.web`요소와 해당 자식 `applicationPool` 요소가 .NET Framework 3.5 s p 1의 .NET Framework에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-118">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="5b392-119">통합 모드에서 IIS 7.0 이상 버전을 실행 하는 경우이 요소 조합을 사용 하면 ASP.NET에서 스레드를 관리 하는 방법 및 ASP.NET가 IIS 응용 프로그램 풀에서 호스팅되는 경우 요청을 큐에 대기 하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-119">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="5b392-120">클래식 또는 ISAPI 모드에서 IIS 7.0 이상 버전을 실행 하는 경우 이러한 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-120">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b392-121">예제</span><span class="sxs-lookup"><span data-stu-id="5b392-121">Example</span></span>  

<span data-ttu-id="5b392-122">다음 예제에서는 ASP.NET가 IIS 응용 프로그램 풀에서 호스팅될 때 aspnet.config 파일에서 ASP.NET 프로세스 전체 동작을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-122">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="5b392-123">이 예제에서는 IIS가 통합 모드로 실행 중이 고 응용 프로그램에서 .NET Framework 3.5 SP1 이상 버전을 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-123">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="5b392-124">이 동작은 .NET Framework 3.5 s p 1 이전의 .NET Framework 버전에서 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-124">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="5b392-125">이 예제의 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="5b392-125">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="5b392-126">요소 정보</span><span class="sxs-lookup"><span data-stu-id="5b392-126">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b392-127">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="5b392-127">Namespace</span></span>||  
|<span data-ttu-id="5b392-128">Schema Name</span><span class="sxs-lookup"><span data-stu-id="5b392-128">Schema Name</span></span>||  
|<span data-ttu-id="5b392-129">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="5b392-129">Validation File</span></span>||  
|<span data-ttu-id="5b392-130">비워 둘 수 있음</span><span class="sxs-lookup"><span data-stu-id="5b392-130">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="5b392-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b392-131">See also</span></span>

- [<span data-ttu-id="5b392-132">\<applicationPool> 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="5b392-132">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
