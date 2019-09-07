---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400564"
---
# <a name="callbackdebug"></a><span data-ttu-id="12676-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="12676-101">\<callbackDebug></span></span>
<span data-ttu-id="12676-102">WCF (Windows Communication Foundation) 콜백 개체에 대 한 서비스 디버깅을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12676-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
<span data-ttu-id="12676-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="12676-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="12676-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="12676-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="12676-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="12676-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="12676-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="12676-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="12676-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="12676-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="12676-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<callbackDebug >**</span><span class="sxs-lookup"><span data-stu-id="12676-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12676-109">구문</span><span class="sxs-lookup"><span data-stu-id="12676-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="12676-110">형식</span><span class="sxs-lookup"><span data-stu-id="12676-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12676-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="12676-111">Attributes and Elements</span></span>  
 <span data-ttu-id="12676-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12676-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12676-113">특성</span><span class="sxs-lookup"><span data-stu-id="12676-113">Attributes</span></span>  
  
|<span data-ttu-id="12676-114">특성</span><span class="sxs-lookup"><span data-stu-id="12676-114">Attribute</span></span>|<span data-ttu-id="12676-115">Description</span><span class="sxs-lookup"><span data-stu-id="12676-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="12676-116">클라이언트 콜백 개체가 관리되는 예외 정보를 SOAP 오류의 형태로 서비스에 반환하는지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="12676-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="12676-117">이 특성을 프로그래밍 방식으로 `true`로 설정한 경우 클라이언트 콜백 개체에 있는 관리되는 예외 정보 흐름을 디버깅을 위해 다시 서비스로 이동하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12676-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="12676-118">**주의:**  관리되는 예외 정보를 클라이언트에 반환하면 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12676-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="12676-119">예외 정보가 내부 서비스 구현 정보를 공개하여 권한 없는 클라이언트에서 이를 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="12676-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12676-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="12676-120">Child Elements</span></span>  
 <span data-ttu-id="12676-121">없음</span><span class="sxs-lookup"><span data-stu-id="12676-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12676-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="12676-122">Parent Elements</span></span>  
  
|<span data-ttu-id="12676-123">요소</span><span class="sxs-lookup"><span data-stu-id="12676-123">Element</span></span>|<span data-ttu-id="12676-124">설명</span><span class="sxs-lookup"><span data-stu-id="12676-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12676-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="12676-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="12676-126">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12676-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12676-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="12676-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
