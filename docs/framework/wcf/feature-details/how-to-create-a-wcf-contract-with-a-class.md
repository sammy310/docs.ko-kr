---
title: '방법: 클래스를 사용 하 여 Windows Communication Foundation 계약 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: a514134ed0af3b691a2e66720f81594a51747b6f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089525"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="133a4-102">방법: 클래스를 사용 하 여 Windows Communication Foundation 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="133a4-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="133a4-103">Windows Communication Foundation (WCF) 계약을 만드는 인터페이스를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="133a4-104">자세한 내용은 [방법: 서비스 계약 정의](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="133a4-105">또는 다음에 요약한 대로 클래스를 만든 후 <xref:System.ServiceModel.ServiceContractAttribute> 특성을 직접 해당 클래스에 적용하고 <xref:System.ServiceModel.OperationContractAttribute> 특성을 계약의 일부인 클래스의 각 메서드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  `[ServiceContract]` <span data-ttu-id="133a4-106">및 `[ServiceContractAttribute]` 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-106">and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="133a4-107">동일한 작업에 대 한 참인 `[OperationContract]` 고 `[OperationContractAttribute]`입니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="133a4-108">각 경우 전자가 후자 보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="133a4-109">서비스 계약에 대 한 자세한 내용은 참조 하세요. [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="133a4-110">클래스를 사용하여 Windows Communication Foundation 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="133a4-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="133a4-111">Visual Basic을 사용 하 여 새 클래스를 만듭니다 C#, 또는 기타 공용 언어 런타임 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="133a4-112">이 클래스에 <xref:System.ServiceModel.ServiceContractAttribute> 클래스를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="133a4-113">클래스에 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="133a4-114">적용 된 <xref:System.ServiceModel.OperationContractAttribute> 고 공개 WCF 계약의 일부로 노출 해야 하는 각 메서드에 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="133a4-115">예제</span><span class="sxs-lookup"><span data-stu-id="133a4-115">Example</span></span>  
 <span data-ttu-id="133a4-116">다음 코드 예제에서는 서비스 계약을 정의하는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="133a4-117"><xref:System.ServiceModel.OperationContractAttribute> 클래스가 적용된 메서드는 기본적으로 요청-회신 메시지 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="133a4-118">이 메시지 패턴에 대 한 자세한 내용은 참조 하세요. [방법: 요청-회신 계약을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="133a4-119">특성의 속성을 설정하여 다른 메시지 패턴을 만들고 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="133a4-120">추가 예제는 [방법: 단방향 계약을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) 고 [방법: 이중 계약 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="133a4-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133a4-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="133a4-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
