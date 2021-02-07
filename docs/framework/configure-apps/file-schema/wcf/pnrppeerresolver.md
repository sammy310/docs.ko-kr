---
description: 다음에 대해 자세히 알아보세요. <pnrpPeerResolver>
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 4af6a63312fa300cfa33e578f01b8e07267ad3a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683543"
---
# \<pnrpPeerResolver>

<span data-ttu-id="daa14-102">PNRP(피어 이름 확인 프로토콜)가 확인자로 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="daa14-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="daa14-103">PNRP가 기본 확인자이므로 이 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="daa14-103">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="daa14-104">구문</span><span class="sxs-lookup"><span data-stu-id="daa14-104">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="daa14-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="daa14-105">Attributes and Elements</span></span>  

 <span data-ttu-id="daa14-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="daa14-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="daa14-107">특성</span><span class="sxs-lookup"><span data-stu-id="daa14-107">Attributes</span></span>  
  
|<span data-ttu-id="daa14-108">attribute</span><span class="sxs-lookup"><span data-stu-id="daa14-108">Attribute</span></span>|<span data-ttu-id="daa14-109">설명</span><span class="sxs-lookup"><span data-stu-id="daa14-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="daa14-110">resolverType</span><span class="sxs-lookup"><span data-stu-id="daa14-110">resolverType</span></span>|<span data-ttu-id="daa14-111">사용할 확인자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="daa14-111">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="daa14-112">이 특성은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="daa14-112">This attribute is optional.</span></span> <span data-ttu-id="daa14-113">이 특성을 설정하지 않거나 빈 문자열로 설정하면 PNRP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="daa14-113">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="daa14-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="daa14-114">Child Elements</span></span>  

 <span data-ttu-id="daa14-115">없음</span><span class="sxs-lookup"><span data-stu-id="daa14-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="daa14-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="daa14-116">Parent Elements</span></span>  
  
|<span data-ttu-id="daa14-117">요소</span><span class="sxs-lookup"><span data-stu-id="daa14-117">Element</span></span>|<span data-ttu-id="daa14-118">설명</span><span class="sxs-lookup"><span data-stu-id="daa14-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="daa14-119">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="daa14-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="daa14-120">예제</span><span class="sxs-lookup"><span data-stu-id="daa14-120">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="daa14-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="daa14-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="daa14-122">바인딩</span><span class="sxs-lookup"><span data-stu-id="daa14-122">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="daa14-123">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="daa14-123">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="daa14-124">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="daa14-124">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="daa14-125">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="daa14-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
