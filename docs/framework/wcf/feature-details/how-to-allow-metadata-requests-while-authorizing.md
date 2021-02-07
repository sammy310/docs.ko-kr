---
description: '자세히 알아보기: 방법: 권한 부여 하는 동안 메타 데이터 요청 허용'
title: '방법: 권한을 부여하는 동안 메타데이터 요청 허용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: a9f5ab7db73aaa8a2a420a60c3172f1b1a738fb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742747"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="edaf5-103">방법: 권한을 부여하는 동안 메타데이터 요청 허용</span><span class="sxs-lookup"><span data-stu-id="edaf5-103">How To: Allow Metadata Requests While Authorizing</span></span>

<span data-ttu-id="edaf5-104">사용자 지정 인증을 수행하는 동안 메타데이터를 처리하도록 요청을 허용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-104">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="edaf5-105">다음 항목에서는 이러한 요청의 유효성을 검사하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-105">The following topic walks through the steps to validate such a request.</span></span>  
  
 <span data-ttu-id="edaf5-106">WCF (Windows Communication Foundation) 권한 부여에 대 한 자세한 내용은 [권한 부여](authorization-in-wcf.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="edaf5-106">For more information about Windows Communication Foundation (WCF) authorization, see [Authorization](authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="edaf5-107">권한을 부여하는 동안 메타데이터 요청을 허용하려면</span><span class="sxs-lookup"><span data-stu-id="edaf5-107">To allow metadata requests during authorization</span></span>  
  
1. <span data-ttu-id="edaf5-108"><xref:System.ServiceModel.ServiceAuthorizationManager> 클래스의 확장을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-108">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2. <span data-ttu-id="edaf5-109"><xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-109">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="edaf5-110">메서드는 권한 부여가 허용되는지 여부에 따라 `true` 또는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-110">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="edaf5-111">현재 프로시저에 대한 정보는 매개 변수로서 메서드에 전달된 <xref:System.ServiceModel.OperationContext>에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-111">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3. <span data-ttu-id="edaf5-112">재정의하는 동안 다음 예제에서처럼 계약 이름, 네임스페이스 및 작업을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-112">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="edaf5-113">조건이 올바른 경우 `true.`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-113">If the conditions are valid, then return `true.`</span></span>  
  
4. <span data-ttu-id="edaf5-114">확장성 지점을 사용하여 클래스를 채택합니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-114">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="edaf5-115">자세한 내용은 [방법: 서비스에 대 한 사용자 지정 권한 부여 관리자 만들기](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="edaf5-115">For more information, see [How to: Create a Custom Authorization Manager for a Service](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="edaf5-116">예제</span><span class="sxs-lookup"><span data-stu-id="edaf5-116">Example</span></span>  

 <span data-ttu-id="edaf5-117">다음 예제에서는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드의 재정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edaf5-117">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="edaf5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edaf5-118">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="edaf5-119">권한 부여</span><span class="sxs-lookup"><span data-stu-id="edaf5-119">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="edaf5-120">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="edaf5-120">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
