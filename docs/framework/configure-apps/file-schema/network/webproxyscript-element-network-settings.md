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
ms.openlocfilehash: dbad888cd0537f63c09840ac1053f924db9ea9bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089066"
---
# <a name="webproxyscript-element-network-settings"></a><span data-ttu-id="9454c-102">\<webProxyScript> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9454c-102">\<webProxyScript> Element (Network Settings)</span></span>
<span data-ttu-id="9454c-103">웹 프록시를 검색 하는 데 사용 되는 스크립트의 특징을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9454c-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webProxyScript>**

## <a name="syntax"></a><span data-ttu-id="9454c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9454c-104">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9454c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9454c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9454c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9454c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9454c-107">특성</span><span class="sxs-lookup"><span data-stu-id="9454c-107">Attributes</span></span>  
  
|<span data-ttu-id="9454c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9454c-108">Attribute</span></span>|<span data-ttu-id="9454c-109">Description</span><span class="sxs-lookup"><span data-stu-id="9454c-109">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="9454c-110">스크립트를 다운로드 하는 최대 시간을 시간, 분, 초 단위로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9454c-110">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="9454c-111">기본값은 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="9454c-111">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9454c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9454c-112">Child Elements</span></span>  
 <span data-ttu-id="9454c-113">없음</span><span class="sxs-lookup"><span data-stu-id="9454c-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9454c-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9454c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9454c-115">요소</span><span class="sxs-lookup"><span data-stu-id="9454c-115">Element</span></span>|<span data-ttu-id="9454c-116">Description</span><span class="sxs-lookup"><span data-stu-id="9454c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9454c-117">설정</span><span class="sxs-lookup"><span data-stu-id="9454c-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="9454c-118"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9454c-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9454c-119">설명</span><span class="sxs-lookup"><span data-stu-id="9454c-119">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9454c-120">구성 파일</span><span class="sxs-lookup"><span data-stu-id="9454c-120">Configuration Files</span></span>  
 <span data-ttu-id="9454c-121">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9454c-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9454c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9454c-122">See also</span></span>

- [<span data-ttu-id="9454c-123">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9454c-123">Network Settings Schema</span></span>](index.md)
