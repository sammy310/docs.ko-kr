---
title: authenticationModules의 <add> 요소(네트워크 설정)
description: <add>ConnectionManagement의 네트워크 설정 요소는 .NET Framework의 연결 관리 목록에 IP 주소 또는 DNS 이름을 추가 합니다.
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
ms.openlocfilehash: f679a43ed1851e9681a2a57ca1639f8aa75aa8b3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149506"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="bd2ca-103">authenticationModules의 \<add> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="bd2ca-103">\<add> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="bd2ca-104">응용 프로그램에 인증 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-104">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="bd2ca-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd2ca-105">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd2ca-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bd2ca-106">Attributes and Elements</span></span>  

 <span data-ttu-id="bd2ca-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd2ca-108">특성</span><span class="sxs-lookup"><span data-stu-id="bd2ca-108">Attributes</span></span>  
  
|<span data-ttu-id="bd2ca-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="bd2ca-109">**Attribute**</span></span>|<span data-ttu-id="bd2ca-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="bd2ca-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="bd2ca-111">속성으로 표시 되는 정규화 된 형식 이름 <xref:System.Type.FullName%2A> 및 쉼표로 구분 된 어셈블리 이름 (속성으로 표시 됨 <xref:System.Reflection.Assembly.FullName%2A> )입니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd2ca-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bd2ca-112">Child Elements</span></span>  

 <span data-ttu-id="bd2ca-113">없음</span><span class="sxs-lookup"><span data-stu-id="bd2ca-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd2ca-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bd2ca-114">Parent Elements</span></span>  
  
|<span data-ttu-id="bd2ca-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="bd2ca-115">**Element**</span></span>|<span data-ttu-id="bd2ca-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="bd2ca-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bd2ca-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="bd2ca-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="bd2ca-118">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd2ca-119">설명</span><span class="sxs-lookup"><span data-stu-id="bd2ca-119">Remarks</span></span>  

 <span data-ttu-id="bd2ca-120">`add` 요소는 등록된 인증 모듈 목록의 끝에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-120">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="bd2ca-121">인증 모듈은 목록에 추가 된 순서 대로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-121">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="bd2ca-122">특성 값은 `type` 쉼표로 구분 된 유효한 형식 이름 및 해당 어셈블리 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-122">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bd2ca-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="bd2ca-123">Configuration Files</span></span>  

 <span data-ttu-id="bd2ca-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd2ca-125">예제</span><span class="sxs-lookup"><span data-stu-id="bd2ca-125">Example</span></span>  

 <span data-ttu-id="bd2ca-126">다음 예에서는 기본 인증 모듈을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-126">The following example enables the default authentication modules.</span></span> <span data-ttu-id="bd2ca-127">Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2ca-127">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bd2ca-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd2ca-128">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="bd2ca-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bd2ca-129">Network Settings Schema</span></span>](index.md)
