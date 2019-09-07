---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d7c6c8efa971fb60f0257cc1c74ceda72e31cb84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400042"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="a26e2-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="a26e2-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="a26e2-102">PNRP(피어 이름 확인 프로토콜)가 확인자로 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a26e2-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="a26e2-103">PNRP가 기본 확인자이므로 이 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="a26e2-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="a26e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a26e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a26e2-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a26e2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a26e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a26e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a26e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="a26e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="a26e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="a26e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a26e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<pnrpResolver >**</span><span class="sxs-lookup"><span data-stu-id="a26e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a26e2-110">구문</span><span class="sxs-lookup"><span data-stu-id="a26e2-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a26e2-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a26e2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a26e2-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a26e2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a26e2-113">특성</span><span class="sxs-lookup"><span data-stu-id="a26e2-113">Attributes</span></span>  
  
|<span data-ttu-id="a26e2-114">특성</span><span class="sxs-lookup"><span data-stu-id="a26e2-114">Attribute</span></span>|<span data-ttu-id="a26e2-115">Description</span><span class="sxs-lookup"><span data-stu-id="a26e2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a26e2-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="a26e2-116">resolverType</span></span>|<span data-ttu-id="a26e2-117">사용할 확인자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a26e2-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="a26e2-118">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a26e2-118">This attribute is optional.</span></span> <span data-ttu-id="a26e2-119">이 특성을 설정하지 않거나 빈 문자열로 설정하면 PNRP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a26e2-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a26e2-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a26e2-120">Child Elements</span></span>  
 <span data-ttu-id="a26e2-121">없음</span><span class="sxs-lookup"><span data-stu-id="a26e2-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a26e2-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a26e2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a26e2-123">요소</span><span class="sxs-lookup"><span data-stu-id="a26e2-123">Element</span></span>|<span data-ttu-id="a26e2-124">설명</span><span class="sxs-lookup"><span data-stu-id="a26e2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a26e2-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="a26e2-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a26e2-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a26e2-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a26e2-127">예제</span><span class="sxs-lookup"><span data-stu-id="a26e2-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="a26e2-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="a26e2-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a26e2-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="a26e2-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a26e2-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="a26e2-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a26e2-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="a26e2-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a26e2-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a26e2-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="a26e2-133">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="a26e2-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
