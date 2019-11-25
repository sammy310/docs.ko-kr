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
ms.openlocfilehash: 2113b2b81ae347b398b0f25028dc6c361aec8447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089175"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="81f4e-102">authenticationModules (네트워크 설정)에 대 한 > 요소 \<제거</span><span class="sxs-lookup"><span data-stu-id="81f4e-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="81f4e-103">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="81f4e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81f4e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81f4e-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="81f4e-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="81f4e-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**authenticationModules**](authenticationmodules-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="81f4e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\</span></span>
<span data-ttu-id="81f4e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<제거 >**</span><span class="sxs-lookup"><span data-stu-id="81f4e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="81f4e-108">구문</span><span class="sxs-lookup"><span data-stu-id="81f4e-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81f4e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="81f4e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="81f4e-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81f4e-111">특성</span><span class="sxs-lookup"><span data-stu-id="81f4e-111">Attributes</span></span>  
  
|<span data-ttu-id="81f4e-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="81f4e-112">**Attribute**</span></span>|<span data-ttu-id="81f4e-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="81f4e-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="81f4e-114">**type**</span><span class="sxs-lookup"><span data-stu-id="81f4e-114">**type**</span></span>|<span data-ttu-id="81f4e-115">제거할 인증 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81f4e-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="81f4e-116">Child Elements</span></span>  
 <span data-ttu-id="81f4e-117">없음.</span><span class="sxs-lookup"><span data-stu-id="81f4e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81f4e-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="81f4e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="81f4e-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="81f4e-119">**Element**</span></span>|<span data-ttu-id="81f4e-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="81f4e-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="81f4e-121">Authenticationmodules></span><span class="sxs-lookup"><span data-stu-id="81f4e-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="81f4e-122">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81f4e-123">주의</span><span class="sxs-lookup"><span data-stu-id="81f4e-123">Remarks</span></span>  
 <span data-ttu-id="81f4e-124">`remove` 요소는 구성 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="81f4e-125">`type` 특성에 대 한 값은 올바른 클래스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="81f4e-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="81f4e-126">Configuration Files</span></span>  
 <span data-ttu-id="81f4e-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81f4e-128">예제</span><span class="sxs-lookup"><span data-stu-id="81f4e-128">Example</span></span>  
 <span data-ttu-id="81f4e-129">다음 예에서는 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f4e-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81f4e-130">참조</span><span class="sxs-lookup"><span data-stu-id="81f4e-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="81f4e-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="81f4e-131">Network Settings Schema</span></span>](index.md)
