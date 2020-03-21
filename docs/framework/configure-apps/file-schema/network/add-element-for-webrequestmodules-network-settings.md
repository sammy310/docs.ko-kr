---
title: webRequestModules의 <add> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155026"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="d4b45-102">\<웹 요청 모듈에 대한> 요소 추가 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="d4b45-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="d4b45-103">응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-103">Adds a custom Web request module to the application.</span></span>  

<span data-ttu-id="d4b45-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4b45-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4b45-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d4b45-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d4b45-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<웹 리퍼모듈>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d4b45-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="d4b45-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="d4b45-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d4b45-108">구문</span><span class="sxs-lookup"><span data-stu-id="d4b45-108">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4b45-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d4b45-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d4b45-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4b45-111">특성</span><span class="sxs-lookup"><span data-stu-id="d4b45-111">Attributes</span></span>  
  
|<span data-ttu-id="d4b45-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="d4b45-112">**Attribute**</span></span>|<span data-ttu-id="d4b45-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="d4b45-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="d4b45-114">이 웹 요청 모듈에서 처리하는 요청에 대한 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="d4b45-115">이 웹 요청 모듈을 <xref:System.Type.FullName%2A> 구현하는 쉼표로 구분된 정규화된 형식 이름(속성으로 표시됨)과 어셈블리 <xref:System.Reflection.Assembly.FullName%2A> 이름(속성으로 표시됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4b45-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d4b45-116">Child Elements</span></span>  
 <span data-ttu-id="d4b45-117">없음</span><span class="sxs-lookup"><span data-stu-id="d4b45-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4b45-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d4b45-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d4b45-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="d4b45-119">**Element**</span></span>|<span data-ttu-id="d4b45-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="d4b45-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d4b45-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d4b45-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="d4b45-122">네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4b45-123">설명</span><span class="sxs-lookup"><span data-stu-id="d4b45-123">Remarks</span></span>  
 <span data-ttu-id="d4b45-124">특성은 `prefix` 지정된 웹 요청 모듈을 사용하는 URI 접두사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="d4b45-125">웹 요청 모듈은 일반적으로 HTTP 또는 FTP와 같은 특정 프로토콜을 처리하도록 등록되지만 서버의 특정 서버 또는 경로에 대한 요청을 처리하도록 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="d4b45-126">웹 요청 모듈은 URI 일치 접두사가 메서드에 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 전달될 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="d4b45-127">특성의 `prefix` 값은 유효한 URI의 선행 문자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="d4b45-128">예를 들어 `http` 또는 `http://www.contoso.com`입니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="d4b45-129">특성의 `type` 값은 유효한 형식 이름과 쉼표로 구분된 해당 어셈블리 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="d4b45-130">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d4b45-130">Configuration Files</span></span>  
 <span data-ttu-id="d4b45-131">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4b45-132">예제</span><span class="sxs-lookup"><span data-stu-id="d4b45-132">Example</span></span>  
 <span data-ttu-id="d4b45-133">다음 예제는 HTTP에 대한 사용자 지정 웹 요청 모듈을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="d4b45-134">버전 및 PublicKeyToken의 값을 지정된 모듈의 올바른 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4b45-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4b45-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4b45-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="d4b45-136">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d4b45-136">Network Settings Schema</span></span>](index.md)
