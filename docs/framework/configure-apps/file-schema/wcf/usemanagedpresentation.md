---
description: 다음에 대해 자세히 알아보세요. <useManagedPresentation>
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 9203daedcc0553c7a1308b2763b9e818ca6560c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749040"
---
# \<useManagedPresentation>

<span data-ttu-id="68d11-102">WS-Trust의 CardSpace 프로필을 지원하는 CardSpace 보안 토큰 서비스와 통신하는 데 사용되는 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="68d11-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="68d11-103">이 요소는 특성이 없고 빈 스위치로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="68d11-103">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="68d11-104">구문</span><span class="sxs-lookup"><span data-stu-id="68d11-104">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68d11-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="68d11-105">Attributes and Elements</span></span>  

 <span data-ttu-id="68d11-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68d11-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68d11-107">특성</span><span class="sxs-lookup"><span data-stu-id="68d11-107">Attributes</span></span>  

 <span data-ttu-id="68d11-108">없음</span><span class="sxs-lookup"><span data-stu-id="68d11-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="68d11-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="68d11-109">Child Elements</span></span>  

 <span data-ttu-id="68d11-110">없음</span><span class="sxs-lookup"><span data-stu-id="68d11-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68d11-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="68d11-111">Parent Elements</span></span>  
  
|<span data-ttu-id="68d11-112">요소</span><span class="sxs-lookup"><span data-stu-id="68d11-112">Element</span></span>|<span data-ttu-id="68d11-113">설명</span><span class="sxs-lookup"><span data-stu-id="68d11-113">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="68d11-114">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="68d11-114">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68d11-115">설명</span><span class="sxs-lookup"><span data-stu-id="68d11-115">Remarks</span></span>  

 <span data-ttu-id="68d11-116">이 요소는 ID 공급자가 정책에서 WS-Trust의 CardSpace 프로필을 지원함을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68d11-116">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="68d11-117">그러한 정책 어설션을 게시하는 ID 공급자는 해당 CardSpace 프로필을 기반으로 토큰을 발급할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68d11-117">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d11-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68d11-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="68d11-119">바인딩</span><span class="sxs-lookup"><span data-stu-id="68d11-119">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="68d11-120">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="68d11-120">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="68d11-121">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="68d11-121">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
