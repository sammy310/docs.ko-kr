---
description: '다음에 대 한 자세한 정보: <webProxyScript> 요소 (네트워크 설정)'
title: <webProxyScript> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
ms.openlocfilehash: 1627b6650582202f3f1a4c1fdebf2d183e4a894b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740108"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="4e538-103">\<webProxyScript> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4e538-103">\<webProxyScript> Element (Network Settings)</span></span>

<span data-ttu-id="4e538-104">웹 프록시를 검색 하는 데 사용 되는 스크립트의 특징을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e538-104">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="4e538-105">구문</span><span class="sxs-lookup"><span data-stu-id="4e538-105">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e538-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e538-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4e538-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e538-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e538-108">특성</span><span class="sxs-lookup"><span data-stu-id="4e538-108">Attributes</span></span>  
  
|<span data-ttu-id="4e538-109">attribute</span><span class="sxs-lookup"><span data-stu-id="4e538-109">Attribute</span></span>|<span data-ttu-id="4e538-110">설명</span><span class="sxs-lookup"><span data-stu-id="4e538-110">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="4e538-111">스크립트를 다운로드 하는 최대 시간을 시간, 분, 초 단위로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e538-111">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="4e538-112">기본값은 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="4e538-112">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e538-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e538-113">Child Elements</span></span>  

 <span data-ttu-id="4e538-114">없음</span><span class="sxs-lookup"><span data-stu-id="4e538-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e538-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e538-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4e538-116">요소</span><span class="sxs-lookup"><span data-stu-id="4e538-116">Element</span></span>|<span data-ttu-id="4e538-117">설명</span><span class="sxs-lookup"><span data-stu-id="4e538-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e538-118">설정</span><span class="sxs-lookup"><span data-stu-id="4e538-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="4e538-119"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e538-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e538-120">설명</span><span class="sxs-lookup"><span data-stu-id="4e538-120">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4e538-121">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4e538-121">Configuration Files</span></span>  

 <span data-ttu-id="4e538-122">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e538-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e538-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e538-123">See also</span></span>

- [<span data-ttu-id="4e538-124">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4e538-124">Network Settings Schema</span></span>](index.md)
