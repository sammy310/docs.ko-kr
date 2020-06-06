---
title: <clear>of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400522"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="56a5b-102">\<clear>of \<claimTypeRequirements> 요소</span><span class="sxs-lookup"><span data-stu-id="56a5b-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="56a5b-103">페더레이션 자격 증명에서 제거할 모든 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="56a5b-104">이를 통해 컬렉션이 빈 상태로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="56a5b-105">구문</span><span class="sxs-lookup"><span data-stu-id="56a5b-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56a5b-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="56a5b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="56a5b-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56a5b-108">특성</span><span class="sxs-lookup"><span data-stu-id="56a5b-108">Attributes</span></span>  
 <span data-ttu-id="56a5b-109">없음</span><span class="sxs-lookup"><span data-stu-id="56a5b-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56a5b-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="56a5b-110">Child Elements</span></span>  
 <span data-ttu-id="56a5b-111">없음</span><span class="sxs-lookup"><span data-stu-id="56a5b-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56a5b-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="56a5b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="56a5b-113">요소</span><span class="sxs-lookup"><span data-stu-id="56a5b-113">Element</span></span>|<span data-ttu-id="56a5b-114">Description</span><span class="sxs-lookup"><span data-stu-id="56a5b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="56a5b-115">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="56a5b-116">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="56a5b-117">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="56a5b-118">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="56a5b-119">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56a5b-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56a5b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56a5b-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
