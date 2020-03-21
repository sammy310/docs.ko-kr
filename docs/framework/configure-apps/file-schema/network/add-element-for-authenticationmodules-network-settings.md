---
title: authenticationModules의 <add> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: 4181a045079bdb455a63ebda722dd6b0daf33c4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155117"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="b83b9-102">\<인증에 대한> 요소 추가Modules (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b83b9-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="b83b9-103">응용 프로그램에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-103">Adds an authentication module to the application.</span></span>  

<span data-ttu-id="b83b9-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b83b9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b83b9-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b83b9-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="b83b9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<인증모듈>**](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b83b9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="b83b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="b83b9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b83b9-108">구문</span><span class="sxs-lookup"><span data-stu-id="b83b9-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b83b9-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b83b9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b83b9-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b83b9-111">특성</span><span class="sxs-lookup"><span data-stu-id="b83b9-111">Attributes</span></span>  
  
|<span data-ttu-id="b83b9-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="b83b9-112">**Attribute**</span></span>|<span data-ttu-id="b83b9-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="b83b9-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="b83b9-114">정규화된 형식 <xref:System.Type.FullName%2A> 이름(속성으로 표시됨)과 쉼표로 <xref:System.Reflection.Assembly.FullName%2A> 구분된 어셈블리 이름(속성으로 표시)입니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b83b9-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b83b9-115">Child Elements</span></span>  
 <span data-ttu-id="b83b9-116">없음</span><span class="sxs-lookup"><span data-stu-id="b83b9-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b83b9-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b83b9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b83b9-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="b83b9-118">**Element**</span></span>|<span data-ttu-id="b83b9-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="b83b9-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b83b9-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="b83b9-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="b83b9-121">네트워크 요청을 인증하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b83b9-122">설명</span><span class="sxs-lookup"><span data-stu-id="b83b9-122">Remarks</span></span>  
 <span data-ttu-id="b83b9-123">`add` 요소는 등록된 인증 모듈 목록의 끝에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="b83b9-124">인증 모듈은 목록에 추가된 순서대로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="b83b9-125">특성의 `type` 값은 유효한 형식 이름과 쉼표로 구분된 해당 어셈블리 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b83b9-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b83b9-126">Configuration Files</span></span>  
 <span data-ttu-id="b83b9-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b83b9-128">예제</span><span class="sxs-lookup"><span data-stu-id="b83b9-128">Example</span></span>  
 <span data-ttu-id="b83b9-129">다음 예제는 기본 인증 모듈을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="b83b9-130">버전 및 PublicKeyToken의 값을 지정된 모듈의 올바른 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b83b9-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b83b9-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b83b9-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="b83b9-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b83b9-132">Network Settings Schema</span></span>](index.md)
