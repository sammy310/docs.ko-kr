---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738773"
---
# \<pnrpPeerResolver>
<span data-ttu-id="0cdd3-101">PNRP(피어 이름 확인 프로토콜)가 확인자로 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd3-101">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="0cdd3-102">PNRP가 기본 확인자이므로 이 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd3-102">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="0cdd3-103">구문</span><span class="sxs-lookup"><span data-stu-id="0cdd3-103">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0cdd3-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0cdd3-104">Attributes and Elements</span></span>  
 <span data-ttu-id="0cdd3-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd3-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cdd3-106">특성</span><span class="sxs-lookup"><span data-stu-id="0cdd3-106">Attributes</span></span>  
  
|<span data-ttu-id="0cdd3-107">attribute</span><span class="sxs-lookup"><span data-stu-id="0cdd3-107">Attribute</span></span>|<span data-ttu-id="0cdd3-108">Description</span><span class="sxs-lookup"><span data-stu-id="0cdd3-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0cdd3-109">resolverType</span><span class="sxs-lookup"><span data-stu-id="0cdd3-109">resolverType</span></span>|<span data-ttu-id="0cdd3-110">사용할 확인자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd3-110">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="0cdd3-111">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd3-111">This attribute is optional.</span></span> <span data-ttu-id="0cdd3-112">이 특성을 설정하지 않거나 빈 문자열로 설정하면 PNRP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd3-112">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0cdd3-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0cdd3-113">Child Elements</span></span>  
 <span data-ttu-id="0cdd3-114">None</span><span class="sxs-lookup"><span data-stu-id="0cdd3-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0cdd3-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0cdd3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0cdd3-116">요소</span><span class="sxs-lookup"><span data-stu-id="0cdd3-116">Element</span></span>|<span data-ttu-id="0cdd3-117">Description</span><span class="sxs-lookup"><span data-stu-id="0cdd3-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0cdd3-118">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd3-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0cdd3-119">예제</span><span class="sxs-lookup"><span data-stu-id="0cdd3-119">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0cdd3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cdd3-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0cdd3-121">바인딩</span><span class="sxs-lookup"><span data-stu-id="0cdd3-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0cdd3-122">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="0cdd3-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0cdd3-123">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="0cdd3-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="0cdd3-124">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="0cdd3-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
