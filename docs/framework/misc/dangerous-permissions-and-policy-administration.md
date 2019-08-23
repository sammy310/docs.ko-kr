---
title: 위험한 권한 및 정책 관리
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f79fd3e0678fc0bba0d3074904f9ce9460fc6c20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910924"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="ae7c6-102">위험한 권한 및 정책 관리</span><span class="sxs-lookup"><span data-stu-id="ae7c6-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="ae7c6-103">.NET Framework가 권한을 제공하는 보호되는 몇몇 작업은 보안 시스템의 보안을 손상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="ae7c6-104">이렇게 위험한 권한은 필요한 경우에만, 그리고 신뢰할 수 있는 코드에만 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="ae7c6-105">일반적으로 이러한 권한이 부여되면 악성 코드를 방어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae7c6-106">.NET Framework 4에서는 .NET Framework 보안 모델 및 용어에 대 한 중요 한 변경 내용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-106">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="ae7c6-107">이러한 변경 내용에 대 한 자세한 내용은 [보안 변경 내용](../../../docs/framework/security/security-changes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="ae7c6-108">위험한 권한은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="ae7c6-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="ae7c6-109">Permission</span></span>|<span data-ttu-id="ae7c6-110">잠재적 위험</span><span class="sxs-lookup"><span data-stu-id="ae7c6-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="ae7c6-111">관리 코드에서 비관리 코드를 호출하도록 허용하므로 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="ae7c6-112">이 코드는 유효성 검사가 없어도 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="ae7c6-113">잘못된 증명 정보로 보안 정책을 속일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="ae7c6-114">보안 정책을 수정하는 기능으로 보안을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="ae7c6-115">직렬화를 사용하면 접근성 메커니즘을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="ae7c6-116">자세한 내용은 [보안 및 직렬화](../../../docs/framework/misc/security-and-serialization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="ae7c6-117">현재 보안 주체를 설정하는 기능은 역할 기반 보안을 속일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="ae7c6-118">스레드 조작은 스레드와 관련된 보안 상태로 인해 위험합니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="ae7c6-119">접근성 메커니즘을 무력화하는 데 전용 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7c6-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae7c6-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae7c6-120">See also</span></span>

- [<span data-ttu-id="ae7c6-121">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="ae7c6-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
