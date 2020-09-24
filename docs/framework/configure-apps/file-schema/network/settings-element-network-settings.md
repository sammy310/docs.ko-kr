---
title: <settings> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: c5fe0b9eccd1c429c0041fcfab06b0cc20a20aa2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167277"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="5d2a0-102">\<settings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="5d2a0-102">\<settings> Element (Network Settings)</span></span>

<span data-ttu-id="5d2a0-103"><xref:System.Net?displayProperty=nameWithType> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="5d2a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d2a0-104">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d2a0-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5d2a0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="5d2a0-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d2a0-107">특성</span><span class="sxs-lookup"><span data-stu-id="5d2a0-107">Attributes</span></span>  

 <span data-ttu-id="5d2a0-108">없음</span><span class="sxs-lookup"><span data-stu-id="5d2a0-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d2a0-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5d2a0-109">Child Elements</span></span>  
  
|<span data-ttu-id="5d2a0-110">요소</span><span class="sxs-lookup"><span data-stu-id="5d2a0-110">Element</span></span>|<span data-ttu-id="5d2a0-111">설명</span><span class="sxs-lookup"><span data-stu-id="5d2a0-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d2a0-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="5d2a0-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="5d2a0-113">클래스에서 사용 하는 매개 변수를 사용자 지정 <xref:System.Net.HttpListener> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="5d2a0-114">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="5d2a0-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="5d2a0-115">웹 요청 매개 변수를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="5d2a0-116">ipv6)</span><span class="sxs-lookup"><span data-stu-id="5d2a0-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="5d2a0-117">IPv6 (인터넷 프로토콜 버전 6) 지원을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="5d2a0-118">\<performanceCounter> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="5d2a0-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="5d2a0-119">네트워크 성능 카운터를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="5d2a0-120">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="5d2a0-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="5d2a0-121">네트워크 리소스에 대 한 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="5d2a0-122">소켓이</span><span class="sxs-lookup"><span data-stu-id="5d2a0-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="5d2a0-123">소켓 작업에서 완료 포트를 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="5d2a0-124">\<webProxyScript> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="5d2a0-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="5d2a0-125">웹 프록시를 검색 하는 데 사용 되는 스크립트의 특징을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d2a0-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5d2a0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="5d2a0-127">요소</span><span class="sxs-lookup"><span data-stu-id="5d2a0-127">Element</span></span>|<span data-ttu-id="5d2a0-128">설명</span><span class="sxs-lookup"><span data-stu-id="5d2a0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d2a0-129">system.net</span><span class="sxs-lookup"><span data-stu-id="5d2a0-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="5d2a0-130">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d2a0-131">설명</span><span class="sxs-lookup"><span data-stu-id="5d2a0-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5d2a0-132">구성 파일</span><span class="sxs-lookup"><span data-stu-id="5d2a0-132">Configuration Files</span></span>  

 <span data-ttu-id="5d2a0-133">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d2a0-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2a0-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d2a0-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="5d2a0-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5d2a0-135">Network Settings Schema</span></span>](index.md)
