---
title: <webProxyScript> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: 2abab3de2965c31c11d9acaf7b78f3a668563506
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697448"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="434e3-102">\<webProxyScript > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="434e3-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="434e3-103">웹 프록시를 검색 하는 데 사용 되는 스크립트의 특징을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e3-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
[<span data-ttu-id="434e3-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="434e3-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="434e3-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="434e3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="434e3-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="434e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="434e3-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<webProxyScript >**</span><span class="sxs-lookup"><span data-stu-id="434e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="434e3-108">구문</span><span class="sxs-lookup"><span data-stu-id="434e3-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="434e3-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="434e3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="434e3-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="434e3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="434e3-111">특성</span><span class="sxs-lookup"><span data-stu-id="434e3-111">Attributes</span></span>  
  
|<span data-ttu-id="434e3-112">특성</span><span class="sxs-lookup"><span data-stu-id="434e3-112">Attribute</span></span>|<span data-ttu-id="434e3-113">설명</span><span class="sxs-lookup"><span data-stu-id="434e3-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="434e3-114">스크립트를 다운로드 하는 최대 시간을 시간, 분, 초 단위로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="434e3-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="434e3-115">기본값은 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="434e3-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="434e3-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="434e3-116">Child Elements</span></span>  
 <span data-ttu-id="434e3-117">없음</span><span class="sxs-lookup"><span data-stu-id="434e3-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="434e3-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="434e3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="434e3-119">요소</span><span class="sxs-lookup"><span data-stu-id="434e3-119">Element</span></span>|<span data-ttu-id="434e3-120">설명</span><span class="sxs-lookup"><span data-stu-id="434e3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="434e3-121">settings</span><span class="sxs-lookup"><span data-stu-id="434e3-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="434e3-122"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="434e3-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="434e3-123">설명</span><span class="sxs-lookup"><span data-stu-id="434e3-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="434e3-124">구성 파일</span><span class="sxs-lookup"><span data-stu-id="434e3-124">Configuration Files</span></span>  
 <span data-ttu-id="434e3-125">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="434e3-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434e3-126">참조</span><span class="sxs-lookup"><span data-stu-id="434e3-126">See also</span></span>

- [<span data-ttu-id="434e3-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="434e3-127">Network Settings Schema</span></span>](index.md)
