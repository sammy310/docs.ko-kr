---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735947"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="0a6b8-101">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="0a6b8-101">\<useManagedPresentation></span></span>
<span data-ttu-id="0a6b8-102">WS-TRUST의 CardSpace 프로필을 지 원하는 CardSpace 보안 토큰 서비스와 통신 하는 데 사용 되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0a6b8-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="0a6b8-103">이 요소는 특성이 없고 빈 스위치로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6b8-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="0a6b8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a6b8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a6b8-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="0a6b8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0a6b8-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="0a6b8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="0a6b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="0a6b8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="0a6b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="0a6b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0a6b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**useManagedPresentation >**</span><span class="sxs-lookup"><span data-stu-id="0a6b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a6b8-110">구문</span><span class="sxs-lookup"><span data-stu-id="0a6b8-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a6b8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0a6b8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0a6b8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6b8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a6b8-113">특성</span><span class="sxs-lookup"><span data-stu-id="0a6b8-113">Attributes</span></span>  
 <span data-ttu-id="0a6b8-114">없음.</span><span class="sxs-lookup"><span data-stu-id="0a6b8-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a6b8-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0a6b8-115">Child Elements</span></span>  
 <span data-ttu-id="0a6b8-116">없음</span><span class="sxs-lookup"><span data-stu-id="0a6b8-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a6b8-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0a6b8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0a6b8-118">요소</span><span class="sxs-lookup"><span data-stu-id="0a6b8-118">Element</span></span>|<span data-ttu-id="0a6b8-119">설명</span><span class="sxs-lookup"><span data-stu-id="0a6b8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a6b8-120">\<binding ></span><span class="sxs-lookup"><span data-stu-id="0a6b8-120">\<binding></span></span>](bindings.md)|<span data-ttu-id="0a6b8-121">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6b8-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a6b8-122">주의</span><span class="sxs-lookup"><span data-stu-id="0a6b8-122">Remarks</span></span>  
 <span data-ttu-id="0a6b8-123">이 요소는 ID 공급자가 정책에서 WS-Trust의 CardSpace 프로필을 지원함을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a6b8-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="0a6b8-124">이러한 정책 어설션을 게시 하는 id 공급자는 해당 CardSpace 프로필을 기반으로 토큰을 발급할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6b8-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6b8-125">참조</span><span class="sxs-lookup"><span data-stu-id="0a6b8-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0a6b8-126">바인딩</span><span class="sxs-lookup"><span data-stu-id="0a6b8-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0a6b8-127">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="0a6b8-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0a6b8-128">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="0a6b8-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0a6b8-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0a6b8-129">\<customBinding></span></span>](custombinding.md)
