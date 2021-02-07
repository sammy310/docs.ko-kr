---
description: '자세히 알아보기: 방법: 사용자 지정 보안 주체 Id 만들기'
title: '방법: 사용자 지정 보안 주체 ID 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
ms.openlocfilehash: 0967257021ba6cdb68426dfa48f9078afe1256fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743683"
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="7faa6-103">방법: 사용자 지정 보안 주체 ID 만들기</span><span class="sxs-lookup"><span data-stu-id="7faa6-103">How to: Create a Custom Principal Identity</span></span>

<span data-ttu-id="7faa6-104"><xref:System.Security.Permissions.PrincipalPermissionAttribute>는 서비스 메서드에 대한 액세스를 제어하는 선언적 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="7faa6-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="7faa6-105">이 특성을 사용하는 경우 <xref:System.ServiceModel.Description.PrincipalPermissionMode> 열거는 권한 부여를 검사하기 위한 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7faa6-105">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="7faa6-106">이 모드를 <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>으로 설정하면 사용자가 <xref:System.Security.Principal.IPrincipal> 속성에 의해 반환된 사용자 지정 <xref:System.Threading.Thread.CurrentPrincipal%2A> 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7faa6-106">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="7faa6-107">이 항목에서는 <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>이 사용자 지정 권한 부여 정책 및 사용자 지정 보안 주체와 함께 사용되는 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7faa6-107">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="7faa6-108">를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Security.Permissions.PrincipalPermissionAttribute> [방법: PrincipalPermissionAttribute 클래스를 사용 하 여 액세스 제한](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7faa6-108">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7faa6-109">예제</span><span class="sxs-lookup"><span data-stu-id="7faa6-109">Example</span></span>  

 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7faa6-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7faa6-110">Compiling the Code</span></span>  

 <span data-ttu-id="7faa6-111">코드를 컴파일하려면 다음 네임스페이스에 대한 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7faa6-111">References to the following namespaces are needed to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.Collections.Generic>  
  
- <xref:System.Security.Permissions>  
  
- <xref:System.Security.Principal>  
  
- <xref:System.Threading>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Description>  
  
- <xref:System.IdentityModel.Claims>  
  
- <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a><span data-ttu-id="7faa6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7faa6-112">See also</span></span>

- <xref:System.ServiceModel.Description.PrincipalPermissionMode>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [<span data-ttu-id="7faa6-113">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="7faa6-113">How to: Use the ASP.NET Role Provider with a Service</span></span>](../feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="7faa6-114">방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="7faa6-114">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)
