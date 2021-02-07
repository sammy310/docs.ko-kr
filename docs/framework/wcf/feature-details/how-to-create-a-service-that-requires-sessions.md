---
description: '자세한 정보: 방법: 세션이 필요한 서비스 만들기'
title: '방법: 세션이 필요한 서비스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: 362aee23437bb7f45af5a265a9d3ef47bf62915c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734466"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="94849-103">방법: 세션이 필요한 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="94849-103">How to: Create a Service That Requires Sessions</span></span>

<span data-ttu-id="94849-104">세션은 콜백, 다중 홉 보안 및 클라이언트와 서비스 인스턴스 간의 연결과 같은 유용한 기능을 사용하는 둘 이상의 엔드포인트 사이에서 공유 상태를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="94849-104">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> <span data-ttu-id="94849-105">WCF (Windows Communication Foundation) 응용 프로그램의 세션에 대 한 자세한 내용은 [세션 사용](../using-sessions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="94849-105">For more information about sessions in Windows Communication Foundation (WCF) applications, see [Using Sessions](../using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="94849-106">계약에서 바인딩이 세션을 지원하도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="94849-106">To specify that a contract require its binding to support sessions</span></span>  
  
1. <span data-ttu-id="94849-107">작업을 하나 이상 포함하는 서비스 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="94849-107">Create a service contract with at least one operation.</span></span> <span data-ttu-id="94849-108">서비스 계약을 만드는 방법에 대 한 예제는 [방법: 서비스 계약 정의](../how-to-define-a-wcf-service-contract.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="94849-108">For an example of how to create a service contract, see [How to: Define a Service Contract](../how-to-define-a-wcf-service-contract.md).</span></span>  
  
2. <span data-ttu-id="94849-109"><xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> 속성을 다음으로 설정하여 계약을 선언하는 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="94849-109">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    - <span data-ttu-id="94849-110">이 계약을 세션 내에서 실행해야 하는 경우, <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="94849-110"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    - <span data-ttu-id="94849-111">이 계약을 세션 내에서 실행할 수 있는 경우, <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="94849-111"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    - <span data-ttu-id="94849-112">이 계약을 세션 내에서 실행하지 않아야 하는 경우, <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="94849-112"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3. <span data-ttu-id="94849-113">세션을 지원하는 바인딩을 사용하도록 서비스 엔드포인트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="94849-113">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="94849-114">다음 구성 예제에서는 WS<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>ReliableMessaging 세션을 지원하는 `-`을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94849-114">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="example"></a><span data-ttu-id="94849-115">예제</span><span class="sxs-lookup"><span data-stu-id="94849-115">Example</span></span>  

 <span data-ttu-id="94849-116">다음 예제 코드에서는 계약 수준 세션 요구 사항을 지정하고 구성 파일을 사용하여 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 바인딩을 통해 해당 요구 사항을 지원하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94849-116">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="see-also"></a><span data-ttu-id="94849-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94849-117">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
