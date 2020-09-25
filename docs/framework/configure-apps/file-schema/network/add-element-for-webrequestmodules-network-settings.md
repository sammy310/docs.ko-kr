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
ms.openlocfilehash: 8d792b967d967540469dca7c090e0f905ecb2e6b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201761"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="d7573-102">webRequestModules의 \<add> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="d7573-102">\<add> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="d7573-103">응용 프로그램에 사용자 지정 웹 요청 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-103">Adds a custom Web request module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="d7573-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7573-104">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7573-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d7573-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d7573-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7573-107">특성</span><span class="sxs-lookup"><span data-stu-id="d7573-107">Attributes</span></span>  
  
|<span data-ttu-id="d7573-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="d7573-108">**Attribute**</span></span>|<span data-ttu-id="d7573-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="d7573-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="d7573-110">이 웹 요청 모듈에서 처리 하는 요청의 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-110">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="d7573-111">이 웹 요청 모듈을 구현 하는 정규화 된 형식 이름 (속성으로 표시 <xref:System.Type.FullName%2A> 됨)과 쉼표로 구분 된 어셈블리 이름 (속성으로 표시 <xref:System.Reflection.Assembly.FullName%2A> 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7573-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d7573-112">Child Elements</span></span>  

 <span data-ttu-id="d7573-113">없음</span><span class="sxs-lookup"><span data-stu-id="d7573-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7573-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d7573-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d7573-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="d7573-115">**Element**</span></span>|<span data-ttu-id="d7573-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="d7573-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d7573-117">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d7573-117">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="d7573-118">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-118">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7573-119">설명</span><span class="sxs-lookup"><span data-stu-id="d7573-119">Remarks</span></span>  

 <span data-ttu-id="d7573-120">`prefix`특성은 지정 된 웹 요청 모듈을 사용 하는 URI 접두사를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-120">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="d7573-121">웹 요청 모듈은 일반적으로 HTTP 또는 FTP와 같은 특정 프로토콜을 처리 하기 위해 등록 되지만 특정 서버 또는 서버의 경로에 대 한 요청을 처리 하도록 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-121">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="d7573-122">웹 요청 모듈은 URI 일치 접두사가 메서드에 전달 될 때 생성 됩니다 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d7573-122">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="d7573-123">특성의 값은 `prefix` 유효한 URI의 선행 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-123">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="d7573-124">예를 들어 `http` 또는 `http://www.contoso.com`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-124">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="d7573-125">특성 값은 `type` 쉼표로 구분 된 유효한 형식 이름 및 해당 어셈블리 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="d7573-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d7573-126">Configuration Files</span></span>  

 <span data-ttu-id="d7573-127">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7573-128">예제</span><span class="sxs-lookup"><span data-stu-id="d7573-128">Example</span></span>  

 <span data-ttu-id="d7573-129">다음 예제에서는 HTTP에 대 한 사용자 지정 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-129">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="d7573-130">Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7573-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d7573-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7573-131">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="d7573-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d7573-132">Network Settings Schema</span></span>](index.md)
