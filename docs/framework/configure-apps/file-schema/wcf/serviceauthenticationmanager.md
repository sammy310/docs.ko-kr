---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399704"
---
# \<serviceAuthenticationManager>
<span data-ttu-id="1a843-101">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="1a843-102">구문</span><span class="sxs-lookup"><span data-stu-id="1a843-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a843-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1a843-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1a843-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a843-105">특성</span><span class="sxs-lookup"><span data-stu-id="1a843-105">Attributes</span></span>  
  
|<span data-ttu-id="1a843-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1a843-106">Attribute</span></span>|<span data-ttu-id="1a843-107">Description</span><span class="sxs-lookup"><span data-stu-id="1a843-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a843-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="1a843-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="1a843-109">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a843-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1a843-110">Child Elements</span></span>  
 <span data-ttu-id="1a843-111">없음</span><span class="sxs-lookup"><span data-stu-id="1a843-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a843-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1a843-112">Parent Elements</span></span>  
  
|<span data-ttu-id="1a843-113">요소</span><span class="sxs-lookup"><span data-stu-id="1a843-113">Element</span></span>|<span data-ttu-id="1a843-114">Description</span><span class="sxs-lookup"><span data-stu-id="1a843-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1a843-115">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a843-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a843-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a843-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
