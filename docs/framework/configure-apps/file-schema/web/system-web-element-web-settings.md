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
ms.openlocfilehash: 3ffd25dae3826df0f02f2afb707f7317b2d92d24
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584550"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="e7e17-102">\<system.web > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="e7e17-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="e7e17-103">ASP.NET 호스팅 계층 프로세스 전반 동작을 관리 하는 방법에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="e7e17-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e7e17-104">\<configuration></span></span>  
<span data-ttu-id="e7e17-105">\<system.web > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="e7e17-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e17-106">구문</span><span class="sxs-lookup"><span data-stu-id="e7e17-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7e17-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e7e17-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e7e17-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7e17-109">특성</span><span class="sxs-lookup"><span data-stu-id="e7e17-109">Attributes</span></span>  
 <span data-ttu-id="e7e17-110">없음</span><span class="sxs-lookup"><span data-stu-id="e7e17-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7e17-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e7e17-111">Child Elements</span></span>  
  
|<span data-ttu-id="e7e17-112">요소</span><span class="sxs-lookup"><span data-stu-id="e7e17-112">Element</span></span>|<span data-ttu-id="e7e17-113">설명</span><span class="sxs-lookup"><span data-stu-id="e7e17-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7e17-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="e7e17-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="e7e17-115">Aspnet.config 파일에서 IIS 응용 프로그램 풀에 대 한 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7e17-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e7e17-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e7e17-117">요소</span><span class="sxs-lookup"><span data-stu-id="e7e17-117">Element</span></span>|<span data-ttu-id="e7e17-118">설명</span><span class="sxs-lookup"><span data-stu-id="e7e17-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7e17-119">\<구성></span><span class="sxs-lookup"><span data-stu-id="e7e17-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="e7e17-120">공용 언어 런타임과.NET Framework 응용 프로그램에서 사용 되는 모든 구성 파일의 루트 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e17-121">설명</span><span class="sxs-lookup"><span data-stu-id="e7e17-121">Remarks</span></span>  
 <span data-ttu-id="e7e17-122">`system.web` 요소와 해당 자식의 `applicationPool` 의.NET Framework에 추가 된 요소 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="e7e17-123">실행할 때 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 통합된 모드의 이후 버전에서는이 요소 조합을 사용 하 여 ASP.NET 스레드를 관리 하는 방법 및 ASP.NET 응용 프로그램 IIS 풀에 호스팅되는 경우 요청 큐 하는 방법을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="e7e17-124">실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 이상을 ISAPI 또는 클래식 모드에서는 이러한 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7e17-125">예제</span><span class="sxs-lookup"><span data-stu-id="e7e17-125">Example</span></span>  
 <span data-ttu-id="e7e17-126">다음 예제에서는 ASP.NET 응용 프로그램 IIS 풀에 호스팅되는 경우 aspnet.config 파일에서 ASP.NET 프로세스 전반 동작을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="e7e17-127">이 예제에서는 IIS 통합 모드에서 실행 되 고 있는지 가정 모드 및 응용 프로그램을 사용 하 여는 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="e7e17-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="e7e17-128">이 동작은.NET Framework의 버전에 없는 이전의 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-128">This behavior does not occur in versions of the .NET Framework earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="e7e17-129">예제에서 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="e7e17-130">요소 정보</span><span class="sxs-lookup"><span data-stu-id="e7e17-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7e17-131">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e7e17-131">Namespace</span></span>||  
|<span data-ttu-id="e7e17-132">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="e7e17-132">Schema Name</span></span>||  
|<span data-ttu-id="e7e17-133">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="e7e17-133">Validation File</span></span>||  
|<span data-ttu-id="e7e17-134">비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e17-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="e7e17-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7e17-135">See also</span></span>

- [<span data-ttu-id="e7e17-136">\<applicationPool> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="e7e17-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
