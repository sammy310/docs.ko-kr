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
ms.openlocfilehash: 50566422c5e28585e93171c991144cf12a6866eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698501"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="dbf8d-102">\<system.web > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="dbf8d-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="dbf8d-103">ASP.NET 호스팅 계층 프로세스 전반 동작을 관리 하는 방법에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="dbf8d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dbf8d-104">\<configuration></span></span>  
<span data-ttu-id="dbf8d-105">\<system.web > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="dbf8d-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbf8d-106">구문</span><span class="sxs-lookup"><span data-stu-id="dbf8d-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbf8d-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dbf8d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dbf8d-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbf8d-109">특성</span><span class="sxs-lookup"><span data-stu-id="dbf8d-109">Attributes</span></span>  
 <span data-ttu-id="dbf8d-110">없음</span><span class="sxs-lookup"><span data-stu-id="dbf8d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dbf8d-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dbf8d-111">Child Elements</span></span>  
  
|<span data-ttu-id="dbf8d-112">요소</span><span class="sxs-lookup"><span data-stu-id="dbf8d-112">Element</span></span>|<span data-ttu-id="dbf8d-113">설명</span><span class="sxs-lookup"><span data-stu-id="dbf8d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbf8d-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="dbf8d-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="dbf8d-115">Aspnet.config 파일에서 IIS 응용 프로그램 풀에 대 한 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dbf8d-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dbf8d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dbf8d-117">요소</span><span class="sxs-lookup"><span data-stu-id="dbf8d-117">Element</span></span>|<span data-ttu-id="dbf8d-118">설명</span><span class="sxs-lookup"><span data-stu-id="dbf8d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbf8d-119">\<구성></span><span class="sxs-lookup"><span data-stu-id="dbf8d-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="dbf8d-120">공용 언어 런타임 및 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbf8d-121">설명</span><span class="sxs-lookup"><span data-stu-id="dbf8d-121">Remarks</span></span>  
 <span data-ttu-id="dbf8d-122">`system.web` 요소와 해당 자식의 `applicationPool` 요소에 추가 된 합니다 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 의 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="dbf8d-123">실행할 때 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 통합된 모드의 이후 버전에서는이 요소 조합을 사용 하 여 ASP.NET 스레드를 관리 하는 방법 및 ASP.NET 응용 프로그램 IIS 풀에 호스팅되는 경우 요청 큐 하는 방법을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="dbf8d-124">실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 이상을 ISAPI 또는 클래식 모드에서는 이러한 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbf8d-125">예제</span><span class="sxs-lookup"><span data-stu-id="dbf8d-125">Example</span></span>  
 <span data-ttu-id="dbf8d-126">다음 예제에서는 ASP.NET 응용 프로그램 IIS 풀에 호스팅되는 경우 aspnet.config 파일에서 ASP.NET 프로세스 전반 동작을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="dbf8d-127">이 예제에서는 IIS 통합 모드에서 실행 되 고 있는지 가정 모드 및 응용 프로그램을 사용 하 여는 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 이상 버전.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="dbf8d-128">버전에서이 문제가 발생 하지 않습니다 합니다 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 이전의 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="dbf8d-129">예제에서 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="dbf8d-130">요소 정보</span><span class="sxs-lookup"><span data-stu-id="dbf8d-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dbf8d-131">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="dbf8d-131">Namespace</span></span>||  
|<span data-ttu-id="dbf8d-132">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="dbf8d-132">Schema Name</span></span>||  
|<span data-ttu-id="dbf8d-133">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="dbf8d-133">Validation File</span></span>||  
|<span data-ttu-id="dbf8d-134">비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf8d-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="dbf8d-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="dbf8d-135">See also</span></span>

- [<span data-ttu-id="dbf8d-136">\<applicationPool> 요소(웹 설정)</span><span class="sxs-lookup"><span data-stu-id="dbf8d-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
