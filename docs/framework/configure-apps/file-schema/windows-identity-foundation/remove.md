---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251924"
---
# \<remove>
<span data-ttu-id="13672-101">토큰 처리기 컬렉션에서 지정 된 보안 토큰 처리기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13672-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="13672-102">구문</span><span class="sxs-lookup"><span data-stu-id="13672-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13672-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="13672-103">Attributes and Elements</span></span>  
 <span data-ttu-id="13672-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13672-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13672-105">특성</span><span class="sxs-lookup"><span data-stu-id="13672-105">Attributes</span></span>  
  
|<span data-ttu-id="13672-106">attribute</span><span class="sxs-lookup"><span data-stu-id="13672-106">Attribute</span></span>|<span data-ttu-id="13672-107">Description</span><span class="sxs-lookup"><span data-stu-id="13672-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13672-108">type</span><span class="sxs-lookup"><span data-stu-id="13672-108">type</span></span>|<span data-ttu-id="13672-109">제거할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="13672-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="13672-110">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13672-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="13672-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="13672-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13672-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="13672-112">Child Elements</span></span>  
 <span data-ttu-id="13672-113">None</span><span class="sxs-lookup"><span data-stu-id="13672-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13672-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="13672-114">Parent Elements</span></span>  
  
|<span data-ttu-id="13672-115">요소</span><span class="sxs-lookup"><span data-stu-id="13672-115">Element</span></span>|<span data-ttu-id="13672-116">Description</span><span class="sxs-lookup"><span data-stu-id="13672-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="13672-117">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13672-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="13672-118">예제</span><span class="sxs-lookup"><span data-stu-id="13672-118">Example</span></span>  
 <span data-ttu-id="13672-119">다음 XML에서는 `<add>` 및 요소를 사용 하 여 `<remove>` 기본 세션 토큰 처리기를 사용자 지정 세션 토큰 처리기로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13672-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="13672-120">XML은 샘플에서 가져옵니다 `ClaimsAwareWebFarm` .</span><span class="sxs-lookup"><span data-stu-id="13672-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
