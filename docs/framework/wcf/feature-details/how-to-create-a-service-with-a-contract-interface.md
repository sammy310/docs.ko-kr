---
title: '방법: Contract 인터페이스를 사용하여 서비스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: 2234e6fe8d0ee2e0029a061ba96ef84f840f0c9b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286346"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="5ce74-102">방법: Contract 인터페이스를 사용하여 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="5ce74-102">How to: Create a Service with a Contract Interface</span></span>

<span data-ttu-id="5ce74-103">WCF (Windows Communication Foundation) 계약을 만드는 기본 방법은 인터페이스를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-103">The preferred way to create a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="5ce74-104">이 계약은 서비스에서 제공하는 작업에 액세스하는 데 필요한 메시지 컬렉션과 구조를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="5ce74-105">이 인터페이스는 <xref:System.ServiceModel.ServiceContractAttribute> 클래스를 인터페이스에 적용하고 <xref:System.ServiceModel.OperationContractAttribute> 클래스를 노출할 메서드에 적용하여 입력 및 출력 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="5ce74-106">서비스 계약에 대 한 자세한 내용은 [서비스 계약 디자인](../designing-service-contracts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ce74-106">For more information about service contracts, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="5ce74-107">인터페이스로 WCF 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="5ce74-107">Creating a WCF contract with an interface</span></span>  
  
1. <span data-ttu-id="5ce74-108">Visual Basic, c # 또는 기타 공용 언어 런타임 언어를 사용 하 여 새 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="5ce74-109">인터페이스에 <xref:System.ServiceModel.ServiceContractAttribute> 클래스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3. <span data-ttu-id="5ce74-110">인터페이스에 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-110">Define the methods in the interface.</span></span>  
  
4. <span data-ttu-id="5ce74-111"><xref:System.ServiceModel.OperationContractAttribute>공용 WCF 계약의 일부로 노출 되어야 하는 각 메서드에 클래스를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ce74-112">예제</span><span class="sxs-lookup"><span data-stu-id="5ce74-112">Example</span></span>  

 <span data-ttu-id="5ce74-113">다음 코드 예제에서는 서비스 계약을 정의하는 인터페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="5ce74-114"><xref:System.ServiceModel.OperationContractAttribute> 클래스가 적용된 메서드는 기본적으로 요청-회신 메시지 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="5ce74-115">이 메시지 패턴에 대 한 자세한 내용은 [방법: Request-Reply 계약 만들기](how-to-create-a-request-reply-contract.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ce74-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="5ce74-116">특성의 속성을 설정하여 다른 메시지 패턴을 만들고 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ce74-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="5ce74-117">더 많은 예제 [는 방법: One-Way 계약 만들기](how-to-create-a-one-way-contract.md) 및 [방법: 이중 계약 만들기](how-to-create-a-duplex-contract.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ce74-117">For more examples, see [How to: Create a One-Way Contract](how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce74-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ce74-118">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
