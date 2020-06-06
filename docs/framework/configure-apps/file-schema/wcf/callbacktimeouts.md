---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398193"
---
# \<callbackTimeouts>
<span data-ttu-id="c67c1-101">이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c67c1-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="c67c1-102">구문</span><span class="sxs-lookup"><span data-stu-id="c67c1-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="c67c1-103">Type</span><span class="sxs-lookup"><span data-stu-id="c67c1-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c67c1-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c67c1-104">Attributes and Elements</span></span>  
 <span data-ttu-id="c67c1-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c67c1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c67c1-106">특성</span><span class="sxs-lookup"><span data-stu-id="c67c1-106">Attributes</span></span>  
  
|<span data-ttu-id="c67c1-107">attribute</span><span class="sxs-lookup"><span data-stu-id="c67c1-107">Attribute</span></span>|<span data-ttu-id="c67c1-108">Description</span><span class="sxs-lookup"><span data-stu-id="c67c1-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="c67c1-109">트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c67c1-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="c67c1-110">기본값은 "00:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="c67c1-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c67c1-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c67c1-111">Child Elements</span></span>  
 <span data-ttu-id="c67c1-112">없음</span><span class="sxs-lookup"><span data-stu-id="c67c1-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c67c1-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c67c1-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c67c1-114">요소</span><span class="sxs-lookup"><span data-stu-id="c67c1-114">Element</span></span>|<span data-ttu-id="c67c1-115">Description</span><span class="sxs-lookup"><span data-stu-id="c67c1-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c67c1-116">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c67c1-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c67c1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c67c1-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
