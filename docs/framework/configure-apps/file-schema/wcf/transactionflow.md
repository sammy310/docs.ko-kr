---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 626ae03d622221ab3e956bd03898b6cc30482c98
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179155"
---
# <a name="transactionflow"></a><span data-ttu-id="d4e2f-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="d4e2f-101">\<transactionFlow></span></span>
<span data-ttu-id="d4e2f-102">사용자 지정 바인딩에 대한 트랜잭션 흐름 지원을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="d4e2f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d4e2f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d4e2f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d4e2f-104">\<bindings></span></span>  
<span data-ttu-id="d4e2f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d4e2f-105">\<customBinding></span></span>  
<span data-ttu-id="d4e2f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d4e2f-106">\<binding></span></span>  
<span data-ttu-id="d4e2f-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="d4e2f-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e2f-108">구문</span><span class="sxs-lookup"><span data-stu-id="d4e2f-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4e2f-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d4e2f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d4e2f-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4e2f-111">특성</span><span class="sxs-lookup"><span data-stu-id="d4e2f-111">Attributes</span></span>  
  
|<span data-ttu-id="d4e2f-112">특성</span><span class="sxs-lookup"><span data-stu-id="d4e2f-112">Attribute</span></span>|<span data-ttu-id="d4e2f-113">설명</span><span class="sxs-lookup"><span data-stu-id="d4e2f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4e2f-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="d4e2f-114">transactionProtocol</span></span>|<span data-ttu-id="d4e2f-115">사용할 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="d4e2f-116">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d4e2f-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="d4e2f-117">-   OleTransactions</span></span><br /><span data-ttu-id="d4e2f-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="d4e2f-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="d4e2f-119">기본값은 OleTransactions입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="d4e2f-120">이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4e2f-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d4e2f-121">Child Elements</span></span>  
 <span data-ttu-id="d4e2f-122">없음</span><span class="sxs-lookup"><span data-stu-id="d4e2f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4e2f-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d4e2f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d4e2f-124">요소</span><span class="sxs-lookup"><span data-stu-id="d4e2f-124">Element</span></span>|<span data-ttu-id="d4e2f-125">설명</span><span class="sxs-lookup"><span data-stu-id="d4e2f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4e2f-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="d4e2f-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d4e2f-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4e2f-128">설명</span><span class="sxs-lookup"><span data-stu-id="d4e2f-128">Remarks</span></span>  
 <span data-ttu-id="d4e2f-129">이 요소를 사용하면 엔드포인트의 바인딩 설정에 들어오는 트랜잭션 흐름을 사용하거나 사용하지 않도록 설정할 수 있을 뿐 아니라 들어오는 트랜잭션에 대해 원하는 프로토콜 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="d4e2f-130">이 구성 요소 사용에 대 한 자세한 내용은 참조 하세요. [ServiceModel 트랜잭션 구성](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) 하 고 [트랜잭션 흐름 사용](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d4e2f-131">`OleTransactions` 프로토콜을 사용하여 엔드포인트 간에 트랜잭션을 전달할 경우 대상 엔드포인트에서 `OleTransactions` 이외의 프로토콜을 사용하여 트랜잭션을 다시 전달하려고 하면 트랜잭션 시간 제한이 상실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="d4e2f-132">따라서 OleTransactions 홉 뒤의 모든 하위 수준 노드가 예상보다 늦게 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4e2f-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e2f-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4e2f-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d4e2f-134">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="d4e2f-134">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="d4e2f-135">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="d4e2f-135">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="d4e2f-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="d4e2f-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d4e2f-137">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="d4e2f-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d4e2f-138">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d4e2f-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d4e2f-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d4e2f-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
