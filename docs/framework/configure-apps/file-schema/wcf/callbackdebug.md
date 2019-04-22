---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: a1190eb1c015ba07488ff5a5952f2f5f1b10974c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152271"
---
# <a name="callbackdebug"></a><span data-ttu-id="0c87c-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="0c87c-101">\<callbackDebug></span></span>
<span data-ttu-id="0c87c-102">Windows Communication Foundation (WCF) 콜백 개체에 대 한 서비스 디버깅을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c87c-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="0c87c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c87c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c87c-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0c87c-104">\<behaviors></span></span>  
<span data-ttu-id="0c87c-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0c87c-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="0c87c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0c87c-106">\<behavior></span></span>  
<span data-ttu-id="0c87c-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="0c87c-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c87c-108">구문</span><span class="sxs-lookup"><span data-stu-id="0c87c-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="0c87c-109">형식</span><span class="sxs-lookup"><span data-stu-id="0c87c-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c87c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c87c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0c87c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c87c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c87c-112">특성</span><span class="sxs-lookup"><span data-stu-id="0c87c-112">Attributes</span></span>  
  
|<span data-ttu-id="0c87c-113">특성</span><span class="sxs-lookup"><span data-stu-id="0c87c-113">Attribute</span></span>|<span data-ttu-id="0c87c-114">설명</span><span class="sxs-lookup"><span data-stu-id="0c87c-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="0c87c-115">클라이언트 콜백 개체가 관리되는 예외 정보를 SOAP 오류의 형태로 서비스에 반환하는지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0c87c-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="0c87c-116">이 특성을 프로그래밍 방식으로 `true`로 설정한 경우 클라이언트 콜백 개체에 있는 관리되는 예외 정보 흐름을 디버깅을 위해 다시 서비스로 이동하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c87c-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="0c87c-117">**주의:**  관리되는 예외 정보를 클라이언트에 반환하면 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c87c-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="0c87c-118">예외 정보가 내부 서비스 구현 정보를 공개하여 권한 없는 클라이언트에서 이를 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0c87c-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c87c-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c87c-119">Child Elements</span></span>  
 <span data-ttu-id="0c87c-120">없음</span><span class="sxs-lookup"><span data-stu-id="0c87c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c87c-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c87c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0c87c-122">요소</span><span class="sxs-lookup"><span data-stu-id="0c87c-122">Element</span></span>|<span data-ttu-id="0c87c-123">설명</span><span class="sxs-lookup"><span data-stu-id="0c87c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c87c-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0c87c-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0c87c-125">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c87c-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c87c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c87c-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
