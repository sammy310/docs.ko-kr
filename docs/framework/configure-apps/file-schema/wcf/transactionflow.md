---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c4e5cbac24e2c72791c2f5c0faed0703363c99e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201423"
---
# \<transactionFlow>

<span data-ttu-id="6f03d-101">사용자 지정 바인딩에 대한 트랜잭션 흐름 지원을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-101">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="6f03d-102">구문</span><span class="sxs-lookup"><span data-stu-id="6f03d-102">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f03d-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6f03d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6f03d-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f03d-105">특성</span><span class="sxs-lookup"><span data-stu-id="6f03d-105">Attributes</span></span>  
  
|<span data-ttu-id="6f03d-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6f03d-106">Attribute</span></span>|<span data-ttu-id="6f03d-107">설명</span><span class="sxs-lookup"><span data-stu-id="6f03d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f03d-108">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="6f03d-108">transactionProtocol</span></span>|<span data-ttu-id="6f03d-109">사용할 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-109">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="6f03d-110">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6f03d-111">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="6f03d-111">-   OleTransactions</span></span><br /><span data-ttu-id="6f03d-112">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="6f03d-112">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="6f03d-113">기본값은 OleTransactions입니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-113">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="6f03d-114">이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-114">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f03d-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6f03d-115">Child Elements</span></span>  

 <span data-ttu-id="6f03d-116">없음</span><span class="sxs-lookup"><span data-stu-id="6f03d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f03d-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6f03d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6f03d-118">요소</span><span class="sxs-lookup"><span data-stu-id="6f03d-118">Element</span></span>|<span data-ttu-id="6f03d-119">설명</span><span class="sxs-lookup"><span data-stu-id="6f03d-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="6f03d-120">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f03d-121">설명</span><span class="sxs-lookup"><span data-stu-id="6f03d-121">Remarks</span></span>  

 <span data-ttu-id="6f03d-122">이 요소를 사용하면 엔드포인트의 바인딩 설정에 들어오는 트랜잭션 흐름을 사용하거나 사용하지 않도록 설정할 수 있을 뿐 아니라 들어오는 트랜잭션에 대해 원하는 프로토콜 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-122">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="6f03d-123">이 구성 요소를 사용 하는 방법에 대 한 자세한 내용은 [ServiceModel 트랜잭션 구성](../../../wcf/feature-details/servicemodel-transaction-configuration.md) 및 [트랜잭션 흐름 사용](../../../wcf/feature-details/enabling-transaction-flow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f03d-123">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="6f03d-124">`OleTransactions` 프로토콜을 사용하여 엔드포인트 간에 트랜잭션을 전달할 경우 대상 엔드포인트에서 `OleTransactions` 이외의 프로토콜을 사용하여 트랜잭션을 다시 전달하려고 하면 트랜잭션 시간 제한이 상실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-124">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="6f03d-125">따라서 OleTransactions 홉 뒤의 모든 하위 수준 노드가 예상보다 늦게 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f03d-125">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f03d-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f03d-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6f03d-127">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="6f03d-127">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="6f03d-128">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="6f03d-128">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="6f03d-129">바인딩하</span><span class="sxs-lookup"><span data-stu-id="6f03d-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6f03d-130">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="6f03d-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6f03d-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="6f03d-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
