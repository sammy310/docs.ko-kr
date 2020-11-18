---
title: Principal 개체 바꾸기
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET], replacing principal objects
- security [.NET], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: b8f7a8fbd3b9c65126d6a3a65a5f6722f2ad93de
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824176"
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="6481d-102">Principal 개체 바꾸기</span><span class="sxs-lookup"><span data-stu-id="6481d-102">Replacing a Principal Object</span></span>

<span data-ttu-id="6481d-103">인증 서비스를 제공하는 애플리케이션은 지정된 스레드에 대해 **Principal** 개체(<xref:System.Security.Principal.IPrincipal>)를 대체할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6481d-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="6481d-104">또한 보안 시스템은 **Principal** 개체를 대체하는 기능을 보호할 수 있어야 합니다. 악의적으로 연결된 잘못된 **Principal** 은 허위 ID 또는 역할을 요청함으로써 애플리케이션의 보안을 손상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6481d-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="6481d-105">따라서 **Principal** 개체를 대체할 수 있는 기능이 필요한 애플리케이션에서는 보안 주체 컨트롤에 대한 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> 개체가 허가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6481d-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="6481d-106">(이 사용 권한은 역할을 기반으로 하는 보안 검사를 수행하거나 **Principal** 개체를 만들 때는 필요하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="6481d-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
<span data-ttu-id="6481d-107">현재 **Principal** 개체는 다음과 같은 작업을 수행하여 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6481d-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="6481d-108">대체 **Principal** 개체 및 연결된 **Identity** 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6481d-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2. <span data-ttu-id="6481d-109">새 **Principal** 개체를 호출 컨텍스트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6481d-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6481d-110">예제</span><span class="sxs-lookup"><span data-stu-id="6481d-110">Example</span></span>

<span data-ttu-id="6481d-111">다음 예제에서는 일반적인 보안 주체 개체를 만들고 이 개체를 사용하여 스레드의 보안 주체를 설정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6481d-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
[!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
[!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6481d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6481d-112">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [<span data-ttu-id="6481d-113">Principal 개체 및 Identity 개체</span><span class="sxs-lookup"><span data-stu-id="6481d-113">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="6481d-114">ASP.NET Core 보안</span><span class="sxs-lookup"><span data-stu-id="6481d-114">ASP.NET Core Security</span></span>](/aspnet/core/security/)
