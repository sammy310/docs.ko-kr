---
title: <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: b4d8479dd9a24774afbd0549caf9e261f55fa147
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "69926153"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="0fa05-102">\<claimTypeRequirements> 요소</span><span class="sxs-lookup"><span data-stu-id="0fa05-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="0fa05-103">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa05-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="0fa05-104">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa05-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="0fa05-105">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa05-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="0fa05-106">이 컬렉션의 각 자식 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa05-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="0fa05-107">클레임 형식 요구 사항은 발급된 토큰에서 해당 클레임 형식이 필수적인지 선택적인지를 나타내는 부울 매개 변수와 함께 발급된 토큰에서 요청된 클레임 형식의 URI로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fa05-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa05-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fa05-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0fa05-109">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="0fa05-109">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0fa05-110">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0fa05-110">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0fa05-111">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="0fa05-111">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="0fa05-112">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0fa05-112">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="0fa05-113">바인딩</span><span class="sxs-lookup"><span data-stu-id="0fa05-113">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0fa05-114">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="0fa05-114">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0fa05-115">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="0fa05-115">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="0fa05-116">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="0fa05-116">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="0fa05-117">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="0fa05-117">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
