---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: e67cc316b8747ee785055ceb4f954988fa82a44c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940622"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="f4f9a-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="f4f9a-101">\<useManagedPresentation></span></span>
<span data-ttu-id="f4f9a-102">WS-Trust의 CardSpace 프로필을 지원하는 CardSpace 보안 토큰 서비스와 통신하는 데 사용되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f4f9a-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="f4f9a-103">이 요소는 특성이 없고 빈 스위치로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f9a-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="f4f9a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f4f9a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f4f9a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f4f9a-105">\<bindings></span></span>  
<span data-ttu-id="f4f9a-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f4f9a-106">\<customBinding></span></span>  
<span data-ttu-id="f4f9a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f4f9a-107">\<binding></span></span>  
<span data-ttu-id="f4f9a-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="f4f9a-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4f9a-109">구문</span><span class="sxs-lookup"><span data-stu-id="f4f9a-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4f9a-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f4f9a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f4f9a-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f9a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4f9a-112">특성</span><span class="sxs-lookup"><span data-stu-id="f4f9a-112">Attributes</span></span>  
 <span data-ttu-id="f4f9a-113">없음</span><span class="sxs-lookup"><span data-stu-id="f4f9a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f4f9a-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f4f9a-114">Child Elements</span></span>  
 <span data-ttu-id="f4f9a-115">없음</span><span class="sxs-lookup"><span data-stu-id="f4f9a-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4f9a-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f4f9a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f4f9a-117">요소</span><span class="sxs-lookup"><span data-stu-id="f4f9a-117">Element</span></span>|<span data-ttu-id="f4f9a-118">설명</span><span class="sxs-lookup"><span data-stu-id="f4f9a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4f9a-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="f4f9a-119">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="f4f9a-120">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f9a-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4f9a-121">설명</span><span class="sxs-lookup"><span data-stu-id="f4f9a-121">Remarks</span></span>  
 <span data-ttu-id="f4f9a-122">이 요소는 ID 공급자가 정책에서 WS-Trust의 CardSpace 프로필을 지원함을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4f9a-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="f4f9a-123">그러한 정책 어설션을 게시하는 ID 공급자는 해당 CardSpace 프로필을 기반으로 토큰을 발급할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f9a-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f9a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4f9a-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f4f9a-125">바인딩</span><span class="sxs-lookup"><span data-stu-id="f4f9a-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f4f9a-126">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="f4f9a-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f4f9a-127">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="f4f9a-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f4f9a-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f4f9a-128">\<customBinding></span></span>](custombinding.md)
