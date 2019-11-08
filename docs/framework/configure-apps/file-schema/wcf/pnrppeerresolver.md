---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738773"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="8fc90-101">\<pnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="8fc90-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="8fc90-102">PNRP(피어 이름 확인 프로토콜)가 확인자로 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc90-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="8fc90-103">PNRP가 기본 확인자이므로 이 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc90-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="8fc90-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8fc90-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8fc90-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="8fc90-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8fc90-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="8fc90-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="8fc90-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8fc90-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8fc90-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="8fc90-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8fc90-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**pnrpResolver >**</span><span class="sxs-lookup"><span data-stu-id="8fc90-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc90-110">구문</span><span class="sxs-lookup"><span data-stu-id="8fc90-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fc90-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8fc90-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8fc90-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc90-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fc90-113">특성</span><span class="sxs-lookup"><span data-stu-id="8fc90-113">Attributes</span></span>  
  
|<span data-ttu-id="8fc90-114">특성</span><span class="sxs-lookup"><span data-stu-id="8fc90-114">Attribute</span></span>|<span data-ttu-id="8fc90-115">설명</span><span class="sxs-lookup"><span data-stu-id="8fc90-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8fc90-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="8fc90-116">resolverType</span></span>|<span data-ttu-id="8fc90-117">사용할 확인자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc90-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="8fc90-118">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc90-118">This attribute is optional.</span></span> <span data-ttu-id="8fc90-119">이 특성을 설정하지 않거나 빈 문자열로 설정하면 PNRP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fc90-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fc90-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8fc90-120">Child Elements</span></span>  
 <span data-ttu-id="8fc90-121">없음</span><span class="sxs-lookup"><span data-stu-id="8fc90-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fc90-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8fc90-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8fc90-123">요소</span><span class="sxs-lookup"><span data-stu-id="8fc90-123">Element</span></span>|<span data-ttu-id="8fc90-124">설명</span><span class="sxs-lookup"><span data-stu-id="8fc90-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fc90-125">\<binding ></span><span class="sxs-lookup"><span data-stu-id="8fc90-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="8fc90-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc90-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8fc90-127">예제</span><span class="sxs-lookup"><span data-stu-id="8fc90-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="8fc90-128">참조</span><span class="sxs-lookup"><span data-stu-id="8fc90-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8fc90-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="8fc90-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8fc90-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="8fc90-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8fc90-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="8fc90-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8fc90-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8fc90-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="8fc90-133">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="8fc90-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
