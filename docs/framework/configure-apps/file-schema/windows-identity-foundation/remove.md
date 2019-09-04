---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251924"
---
# <a name="remove"></a><span data-ttu-id="ab4e2-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="ab4e2-101">\<remove></span></span>
<span data-ttu-id="ab4e2-102">토큰 처리기 컬렉션에서 지정 된 보안 토큰 처리기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
<span data-ttu-id="ab4e2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ab4e2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ab4e2-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ab4e2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ab4e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ab4e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ab4e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="ab4e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="ab4e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 제거**</span><span class="sxs-lookup"><span data-stu-id="ab4e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab4e2-108">구문</span><span class="sxs-lookup"><span data-stu-id="ab4e2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab4e2-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ab4e2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ab4e2-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab4e2-111">특성</span><span class="sxs-lookup"><span data-stu-id="ab4e2-111">Attributes</span></span>  
  
|<span data-ttu-id="ab4e2-112">특성</span><span class="sxs-lookup"><span data-stu-id="ab4e2-112">Attribute</span></span>|<span data-ttu-id="ab4e2-113">설명</span><span class="sxs-lookup"><span data-stu-id="ab4e2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab4e2-114">type</span><span class="sxs-lookup"><span data-stu-id="ab4e2-114">type</span></span>|<span data-ttu-id="ab4e2-115">제거할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="ab4e2-116">`type` 특성을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="ab4e2-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab4e2-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ab4e2-118">Child Elements</span></span>  
 <span data-ttu-id="ab4e2-119">없음</span><span class="sxs-lookup"><span data-stu-id="ab4e2-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab4e2-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ab4e2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ab4e2-121">요소</span><span class="sxs-lookup"><span data-stu-id="ab4e2-121">Element</span></span>|<span data-ttu-id="ab4e2-122">설명</span><span class="sxs-lookup"><span data-stu-id="ab4e2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab4e2-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ab4e2-123">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="ab4e2-124">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ab4e2-125">예제</span><span class="sxs-lookup"><span data-stu-id="ab4e2-125">Example</span></span>  
 <span data-ttu-id="ab4e2-126">다음 XML에서는 `<add>` 및 `<remove>` 요소를 사용 하 여 기본 세션 토큰 처리기를 사용자 지정 세션 토큰 처리기로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="ab4e2-127">XML은 `ClaimsAwareWebFarm` 샘플에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ab4e2-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
