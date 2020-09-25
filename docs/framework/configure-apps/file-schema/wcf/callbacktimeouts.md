---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 98523489aacebf910bcf5d81c479819183887dff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198888"
---
# \<callbackTimeouts>

<span data-ttu-id="91259-101">이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91259-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="91259-102">구문</span><span class="sxs-lookup"><span data-stu-id="91259-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="91259-103">형식</span><span class="sxs-lookup"><span data-stu-id="91259-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91259-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91259-104">Attributes and Elements</span></span>  

 <span data-ttu-id="91259-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91259-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91259-106">특성</span><span class="sxs-lookup"><span data-stu-id="91259-106">Attributes</span></span>  
  
|<span data-ttu-id="91259-107">attribute</span><span class="sxs-lookup"><span data-stu-id="91259-107">Attribute</span></span>|<span data-ttu-id="91259-108">설명</span><span class="sxs-lookup"><span data-stu-id="91259-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="91259-109">트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="91259-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="91259-110">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="91259-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91259-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91259-111">Child Elements</span></span>  

 <span data-ttu-id="91259-112">없음</span><span class="sxs-lookup"><span data-stu-id="91259-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91259-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91259-113">Parent Elements</span></span>  
  
|<span data-ttu-id="91259-114">요소</span><span class="sxs-lookup"><span data-stu-id="91259-114">Element</span></span>|<span data-ttu-id="91259-115">설명</span><span class="sxs-lookup"><span data-stu-id="91259-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="91259-116">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91259-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91259-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91259-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
