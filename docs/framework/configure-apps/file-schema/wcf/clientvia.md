---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 5e62201a38dc4dc251996531a4af5f294dd2395f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151105"
---
# \<clientVia>

<span data-ttu-id="9e88d-101">전송 채널을 만들어야 하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e88d-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="9e88d-102">자세한 내용은 <xref:System.ServiceModel.Description.ClientViaBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e88d-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="9e88d-103">구문</span><span class="sxs-lookup"><span data-stu-id="9e88d-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e88d-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9e88d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="9e88d-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e88d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e88d-106">특성</span><span class="sxs-lookup"><span data-stu-id="9e88d-106">Attributes</span></span>  
  
|<span data-ttu-id="9e88d-107">attribute</span><span class="sxs-lookup"><span data-stu-id="9e88d-107">Attribute</span></span>|<span data-ttu-id="9e88d-108">설명</span><span class="sxs-lookup"><span data-stu-id="9e88d-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="9e88d-109">메시지가 이동할 경로를 나타내는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e88d-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e88d-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9e88d-110">Child Elements</span></span>  

 <span data-ttu-id="9e88d-111">없음</span><span class="sxs-lookup"><span data-stu-id="9e88d-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e88d-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9e88d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="9e88d-113">요소</span><span class="sxs-lookup"><span data-stu-id="9e88d-113">Element</span></span>|<span data-ttu-id="9e88d-114">설명</span><span class="sxs-lookup"><span data-stu-id="9e88d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9e88d-115">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e88d-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e88d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e88d-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
