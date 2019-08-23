---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 65488c34931f6d7c424ece58a4855e746ea455bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936419"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="9e959-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="9e959-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="9e959-102">서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e959-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="9e959-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9e959-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9e959-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9e959-104">\<behaviors></span></span>  
<span data-ttu-id="9e959-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9e959-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9e959-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9e959-106">\<behavior></span></span>  
<span data-ttu-id="9e959-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="9e959-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e959-108">구문</span><span class="sxs-lookup"><span data-stu-id="9e959-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e959-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9e959-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9e959-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e959-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e959-111">특성</span><span class="sxs-lookup"><span data-stu-id="9e959-111">Attributes</span></span>  
  
|<span data-ttu-id="9e959-112">특성</span><span class="sxs-lookup"><span data-stu-id="9e959-112">Attribute</span></span>|<span data-ttu-id="9e959-113">Description</span><span class="sxs-lookup"><span data-stu-id="9e959-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e959-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="9e959-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="9e959-115">현재 동작에 대한 인증 정책 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e959-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e959-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9e959-116">Child Elements</span></span>  
 <span data-ttu-id="9e959-117">없음</span><span class="sxs-lookup"><span data-stu-id="9e959-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e959-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9e959-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9e959-119">요소</span><span class="sxs-lookup"><span data-stu-id="9e959-119">Element</span></span>|<span data-ttu-id="9e959-120">설명</span><span class="sxs-lookup"><span data-stu-id="9e959-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e959-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9e959-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9e959-122">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e959-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e959-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e959-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
