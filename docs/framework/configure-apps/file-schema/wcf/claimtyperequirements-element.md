---
title: <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: b4d8479dd9a24774afbd0549caf9e261f55fa147
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926153"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="a90e9-102">\<claimTypeRequirements > 요소</span><span class="sxs-lookup"><span data-stu-id="a90e9-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="a90e9-103">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a90e9-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="a90e9-104">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="a90e9-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="a90e9-105">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a90e9-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="a90e9-106">이 컬렉션의 각 자식 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a90e9-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="a90e9-107">클레임 형식 요구 사항은 발급된 토큰에서 해당 클레임 형식이 필수적인지 선택적인지를 나타내는 부울 매개 변수와 함께 발급된 토큰에서 요청된 클레임 형식의 URI로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a90e9-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90e9-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="a90e9-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a90e9-109">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="a90e9-109">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a90e9-110">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="a90e9-110">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a90e9-111">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="a90e9-111">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a90e9-112">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="a90e9-112">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a90e9-113">\<add></span><span class="sxs-lookup"><span data-stu-id="a90e9-113">\<add></span></span>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="a90e9-114">바인딩</span><span class="sxs-lookup"><span data-stu-id="a90e9-114">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a90e9-115">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="a90e9-115">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a90e9-116">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="a90e9-116">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a90e9-117">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a90e9-117">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="a90e9-118">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="a90e9-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="a90e9-119">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="a90e9-119">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
