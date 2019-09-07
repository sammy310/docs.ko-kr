---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399704"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="e959b-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="e959b-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="e959b-102">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e959b-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="e959b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e959b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e959b-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e959b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e959b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e959b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e959b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e959b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e959b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e959b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e959b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<r >**</span><span class="sxs-lookup"><span data-stu-id="e959b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e959b-109">구문</span><span class="sxs-lookup"><span data-stu-id="e959b-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e959b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e959b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e959b-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e959b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e959b-112">특성</span><span class="sxs-lookup"><span data-stu-id="e959b-112">Attributes</span></span>  
  
|<span data-ttu-id="e959b-113">특성</span><span class="sxs-lookup"><span data-stu-id="e959b-113">Attribute</span></span>|<span data-ttu-id="e959b-114">설명</span><span class="sxs-lookup"><span data-stu-id="e959b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e959b-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="e959b-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="e959b-116">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e959b-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e959b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e959b-117">Child Elements</span></span>  
 <span data-ttu-id="e959b-118">없음</span><span class="sxs-lookup"><span data-stu-id="e959b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e959b-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e959b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e959b-120">요소</span><span class="sxs-lookup"><span data-stu-id="e959b-120">Element</span></span>|<span data-ttu-id="e959b-121">설명</span><span class="sxs-lookup"><span data-stu-id="e959b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e959b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e959b-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e959b-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e959b-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e959b-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="e959b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
