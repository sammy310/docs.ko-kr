---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 624b52c0618362f48063c8f7e7c53c5a68d7de8f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400038"
---
# <a name="privacynoticeat"></a><span data-ttu-id="428a7-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="428a7-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="428a7-102">`wsFederationHttp` 바인딩에 사용되는 개인 정보 알림을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="428a7-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="428a7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="428a7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="428a7-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="428a7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="428a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="428a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="428a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="428a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="428a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="428a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="428a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<privacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="428a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="428a7-109">구문</span><span class="sxs-lookup"><span data-stu-id="428a7-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="428a7-110">형식</span><span class="sxs-lookup"><span data-stu-id="428a7-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="428a7-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="428a7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="428a7-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="428a7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="428a7-113">특성</span><span class="sxs-lookup"><span data-stu-id="428a7-113">Attributes</span></span>  
  
|<span data-ttu-id="428a7-114">특성</span><span class="sxs-lookup"><span data-stu-id="428a7-114">Attribute</span></span>|<span data-ttu-id="428a7-115">설명</span><span class="sxs-lookup"><span data-stu-id="428a7-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="428a7-116">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="428a7-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="428a7-117">이 개인 정보 알림의 버전을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="428a7-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="428a7-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="428a7-118">Child Elements</span></span>  
 <span data-ttu-id="428a7-119">없음</span><span class="sxs-lookup"><span data-stu-id="428a7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="428a7-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="428a7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="428a7-121">요소</span><span class="sxs-lookup"><span data-stu-id="428a7-121">Element</span></span>|<span data-ttu-id="428a7-122">설명</span><span class="sxs-lookup"><span data-stu-id="428a7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="428a7-123">\<binding></span><span class="sxs-lookup"><span data-stu-id="428a7-123">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="428a7-124">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="428a7-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="428a7-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="428a7-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="428a7-126">바인딩</span><span class="sxs-lookup"><span data-stu-id="428a7-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="428a7-127">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="428a7-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="428a7-128">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="428a7-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="428a7-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="428a7-129">\<customBinding></span></span>](custombinding.md)
