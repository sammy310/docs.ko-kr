---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: e7e82117304ac133e5e84c0fc36b987560bcef96
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933807"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="80509-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="80509-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="80509-102">PNRP(피어 이름 확인 프로토콜)가 확인자로 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80509-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="80509-103">PNRP가 기본 확인자이므로 이 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="80509-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="80509-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="80509-104">\<system.serviceModel></span></span>  
<span data-ttu-id="80509-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="80509-105">\<bindings></span></span>  
<span data-ttu-id="80509-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="80509-106">\<customBinding></span></span>  
<span data-ttu-id="80509-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="80509-107">\<binding></span></span>  
<span data-ttu-id="80509-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="80509-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80509-109">구문</span><span class="sxs-lookup"><span data-stu-id="80509-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80509-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="80509-110">Attributes and Elements</span></span>  
 <span data-ttu-id="80509-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80509-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80509-112">특성</span><span class="sxs-lookup"><span data-stu-id="80509-112">Attributes</span></span>  
  
|<span data-ttu-id="80509-113">특성</span><span class="sxs-lookup"><span data-stu-id="80509-113">Attribute</span></span>|<span data-ttu-id="80509-114">설명</span><span class="sxs-lookup"><span data-stu-id="80509-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80509-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="80509-115">resolverType</span></span>|<span data-ttu-id="80509-116">사용할 확인자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80509-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="80509-117">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="80509-117">This attribute is optional.</span></span> <span data-ttu-id="80509-118">이 특성을 설정하지 않거나 빈 문자열로 설정하면 PNRP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="80509-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80509-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="80509-119">Child Elements</span></span>  
 <span data-ttu-id="80509-120">없음</span><span class="sxs-lookup"><span data-stu-id="80509-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80509-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="80509-121">Parent Elements</span></span>  
  
|<span data-ttu-id="80509-122">요소</span><span class="sxs-lookup"><span data-stu-id="80509-122">Element</span></span>|<span data-ttu-id="80509-123">설명</span><span class="sxs-lookup"><span data-stu-id="80509-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80509-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="80509-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="80509-125">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="80509-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80509-126">예제</span><span class="sxs-lookup"><span data-stu-id="80509-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="80509-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="80509-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="80509-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="80509-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="80509-129">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="80509-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="80509-130">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="80509-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="80509-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="80509-131">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="80509-132">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="80509-132">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
