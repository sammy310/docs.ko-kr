---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 7581f581c4b97a07eb4bdeb49eb5ae5ce72c2aa7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535718"
---
# \<remove>
<span data-ttu-id="b2557-101">토큰 처리기 컬렉션에서 지정 된 보안 토큰 처리기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2557-101">Removes the specified security token handler from the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="b2557-102">구문</span><span class="sxs-lookup"><span data-stu-id="b2557-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2557-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2557-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b2557-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2557-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2557-105">특성</span><span class="sxs-lookup"><span data-stu-id="b2557-105">Attributes</span></span>  
  
|<span data-ttu-id="b2557-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b2557-106">Attribute</span></span>|<span data-ttu-id="b2557-107">Description</span><span class="sxs-lookup"><span data-stu-id="b2557-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2557-108">type</span><span class="sxs-lookup"><span data-stu-id="b2557-108">type</span></span>|<span data-ttu-id="b2557-109">제거할 토큰 처리기의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2557-109">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="b2557-110">특성을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2557-110">For more information about how to specify the `type` attribute, see [Custom Type References](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="b2557-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b2557-111">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2557-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2557-112">Child Elements</span></span>  
 <span data-ttu-id="b2557-113">None</span><span class="sxs-lookup"><span data-stu-id="b2557-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2557-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2557-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b2557-115">요소</span><span class="sxs-lookup"><span data-stu-id="b2557-115">Element</span></span>|<span data-ttu-id="b2557-116">Description</span><span class="sxs-lookup"><span data-stu-id="b2557-116">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="b2557-117">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2557-117">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2557-118">예제</span><span class="sxs-lookup"><span data-stu-id="b2557-118">Example</span></span>  
 <span data-ttu-id="b2557-119">다음 XML에서는 `<add>` 및 요소를 사용 하 여 `<remove>` 기본 세션 토큰 처리기를 사용자 지정 세션 토큰 처리기로 바꾸는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2557-119">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="b2557-120">XML은 샘플에서 가져옵니다 `ClaimsAwareWebFarm` .</span><span class="sxs-lookup"><span data-stu-id="b2557-120">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
