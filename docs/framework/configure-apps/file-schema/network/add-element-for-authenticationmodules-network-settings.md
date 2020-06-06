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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155117"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="f1703-102">authenticationModules의 \<add> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="f1703-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="f1703-103">응용 프로그램에 인증 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-103">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="f1703-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1703-104">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1703-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1703-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f1703-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1703-107">특성</span><span class="sxs-lookup"><span data-stu-id="f1703-107">Attributes</span></span>  
  
|<span data-ttu-id="f1703-108">**특성**</span><span class="sxs-lookup"><span data-stu-id="f1703-108">**Attribute**</span></span>|<span data-ttu-id="f1703-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="f1703-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="f1703-110">속성으로 표시 되는 정규화 된 형식 이름 <xref:System.Type.FullName%2A> 및 쉼표로 구분 된 어셈블리 이름 (속성으로 표시 됨 <xref:System.Reflection.Assembly.FullName%2A> )입니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-110">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1703-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1703-111">Child Elements</span></span>  
 <span data-ttu-id="f1703-112">없음</span><span class="sxs-lookup"><span data-stu-id="f1703-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1703-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1703-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f1703-114">**요소**</span><span class="sxs-lookup"><span data-stu-id="f1703-114">**Element**</span></span>|<span data-ttu-id="f1703-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="f1703-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f1703-116">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="f1703-116">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="f1703-117">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-117">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1703-118">설명</span><span class="sxs-lookup"><span data-stu-id="f1703-118">Remarks</span></span>  
 <span data-ttu-id="f1703-119">`add` 요소는 등록된 인증 모듈 목록의 끝에 인증 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-119">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="f1703-120">인증 모듈은 목록에 추가 된 순서 대로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-120">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="f1703-121">특성 값은 `type` 쉼표로 구분 된 유효한 형식 이름 및 해당 어셈블리 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-121">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f1703-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f1703-122">Configuration Files</span></span>  
 <span data-ttu-id="f1703-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1703-124">예제</span><span class="sxs-lookup"><span data-stu-id="f1703-124">Example</span></span>  
 <span data-ttu-id="f1703-125">다음 예에서는 기본 인증 모듈을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-125">The following example enables the default authentication modules.</span></span> <span data-ttu-id="f1703-126">Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1703-126">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1703-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1703-127">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="f1703-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f1703-128">Network Settings Schema</span></span>](index.md)
