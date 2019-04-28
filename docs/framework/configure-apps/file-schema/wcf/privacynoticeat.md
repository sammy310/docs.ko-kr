---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: e2ce2111e4bb26cc6a51b4a772b1d8a4d3238c70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783164"
---
# <a name="privacynoticeat"></a><span data-ttu-id="3597f-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="3597f-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="3597f-102">`wsFederationHttp` 바인딩에 사용되는 개인 정보 알림을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3597f-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="3597f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3597f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="3597f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3597f-104">\<bindings></span></span>  
<span data-ttu-id="3597f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3597f-105">\<customBinding></span></span>  
<span data-ttu-id="3597f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="3597f-106">\<binding></span></span>  
<span data-ttu-id="3597f-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="3597f-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3597f-108">구문</span><span class="sxs-lookup"><span data-stu-id="3597f-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="3597f-109">형식</span><span class="sxs-lookup"><span data-stu-id="3597f-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3597f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3597f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3597f-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3597f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3597f-112">특성</span><span class="sxs-lookup"><span data-stu-id="3597f-112">Attributes</span></span>  
  
|<span data-ttu-id="3597f-113">특성</span><span class="sxs-lookup"><span data-stu-id="3597f-113">Attribute</span></span>|<span data-ttu-id="3597f-114">설명</span><span class="sxs-lookup"><span data-stu-id="3597f-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="3597f-115">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3597f-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="3597f-116">이 개인 정보 알림의 버전을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3597f-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3597f-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3597f-117">Child Elements</span></span>  
 <span data-ttu-id="3597f-118">없음</span><span class="sxs-lookup"><span data-stu-id="3597f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3597f-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3597f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3597f-120">요소</span><span class="sxs-lookup"><span data-stu-id="3597f-120">Element</span></span>|<span data-ttu-id="3597f-121">설명</span><span class="sxs-lookup"><span data-stu-id="3597f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3597f-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="3597f-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3597f-123">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3597f-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3597f-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="3597f-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3597f-125">바인딩</span><span class="sxs-lookup"><span data-stu-id="3597f-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="3597f-126">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="3597f-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3597f-127">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="3597f-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3597f-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3597f-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
