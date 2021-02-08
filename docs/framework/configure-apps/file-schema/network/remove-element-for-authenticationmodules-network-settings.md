---
description: '자세한 정보: <remove> authenticationModules의 요소 (네트워크 설정)'
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
ms.openlocfilehash: 7c97cd20717e6e0945cf77ad6584b319120ec6a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804090"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="83402-103">authenticationModules의 \<remove> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="83402-103">\<remove> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="83402-104">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83402-104">Removes an authentication module from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="83402-105">구문</span><span class="sxs-lookup"><span data-stu-id="83402-105">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83402-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="83402-106">Attributes and Elements</span></span>  

 <span data-ttu-id="83402-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83402-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83402-108">특성</span><span class="sxs-lookup"><span data-stu-id="83402-108">Attributes</span></span>  
  
|<span data-ttu-id="83402-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="83402-109">**Attribute**</span></span>|<span data-ttu-id="83402-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="83402-110">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="83402-111">**type**</span><span class="sxs-lookup"><span data-stu-id="83402-111">**type**</span></span>|<span data-ttu-id="83402-112">제거할 인증 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83402-112">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83402-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="83402-113">Child Elements</span></span>  

 <span data-ttu-id="83402-114">없음</span><span class="sxs-lookup"><span data-stu-id="83402-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83402-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="83402-115">Parent Elements</span></span>  
  
|<span data-ttu-id="83402-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="83402-116">**Element**</span></span>|<span data-ttu-id="83402-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="83402-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83402-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="83402-118">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="83402-119">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83402-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83402-120">설명</span><span class="sxs-lookup"><span data-stu-id="83402-120">Remarks</span></span>  

 <span data-ttu-id="83402-121">요소는 구성 `remove` 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83402-121">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="83402-122">특성 값은 `type` 올바른 클래스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83402-122">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="83402-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="83402-123">Configuration Files</span></span>  

 <span data-ttu-id="83402-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83402-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83402-125">예제</span><span class="sxs-lookup"><span data-stu-id="83402-125">Example</span></span>  

 <span data-ttu-id="83402-126">다음 예에서는 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83402-126">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83402-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83402-127">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="83402-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="83402-128">Network Settings Schema</span></span>](index.md)
