---
description: '다음에 대 한 자세한 정보: <clear> <claimTypeRequirements> 요소'
title: <clear> of <claimTypeRequirements> 요소
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: d25dad5afcec352f040ea4f8c08e5ffa2bc16d19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638888"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="18373-103">\<clear> of \<claimTypeRequirements> 요소</span><span class="sxs-lookup"><span data-stu-id="18373-103">\<clear> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="18373-104">페더레이션 자격 증명에서 제거할 모든 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18373-104">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="18373-105">이를 통해 컬렉션이 빈 상태로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="18373-105">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="18373-106">구문</span><span class="sxs-lookup"><span data-stu-id="18373-106">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18373-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="18373-107">Attributes and Elements</span></span>  

 <span data-ttu-id="18373-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18373-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18373-109">특성</span><span class="sxs-lookup"><span data-stu-id="18373-109">Attributes</span></span>  

 <span data-ttu-id="18373-110">없음</span><span class="sxs-lookup"><span data-stu-id="18373-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18373-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="18373-111">Child Elements</span></span>  

 <span data-ttu-id="18373-112">없음</span><span class="sxs-lookup"><span data-stu-id="18373-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18373-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="18373-113">Parent Elements</span></span>  
  
|<span data-ttu-id="18373-114">요소</span><span class="sxs-lookup"><span data-stu-id="18373-114">Element</span></span>|<span data-ttu-id="18373-115">설명</span><span class="sxs-lookup"><span data-stu-id="18373-115">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="18373-116">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18373-116">Specifies a collection of required claim types.</span></span> <span data-ttu-id="18373-117">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="18373-117">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="18373-118">페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="18373-118">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="18373-119">예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18373-119">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="18373-120">이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18373-120">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18373-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18373-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
