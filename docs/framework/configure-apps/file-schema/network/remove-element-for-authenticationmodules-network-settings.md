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
ms.openlocfilehash: d171fea193bbae068e69b8976abb8e56a5623f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154779"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="cb00a-102">\<인증에 대한> 요소 제거Modules (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="cb00a-102">\<remove> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="cb00a-103">응용 프로그램에서 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-103">Removes an authentication module from the application.</span></span>  

<span data-ttu-id="cb00a-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cb00a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cb00a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cb00a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="cb00a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<인증모듈>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cb00a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="cb00a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>제거**</span><span class="sxs-lookup"><span data-stu-id="cb00a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cb00a-108">구문</span><span class="sxs-lookup"><span data-stu-id="cb00a-108">Syntax</span></span>  
  
```xml  
<remove
   type="authentication module name"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb00a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cb00a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cb00a-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb00a-111">특성</span><span class="sxs-lookup"><span data-stu-id="cb00a-111">Attributes</span></span>  
  
|<span data-ttu-id="cb00a-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="cb00a-112">**Attribute**</span></span>|<span data-ttu-id="cb00a-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="cb00a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="cb00a-114">**종류**</span><span class="sxs-lookup"><span data-stu-id="cb00a-114">**type**</span></span>|<span data-ttu-id="cb00a-115">제거할 인증 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb00a-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cb00a-116">Child Elements</span></span>  
 <span data-ttu-id="cb00a-117">없음</span><span class="sxs-lookup"><span data-stu-id="cb00a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb00a-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cb00a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cb00a-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="cb00a-119">**Element**</span></span>|<span data-ttu-id="cb00a-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="cb00a-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cb00a-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="cb00a-121">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="cb00a-122">네트워크 요청을 인증하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb00a-123">설명</span><span class="sxs-lookup"><span data-stu-id="cb00a-123">Remarks</span></span>  
 <span data-ttu-id="cb00a-124">요소는 `remove` 구성 파일의 이전 또는 구성 계층 구조의 상위 수준에서 정의된 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="cb00a-125">특성의 `type` 값은 유효한 클래스 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cb00a-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="cb00a-126">Configuration Files</span></span>  
 <span data-ttu-id="cb00a-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb00a-128">예제</span><span class="sxs-lookup"><span data-stu-id="cb00a-128">Example</span></span>  
 <span data-ttu-id="cb00a-129">다음 예제는 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cb00a-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb00a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb00a-130">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="cb00a-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="cb00a-131">Network Settings Schema</span></span>](index.md)
