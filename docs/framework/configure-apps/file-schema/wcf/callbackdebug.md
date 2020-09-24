---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 02632cc3f668bb9e4cc6f8c9726d7bcb3cab2c5d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183821"
---
# \<callbackDebug>

<span data-ttu-id="484a4-101">WCF (Windows Communication Foundation) 콜백 개체에 대 한 서비스 디버깅을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-101">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="484a4-102">구문</span><span class="sxs-lookup"><span data-stu-id="484a4-102">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="484a4-103">형식</span><span class="sxs-lookup"><span data-stu-id="484a4-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="484a4-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="484a4-104">Attributes and Elements</span></span>  

 <span data-ttu-id="484a4-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="484a4-106">특성</span><span class="sxs-lookup"><span data-stu-id="484a4-106">Attributes</span></span>  
  
|<span data-ttu-id="484a4-107">attribute</span><span class="sxs-lookup"><span data-stu-id="484a4-107">Attribute</span></span>|<span data-ttu-id="484a4-108">설명</span><span class="sxs-lookup"><span data-stu-id="484a4-108">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="484a4-109">클라이언트 콜백 개체가 관리되는 예외 정보를 SOAP 오류의 형태로 서비스에 반환하는지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-109">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="484a4-110">이 특성을 프로그래밍 방식으로 `true`로 설정한 경우 클라이언트 콜백 개체에 있는 관리되는 예외 정보 흐름을 디버깅을 위해 다시 서비스로 이동하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-110">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="484a4-111">**주의:**  관리 되는 예외 정보를 클라이언트에 반환 하면 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-111">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="484a4-112">예외 정보가 내부 서비스 구현 정보를 공개하여 권한 없는 클라이언트에서 이를 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-112">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="484a4-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="484a4-113">Child Elements</span></span>  

 <span data-ttu-id="484a4-114">없음</span><span class="sxs-lookup"><span data-stu-id="484a4-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="484a4-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="484a4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="484a4-116">요소</span><span class="sxs-lookup"><span data-stu-id="484a4-116">Element</span></span>|<span data-ttu-id="484a4-117">설명</span><span class="sxs-lookup"><span data-stu-id="484a4-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="484a4-118">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-118">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="484a4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="484a4-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
