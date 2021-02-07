---
description: 다음에 대해 자세히 알아보세요. <persistenceProvider>
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 60ddaf9f26f496bd7d79ccab84f84135e46963d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683556"
---
# \<persistenceProvider>

<span data-ttu-id="39aab-102">사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="39aab-103">구문</span><span class="sxs-lookup"><span data-stu-id="39aab-103">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39aab-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="39aab-104">Attributes and Elements</span></span>  

 <span data-ttu-id="39aab-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39aab-106">특성</span><span class="sxs-lookup"><span data-stu-id="39aab-106">Attributes</span></span>  
  
|<span data-ttu-id="39aab-107">attribute</span><span class="sxs-lookup"><span data-stu-id="39aab-107">Attribute</span></span>|<span data-ttu-id="39aab-108">설명</span><span class="sxs-lookup"><span data-stu-id="39aab-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39aab-109">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="39aab-109">persistenceOperationTimeout</span></span>|<span data-ttu-id="39aab-110">지속성 작업에 사용되는 제한 시간을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-110">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="39aab-111">기본값은 "00:00:30"입니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-111">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="39aab-112">형식</span><span class="sxs-lookup"><span data-stu-id="39aab-112">type</span></span>|<span data-ttu-id="39aab-113">사용할 지속성 공급자 팩터리의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-113">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39aab-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="39aab-114">Child Elements</span></span>  

 <span data-ttu-id="39aab-115">없음</span><span class="sxs-lookup"><span data-stu-id="39aab-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39aab-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="39aab-116">Parent Elements</span></span>  
  
|<span data-ttu-id="39aab-117">요소</span><span class="sxs-lookup"><span data-stu-id="39aab-117">Element</span></span>|<span data-ttu-id="39aab-118">설명</span><span class="sxs-lookup"><span data-stu-id="39aab-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="39aab-119">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-119">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39aab-120">설명</span><span class="sxs-lookup"><span data-stu-id="39aab-120">Remarks</span></span>  

 <span data-ttu-id="39aab-121">이 요소는 WCF 서비스의 상태를 serialize하는 데 사용되는 지속성 공급자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-121">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="39aab-122">이 요소는 HTTP 헤더에서 상태 정보를 전달하는 `wsHttpContextBinding`과 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39aab-122">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39aab-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39aab-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
