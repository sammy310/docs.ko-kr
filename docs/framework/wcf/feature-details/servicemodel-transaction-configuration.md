---
title: ServiceModel 트랜잭션 구성
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: 27deaf38a8809b8a7fca560cc6783bd24dc43686
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242892"
---
# <a name="servicemodel-transaction-configuration"></a><span data-ttu-id="ec0a3-102">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="ec0a3-102">ServiceModel Transaction Configuration</span></span>

<span data-ttu-id="ec0a3-103">WCF (Windows Communication Foundation)는 서비스에 대 한 트랜잭션 구성에, 및의 세 가지 특성 `transactionFlow` 을 제공 `transactionProtocol` `transactionTimeout` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-103">Windows Communication Foundation (WCF) provides three attributes for configuring transactions for a service: `transactionFlow`, `transactionProtocol`, and `transactionTimeout`.</span></span>  
  
## <a name="configuring-transactionflow"></a><span data-ttu-id="ec0a3-104">transactionFlow 구성</span><span class="sxs-lookup"><span data-stu-id="ec0a3-104">Configuring transactionFlow</span></span>  

 <span data-ttu-id="ec0a3-105">WCF에서 제공 하는 미리 정의 된 바인딩 대부분은 `transactionFlow` 및 `transactionProtocol` 특성을 포함 하므로 특정 트랜잭션 흐름 프로토콜을 사용 하 여 특정 끝점에 대 한 들어오는 트랜잭션을 허용 하도록 바인딩을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-105">Most of the predefined bindings WCF provides contain the `transactionFlow` and `transactionProtocol` attributes, so that you can configure the binding to accept incoming transactions for a specific endpoint using a specific transaction flow protocol.</span></span> <span data-ttu-id="ec0a3-106">또한 `transactionFlow` 요소와 해당 `transactionProtocol` 특성을 사용하여 고유의 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-106">In addition, you can use the `transactionFlow` element and its `transactionProtocol` attribute to build your own custom binding.</span></span> <span data-ttu-id="ec0a3-107">구성 요소를 설정 하는 방법에 대 한 자세한 내용은 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 및 [WCF 구성 스키마](../../configure-apps/file-schema/wcf/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-107">For more information about setting the configuration elements, see [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) and [WCF Configuration Schema](../../configure-apps/file-schema/wcf/index.md).</span></span>  
  
 <span data-ttu-id="ec0a3-108">ph x="1" /&gt; 특성은 바인딩을 사용하는 서비스 엔드포인트에 대해 트랜잭션 흐름을 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-108">The `transactionFlow` attribute specifies whether transaction flow is enabled for service endpoints that use the binding.</span></span>  
  
## <a name="configuring-transactionprotocol"></a><span data-ttu-id="ec0a3-109">transactionProtocol 구성</span><span class="sxs-lookup"><span data-stu-id="ec0a3-109">Configuring transactionProtocol</span></span>  

 <span data-ttu-id="ec0a3-110">ph x="1" /&gt; 특성은 바인딩을 사용하는 서비스 엔드포인트에서 사용할 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-110">The `transactionProtocol` attribute specifies the transaction protocol to use with service endpoints that use the binding.</span></span>  
  
 <span data-ttu-id="ec0a3-111">다음은 지정된 바인딩에서 WS-AtomicTransaction 프로토콜을 사용하고 트랜잭션 흐름을 지원하도록 구성하는 구성 섹션의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-111">The following is an example of a configuration section that configures the specified binding to support transaction flow, as well as a use the WS-AtomicTransaction protocol.</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding name="test"  
      closeTimeout="00:00:10"  
      openTimeout="00:00:20"
      receiveTimeout="00:00:30"  
      sendTimeout="00:00:40"  
      transactionFlow="true"  
      transactionProtocol="WSAtomicTransactionOctober2004"  
      hostNameComparisonMode="WeakWildcard"  
      maxBufferSize="1001"  
      maxConnections="123"
      maxReceivedMessageSize="1000">  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="configuring-transactiontimeout"></a><span data-ttu-id="ec0a3-112">transactionTimeout 구성</span><span class="sxs-lookup"><span data-stu-id="ec0a3-112">Configuring transactionTimeout</span></span>  

 <span data-ttu-id="ec0a3-113">`transactionTimeout`구성 파일의 요소에서 WCF 서비스에 대 한 특성을 구성할 수 있습니다 `behavior` .</span><span class="sxs-lookup"><span data-stu-id="ec0a3-113">You can configure the `transactionTimeout` attribute for your WCF service in the `behavior` element of the configuration file.</span></span> <span data-ttu-id="ec0a3-114">다음 코드에서는 이 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-114">The following code demonstrates how to do this.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ec0a3-115">`transactionTimeout` 특성은 서비스에서 만들어진 새 트랜잭션이 완료되어야 하는 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-115">The `transactionTimeout` attribute specifies the time period within which a new transaction created at the service must complete.</span></span> <span data-ttu-id="ec0a3-116">새 트랜잭션을 설정하는 작업에 대한 <xref:System.Transactions.TransactionScope> 시간 제한으로 사용됩니다. <xref:System.ServiceModel.OperationBehaviorAttribute>가 적용되면 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 속성이 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-116">It is used as the <xref:System.Transactions.TransactionScope> time-out for any operation that establishes a new transaction, and if <xref:System.ServiceModel.OperationBehaviorAttribute> is applied, the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="ec0a3-117">시간 제한은 트랜잭션을 만든 시점으로부터 2단계 커밋 프로토콜의 1단계를 완료할 때까지의 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-117">The time-out specifies the duration of time from the creation of the transaction to the completion of phase 1 in the two-phase commit protocol.</span></span>  
  
 <span data-ttu-id="ec0a3-118">`service` 구성 섹션에 이 특성이 설정되어 있으면 <xref:System.ServiceModel.OperationBehaviorAttribute>를 사용하여 해당 서비스에 대한 하나 이상의 메서드를 적용해야 합니다. 여기서 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 속성은 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-118">If this attribute is set within a `service` configuration section, you should apply at least one method of the corresponding service with <xref:System.ServiceModel.OperationBehaviorAttribute>, in which the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="ec0a3-119">이 `transactionTimeout` 구성 설정과 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> 속성 사이에서 더 작은 값이 시간 제한 값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec0a3-119">Note that the time-out value used is the smaller value between this `transactionTimeout` configuration setting and any <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0a3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec0a3-120">See also</span></span>

- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)
- [<span data-ttu-id="ec0a3-121">WCF 구성 스키마</span><span class="sxs-lookup"><span data-stu-id="ec0a3-121">WCF Configuration Schema</span></span>](../../configure-apps/file-schema/wcf/index.md)
