---
title: authenticationModules의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 9b73c0dc1fe161616c08ef0501241d55e9fea9bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697936"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="46d1f-102">@no__t-authenticationModules의 > 요소 제거 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="46d1f-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="46d1f-103">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-103">Removes an authentication module from the application.</span></span>  
  
[<span data-ttu-id="46d1f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="46d1f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="46d1f-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="46d1f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="46d1f-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="46d1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="46d1f-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="46d1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d1f-108">구문</span><span class="sxs-lookup"><span data-stu-id="46d1f-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46d1f-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="46d1f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="46d1f-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46d1f-111">특성</span><span class="sxs-lookup"><span data-stu-id="46d1f-111">Attributes</span></span>  
  
|<span data-ttu-id="46d1f-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="46d1f-112">**Attribute**</span></span>|<span data-ttu-id="46d1f-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="46d1f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="46d1f-114">**type**</span><span class="sxs-lookup"><span data-stu-id="46d1f-114">**type**</span></span>|<span data-ttu-id="46d1f-115">제거할 인증 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46d1f-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="46d1f-116">Child Elements</span></span>  
 <span data-ttu-id="46d1f-117">없음</span><span class="sxs-lookup"><span data-stu-id="46d1f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46d1f-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="46d1f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="46d1f-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="46d1f-119">**Element**</span></span>|<span data-ttu-id="46d1f-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="46d1f-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="46d1f-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="46d1f-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="46d1f-122">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46d1f-123">설명</span><span class="sxs-lookup"><span data-stu-id="46d1f-123">Remarks</span></span>  
 <span data-ttu-id="46d1f-124">@No__t-0 요소는 구성 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="46d1f-125">@No__t-0 특성의 값은 올바른 클래스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="46d1f-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="46d1f-126">Configuration Files</span></span>  
 <span data-ttu-id="46d1f-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46d1f-128">예제</span><span class="sxs-lookup"><span data-stu-id="46d1f-128">Example</span></span>  
 <span data-ttu-id="46d1f-129">다음 예에서는 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d1f-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46d1f-130">참조</span><span class="sxs-lookup"><span data-stu-id="46d1f-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="46d1f-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="46d1f-131">Network Settings Schema</span></span>](index.md)
