---
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
ms.openlocfilehash: 05a90c4020f225414b21e82684e46b3c2abda010
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797077"
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="3e9dd-102">방법: 사용자 지정 보안 주체 ID 만들기</span><span class="sxs-lookup"><span data-stu-id="3e9dd-102">How to: Create a Custom Principal Identity</span></span>
<span data-ttu-id="3e9dd-103"><xref:System.Security.Permissions.PrincipalPermissionAttribute>는 서비스 메서드에 대한 액세스를 제어하는 선언적 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="3e9dd-103">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="3e9dd-104">이 특성을 사용하는 경우 <xref:System.ServiceModel.Description.PrincipalPermissionMode> 열거는 권한 부여를 검사하기 위한 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9dd-104">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="3e9dd-105">이 모드를 <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>으로 설정하면 사용자가 <xref:System.Security.Principal.IPrincipal> 속성에 의해 반환된 사용자 지정 <xref:System.Threading.Thread.CurrentPrincipal%2A> 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e9dd-105">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="3e9dd-106">이 항목에서는 <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>이 사용자 지정 권한 부여 정책 및 사용자 지정 보안 주체와 함께 사용되는 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e9dd-106">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="3e9dd-107">를 사용 하 <xref:System.Security.Permissions.PrincipalPermissionAttribute> [는 방법에 대 한 자세한 내용은 방법: PrincipalPermissionAttribute 클래스](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)를 사용 하 여 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9dd-107">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e9dd-108">예제</span><span class="sxs-lookup"><span data-stu-id="3e9dd-108">Example</span></span>  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e9dd-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3e9dd-109">Compiling the Code</span></span>  
 <span data-ttu-id="3e9dd-110">코드를 컴파일하려면 다음 네임스페이스에 대한 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e9dd-110">References to the following namespaces are needed to compile the code:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3e9dd-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="3e9dd-111">See also</span></span>

- <xref:System.ServiceModel.Description.PrincipalPermissionMode>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [<span data-ttu-id="3e9dd-112">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="3e9dd-112">How to: Use the ASP.NET Role Provider with a Service</span></span>](../feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="3e9dd-113">방법: PrincipalPermissionAttribute 클래스를 사용 하 여 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="3e9dd-113">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)
