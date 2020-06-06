---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735947"
---
# \<useManagedPresentation>
<span data-ttu-id="30d3f-101">WS-Trust의 CardSpace 프로필을 지원하는 CardSpace 보안 토큰 서비스와 통신하는 데 사용되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="30d3f-101">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="30d3f-102">이 요소는 특성이 없고 빈 스위치로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="30d3f-102">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="30d3f-103">구문</span><span class="sxs-lookup"><span data-stu-id="30d3f-103">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30d3f-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="30d3f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="30d3f-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30d3f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30d3f-106">특성</span><span class="sxs-lookup"><span data-stu-id="30d3f-106">Attributes</span></span>  
 <span data-ttu-id="30d3f-107">없음</span><span class="sxs-lookup"><span data-stu-id="30d3f-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="30d3f-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="30d3f-108">Child Elements</span></span>  
 <span data-ttu-id="30d3f-109">None</span><span class="sxs-lookup"><span data-stu-id="30d3f-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30d3f-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="30d3f-110">Parent Elements</span></span>  
  
|<span data-ttu-id="30d3f-111">요소</span><span class="sxs-lookup"><span data-stu-id="30d3f-111">Element</span></span>|<span data-ttu-id="30d3f-112">Description</span><span class="sxs-lookup"><span data-stu-id="30d3f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="30d3f-113">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="30d3f-113">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30d3f-114">설명</span><span class="sxs-lookup"><span data-stu-id="30d3f-114">Remarks</span></span>  
 <span data-ttu-id="30d3f-115">이 요소는 ID 공급자가 정책에서 WS-Trust의 CardSpace 프로필을 지원함을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30d3f-115">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="30d3f-116">그러한 정책 어설션을 게시하는 ID 공급자는 해당 CardSpace 프로필을 기반으로 토큰을 발급할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d3f-116">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d3f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30d3f-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="30d3f-118">바인딩</span><span class="sxs-lookup"><span data-stu-id="30d3f-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="30d3f-119">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="30d3f-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="30d3f-120">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="30d3f-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
