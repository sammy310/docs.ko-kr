---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 206a684e1279871eee4aed95a087921123f8efb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918655"
---
# <a name="transactionflow"></a><span data-ttu-id="96287-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="96287-101">\<transactionFlow></span></span>
<span data-ttu-id="96287-102">사용자 지정 바인딩에 대한 트랜잭션 흐름 지원을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96287-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="96287-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="96287-103">\<system.serviceModel></span></span>  
<span data-ttu-id="96287-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="96287-104">\<bindings></span></span>  
<span data-ttu-id="96287-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="96287-105">\<customBinding></span></span>  
<span data-ttu-id="96287-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="96287-106">\<binding></span></span>  
<span data-ttu-id="96287-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="96287-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96287-108">구문</span><span class="sxs-lookup"><span data-stu-id="96287-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96287-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="96287-109">Attributes and Elements</span></span>  
 <span data-ttu-id="96287-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96287-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96287-111">특성</span><span class="sxs-lookup"><span data-stu-id="96287-111">Attributes</span></span>  
  
|<span data-ttu-id="96287-112">특성</span><span class="sxs-lookup"><span data-stu-id="96287-112">Attribute</span></span>|<span data-ttu-id="96287-113">Description</span><span class="sxs-lookup"><span data-stu-id="96287-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96287-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="96287-114">transactionProtocol</span></span>|<span data-ttu-id="96287-115">사용할 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96287-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="96287-116">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96287-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="96287-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="96287-117">-   OleTransactions</span></span><br /><span data-ttu-id="96287-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="96287-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="96287-119">기본값은 OleTransactions입니다.</span><span class="sxs-lookup"><span data-stu-id="96287-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="96287-120">이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="96287-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96287-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="96287-121">Child Elements</span></span>  
 <span data-ttu-id="96287-122">없음</span><span class="sxs-lookup"><span data-stu-id="96287-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96287-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="96287-123">Parent Elements</span></span>  
  
|<span data-ttu-id="96287-124">요소</span><span class="sxs-lookup"><span data-stu-id="96287-124">Element</span></span>|<span data-ttu-id="96287-125">설명</span><span class="sxs-lookup"><span data-stu-id="96287-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96287-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="96287-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="96287-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="96287-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96287-128">설명</span><span class="sxs-lookup"><span data-stu-id="96287-128">Remarks</span></span>  
 <span data-ttu-id="96287-129">이 요소를 사용하면 엔드포인트의 바인딩 설정에 들어오는 트랜잭션 흐름을 사용하거나 사용하지 않도록 설정할 수 있을 뿐 아니라 들어오는 트랜잭션에 대해 원하는 프로토콜 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96287-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="96287-130">이 구성 요소를 사용 하는 방법에 대 한 자세한 내용은 [ServiceModel 트랜잭션 구성](../../../wcf/feature-details/servicemodel-transaction-configuration.md) 및 [트랜잭션 흐름 사용](../../../wcf/feature-details/enabling-transaction-flow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96287-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="96287-131">`OleTransactions` 프로토콜을 사용하여 엔드포인트 간에 트랜잭션을 전달할 경우 대상 엔드포인트에서 `OleTransactions` 이외의 프로토콜을 사용하여 트랜잭션을 다시 전달하려고 하면 트랜잭션 시간 제한이 상실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96287-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="96287-132">따라서 OleTransactions 홉 뒤의 모든 하위 수준 노드가 예상보다 늦게 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96287-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96287-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="96287-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="96287-134">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="96287-134">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="96287-135">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="96287-135">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="96287-136">바인딩</span><span class="sxs-lookup"><span data-stu-id="96287-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="96287-137">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="96287-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="96287-138">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="96287-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="96287-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="96287-139">\<customBinding></span></span>](custombinding.md)
