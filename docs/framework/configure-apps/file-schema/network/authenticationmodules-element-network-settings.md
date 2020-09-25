---
title: <authenticationModules> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 154a73a5fe3fa9e2b6b1c9e5c462b76bdc1ba640
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201748"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="4a5b3-102">\<authenticationModules> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4a5b3-102">\<authenticationModules> Element (Network Settings)</span></span>

<span data-ttu-id="4a5b3-103">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="4a5b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a5b3-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a5b3-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4a5b3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4a5b3-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a5b3-107">특성</span><span class="sxs-lookup"><span data-stu-id="4a5b3-107">Attributes</span></span>  

 <span data-ttu-id="4a5b3-108">없음</span><span class="sxs-lookup"><span data-stu-id="4a5b3-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4a5b3-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4a5b3-109">Child Elements</span></span>  
  
|<span data-ttu-id="4a5b3-110">**요소**</span><span class="sxs-lookup"><span data-stu-id="4a5b3-110">**Element**</span></span>|<span data-ttu-id="4a5b3-111">**설명**</span><span class="sxs-lookup"><span data-stu-id="4a5b3-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4a5b3-112">add</span><span class="sxs-lookup"><span data-stu-id="4a5b3-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="4a5b3-113">응용 프로그램에 인증 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="4a5b3-114">clear</span><span class="sxs-lookup"><span data-stu-id="4a5b3-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="4a5b3-115">응용 프로그램에서 모든 인증 모듈을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="4a5b3-116">remove</span><span class="sxs-lookup"><span data-stu-id="4a5b3-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="4a5b3-117">응용 프로그램에서 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a5b3-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4a5b3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4a5b3-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="4a5b3-119">**Element**</span></span>|<span data-ttu-id="4a5b3-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="4a5b3-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4a5b3-121">system.net</span><span class="sxs-lookup"><span data-stu-id="4a5b3-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="4a5b3-122">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a5b3-123">설명</span><span class="sxs-lookup"><span data-stu-id="4a5b3-123">Remarks</span></span>  

 <span data-ttu-id="4a5b3-124">요소는 서버를 사용 하 여 `authenticationModule` 인증 프로세스를 수행 하는 인증 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="4a5b3-125">인증 모듈은 인터페이스를 구현 해야 합니다 <xref:System.Net.IAuthenticationModule> .</span><span class="sxs-lookup"><span data-stu-id="4a5b3-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4a5b3-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4a5b3-126">Configuration Files</span></span>  

 <span data-ttu-id="4a5b3-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a5b3-128">예제</span><span class="sxs-lookup"><span data-stu-id="4a5b3-128">Example</span></span>  

 <span data-ttu-id="4a5b3-129">다음 예에서는 인증 모듈을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-129">The following example enables an authentication module.</span></span> <span data-ttu-id="4a5b3-130">Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a5b3-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a5b3-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="4a5b3-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4a5b3-132">Network Settings Schema</span></span>](index.md)
