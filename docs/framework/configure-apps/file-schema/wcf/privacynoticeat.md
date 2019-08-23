---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: f7349bf61082c5d8e5bd4249e01b8835a1861cb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934263"
---
# <a name="privacynoticeat"></a><span data-ttu-id="ba27e-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="ba27e-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="ba27e-102">`wsFederationHttp` 바인딩에 사용되는 개인 정보 알림을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba27e-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="ba27e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ba27e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ba27e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ba27e-104">\<bindings></span></span>  
<span data-ttu-id="ba27e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ba27e-105">\<customBinding></span></span>  
<span data-ttu-id="ba27e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba27e-106">\<binding></span></span>  
<span data-ttu-id="ba27e-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="ba27e-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba27e-108">구문</span><span class="sxs-lookup"><span data-stu-id="ba27e-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="ba27e-109">형식</span><span class="sxs-lookup"><span data-stu-id="ba27e-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba27e-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ba27e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba27e-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba27e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba27e-112">특성</span><span class="sxs-lookup"><span data-stu-id="ba27e-112">Attributes</span></span>  
  
|<span data-ttu-id="ba27e-113">특성</span><span class="sxs-lookup"><span data-stu-id="ba27e-113">Attribute</span></span>|<span data-ttu-id="ba27e-114">Description</span><span class="sxs-lookup"><span data-stu-id="ba27e-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="ba27e-115">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ba27e-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="ba27e-116">이 개인 정보 알림의 버전을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ba27e-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba27e-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ba27e-117">Child Elements</span></span>  
 <span data-ttu-id="ba27e-118">없음</span><span class="sxs-lookup"><span data-stu-id="ba27e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba27e-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ba27e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ba27e-120">요소</span><span class="sxs-lookup"><span data-stu-id="ba27e-120">Element</span></span>|<span data-ttu-id="ba27e-121">설명</span><span class="sxs-lookup"><span data-stu-id="ba27e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba27e-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba27e-122">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ba27e-123">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ba27e-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba27e-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba27e-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ba27e-125">바인딩</span><span class="sxs-lookup"><span data-stu-id="ba27e-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ba27e-126">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="ba27e-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ba27e-127">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="ba27e-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ba27e-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ba27e-128">\<customBinding></span></span>](custombinding.md)
