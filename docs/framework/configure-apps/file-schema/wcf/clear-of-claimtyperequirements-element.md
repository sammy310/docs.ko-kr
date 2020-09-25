---
title: <clear> of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: aa94a012da11bcec6fb5fe270ad9f3574f88e6d7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172907"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="1b167-102">\<clear> of \<claimTypeRequirements> 요소</span><span class="sxs-lookup"><span data-stu-id="1b167-102">\<clear> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="1b167-103">페더레이션 자격 증명에서 제거할 모든 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="1b167-104">이를 통해 컬렉션이 빈 상태로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="1b167-105">구문</span><span class="sxs-lookup"><span data-stu-id="1b167-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b167-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1b167-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1b167-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b167-108">특성</span><span class="sxs-lookup"><span data-stu-id="1b167-108">Attributes</span></span>  

 <span data-ttu-id="1b167-109">없음</span><span class="sxs-lookup"><span data-stu-id="1b167-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1b167-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1b167-110">Child Elements</span></span>  

 <span data-ttu-id="1b167-111">없음</span><span class="sxs-lookup"><span data-stu-id="1b167-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b167-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1b167-112">Parent Elements</span></span>  
  
|<span data-ttu-id="1b167-113">요소</span><span class="sxs-lookup"><span data-stu-id="1b167-113">Element</span></span>|<span data-ttu-id="1b167-114">설명</span><span class="sxs-lookup"><span data-stu-id="1b167-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="1b167-115">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="1b167-116">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="1b167-117">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1b167-118">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1b167-119">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b167-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b167-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b167-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
