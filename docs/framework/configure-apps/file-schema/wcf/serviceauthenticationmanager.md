---
description: 다음에 대해 자세히 알아보세요. <serviceAuthenticationManager>
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: ae9c8d7f74b3ad7d0c61a77d20f38f228c695970
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786774"
---
# \<serviceAuthenticationManager>

<span data-ttu-id="7f83a-102">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f83a-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="7f83a-103">구문</span><span class="sxs-lookup"><span data-stu-id="7f83a-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f83a-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7f83a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="7f83a-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f83a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f83a-106">특성</span><span class="sxs-lookup"><span data-stu-id="7f83a-106">Attributes</span></span>  
  
|<span data-ttu-id="7f83a-107">attribute</span><span class="sxs-lookup"><span data-stu-id="7f83a-107">Attribute</span></span>|<span data-ttu-id="7f83a-108">설명</span><span class="sxs-lookup"><span data-stu-id="7f83a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f83a-109">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="7f83a-109">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="7f83a-110">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7f83a-110">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f83a-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7f83a-111">Child Elements</span></span>  

 <span data-ttu-id="7f83a-112">없음</span><span class="sxs-lookup"><span data-stu-id="7f83a-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f83a-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7f83a-113">Parent Elements</span></span>  
  
|<span data-ttu-id="7f83a-114">요소</span><span class="sxs-lookup"><span data-stu-id="7f83a-114">Element</span></span>|<span data-ttu-id="7f83a-115">설명</span><span class="sxs-lookup"><span data-stu-id="7f83a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7f83a-116">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f83a-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f83a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f83a-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
