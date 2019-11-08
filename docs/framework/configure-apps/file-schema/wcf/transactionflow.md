---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: f5bcd142fb2b032ea179bcbba68fee53b98d2d77
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736310"
---
# <a name="transactionflow"></a><span data-ttu-id="ffda5-101">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="ffda5-101">\<transactionFlow></span></span>
<span data-ttu-id="ffda5-102">사용자 지정 바인딩에 대한 트랜잭션 흐름 지원을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-102">Specifies transaction flow support for the custom binding.</span></span>  
  
<span data-ttu-id="ffda5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ffda5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ffda5-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="ffda5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ffda5-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="ffda5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="ffda5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="ffda5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="ffda5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="ffda5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ffda5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transactionFlow >**</span><span class="sxs-lookup"><span data-stu-id="ffda5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffda5-109">구문</span><span class="sxs-lookup"><span data-stu-id="ffda5-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffda5-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ffda5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ffda5-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffda5-112">특성</span><span class="sxs-lookup"><span data-stu-id="ffda5-112">Attributes</span></span>  
  
|<span data-ttu-id="ffda5-113">특성</span><span class="sxs-lookup"><span data-stu-id="ffda5-113">Attribute</span></span>|<span data-ttu-id="ffda5-114">설명</span><span class="sxs-lookup"><span data-stu-id="ffda5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ffda5-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="ffda5-115">transactionProtocol</span></span>|<span data-ttu-id="ffda5-116">사용할 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="ffda5-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ffda5-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="ffda5-118">-   OleTransactions</span></span><br /><span data-ttu-id="ffda5-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="ffda5-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="ffda5-120">기본값은 OleTransactions입니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="ffda5-121">이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffda5-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ffda5-122">Child Elements</span></span>  
 <span data-ttu-id="ffda5-123">없음.</span><span class="sxs-lookup"><span data-stu-id="ffda5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ffda5-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ffda5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ffda5-125">요소</span><span class="sxs-lookup"><span data-stu-id="ffda5-125">Element</span></span>|<span data-ttu-id="ffda5-126">설명</span><span class="sxs-lookup"><span data-stu-id="ffda5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffda5-127">\<binding ></span><span class="sxs-lookup"><span data-stu-id="ffda5-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="ffda5-128">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffda5-129">주의</span><span class="sxs-lookup"><span data-stu-id="ffda5-129">Remarks</span></span>  
 <span data-ttu-id="ffda5-130">이 요소를 사용하면 엔드포인트의 바인딩 설정에 들어오는 트랜잭션 흐름을 사용하거나 사용하지 않도록 설정할 수 있을 뿐 아니라 들어오는 트랜잭션에 대해 원하는 프로토콜 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="ffda5-131">이 구성 요소를 사용 하는 방법에 대 한 자세한 내용은 [ServiceModel 트랜잭션 구성](../../../wcf/feature-details/servicemodel-transaction-configuration.md) 및 [트랜잭션 흐름 사용](../../../wcf/feature-details/enabling-transaction-flow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ffda5-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ffda5-132">`OleTransactions` 프로토콜을 사용하여 엔드포인트 간에 트랜잭션을 전달할 경우 대상 엔드포인트에서 `OleTransactions` 이외의 프로토콜을 사용하여 트랜잭션을 다시 전달하려고 하면 트랜잭션 시간 제한이 상실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="ffda5-133">따라서 OleTransactions 홉 뒤의 모든 하위 수준 노드가 예상보다 늦게 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffda5-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffda5-134">참조</span><span class="sxs-lookup"><span data-stu-id="ffda5-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ffda5-135">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="ffda5-135">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="ffda5-136">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="ffda5-136">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="ffda5-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="ffda5-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ffda5-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="ffda5-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ffda5-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="ffda5-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ffda5-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ffda5-140">\<customBinding></span></span>](custombinding.md)
