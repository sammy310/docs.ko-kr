---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 11aeed0277fc13cbd9a65232311bd575a4a81ff7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942578"
---
# <a name="remove"></a><span data-ttu-id="f3b1a-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="f3b1a-101">\<remove></span></span>
<span data-ttu-id="f3b1a-102">토큰 처리기 컬렉션에서 지정 된 보안 토큰 처리기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="f3b1a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f3b1a-103">\<system.identityModel></span></span>  
<span data-ttu-id="f3b1a-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f3b1a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f3b1a-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f3b1a-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f3b1a-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="f3b1a-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b1a-107">구문</span><span class="sxs-lookup"><span data-stu-id="f3b1a-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3b1a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f3b1a-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3b1a-110">특성</span><span class="sxs-lookup"><span data-stu-id="f3b1a-110">Attributes</span></span>  
  
|<span data-ttu-id="f3b1a-111">특성</span><span class="sxs-lookup"><span data-stu-id="f3b1a-111">Attribute</span></span>|<span data-ttu-id="f3b1a-112">Description</span><span class="sxs-lookup"><span data-stu-id="f3b1a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3b1a-113">type</span><span class="sxs-lookup"><span data-stu-id="f3b1a-113">type</span></span>|<span data-ttu-id="f3b1a-114">제거할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="f3b1a-115">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="f3b1a-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3b1a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-117">Child Elements</span></span>  
 <span data-ttu-id="f3b1a-118">없음</span><span class="sxs-lookup"><span data-stu-id="f3b1a-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3b1a-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f3b1a-120">요소</span><span class="sxs-lookup"><span data-stu-id="f3b1a-120">Element</span></span>|<span data-ttu-id="f3b1a-121">Description</span><span class="sxs-lookup"><span data-stu-id="f3b1a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3b1a-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f3b1a-122">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="f3b1a-123">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f3b1a-124">예제</span><span class="sxs-lookup"><span data-stu-id="f3b1a-124">Example</span></span>  
 <span data-ttu-id="f3b1a-125">다음 XML에서는 `<add>` 및 `<remove>` 요소를 사용 하 여 기본 세션 토큰 처리기를 사용자 지정 세션 토큰 처리기로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="f3b1a-126">XML은 `ClaimsAwareWebFarm` 샘플에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3b1a-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
