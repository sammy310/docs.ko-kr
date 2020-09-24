---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: a7c1e06c74bd3ba62d52ef833b8ffb6a8fd594fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167173"
---
# \<serviceAuthenticationManager>

<span data-ttu-id="a600c-101">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a600c-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="a600c-102">구문</span><span class="sxs-lookup"><span data-stu-id="a600c-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a600c-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a600c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a600c-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a600c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a600c-105">특성</span><span class="sxs-lookup"><span data-stu-id="a600c-105">Attributes</span></span>  
  
|<span data-ttu-id="a600c-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a600c-106">Attribute</span></span>|<span data-ttu-id="a600c-107">설명</span><span class="sxs-lookup"><span data-stu-id="a600c-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a600c-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="a600c-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="a600c-109">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a600c-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a600c-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a600c-110">Child Elements</span></span>  

 <span data-ttu-id="a600c-111">없음</span><span class="sxs-lookup"><span data-stu-id="a600c-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a600c-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a600c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a600c-113">요소</span><span class="sxs-lookup"><span data-stu-id="a600c-113">Element</span></span>|<span data-ttu-id="a600c-114">설명</span><span class="sxs-lookup"><span data-stu-id="a600c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a600c-115">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a600c-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a600c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a600c-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
