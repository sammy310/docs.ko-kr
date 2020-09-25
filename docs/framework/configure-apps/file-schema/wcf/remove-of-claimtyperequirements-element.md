---
title: <remove> of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 773f37156969f64f02711e6a60764aeb7e50a840
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181325"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="1a805-102">\<remove> of \<claimTypeRequirements> 요소</span><span class="sxs-lookup"><span data-stu-id="1a805-102">\<remove> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="1a805-103">페더레이션 자격 증명에서 제거할 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="1a805-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a805-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a805-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1a805-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1a805-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a805-107">특성</span><span class="sxs-lookup"><span data-stu-id="1a805-107">Attributes</span></span>  
  
|<span data-ttu-id="1a805-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1a805-108">Attribute</span></span>|<span data-ttu-id="1a805-109">설명</span><span class="sxs-lookup"><span data-stu-id="1a805-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a805-110">claimType</span><span class="sxs-lookup"><span data-stu-id="1a805-110">claimType</span></span>|<span data-ttu-id="1a805-111">제거할 클레임의 형식을 정의하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a805-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1a805-112">Child Elements</span></span>  

 <span data-ttu-id="1a805-113">없음</span><span class="sxs-lookup"><span data-stu-id="1a805-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a805-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1a805-114">Parent Elements</span></span>  
  
|<span data-ttu-id="1a805-115">요소</span><span class="sxs-lookup"><span data-stu-id="1a805-115">Element</span></span>|<span data-ttu-id="1a805-116">설명</span><span class="sxs-lookup"><span data-stu-id="1a805-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="1a805-117">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="1a805-118">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="1a805-119">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1a805-120">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1a805-121">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a805-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a805-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a805-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
