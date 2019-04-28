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
ms.openlocfilehash: 4c1116c088c12ad3859714c8d75704d0156c12f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705144"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="b1f73-102">\<추가 > webRequestModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="b1f73-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="b1f73-103">응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="b1f73-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b1f73-104">\<configuration></span></span>  
<span data-ttu-id="b1f73-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b1f73-105">\<system.net></span></span>  
<span data-ttu-id="b1f73-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="b1f73-106">\<webRequestModules></span></span>  
<span data-ttu-id="b1f73-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b1f73-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1f73-108">구문</span><span class="sxs-lookup"><span data-stu-id="b1f73-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1f73-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b1f73-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1f73-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1f73-111">특성</span><span class="sxs-lookup"><span data-stu-id="b1f73-111">Attributes</span></span>  
  
|<span data-ttu-id="b1f73-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="b1f73-112">**Attribute**</span></span>|<span data-ttu-id="b1f73-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="b1f73-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="b1f73-114">이 웹 요청 모듈에서 처리 하는 요청에 대 한 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="b1f73-115">정규화 된 형식 이름을 (나타난 합니다 <xref:System.Type.FullName%2A> 속성)와 어셈블리 이름 (나타난는 <xref:System.Reflection.Assembly.FullName%2A> 속성)이 웹 요청 모듈을 구현 하는 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1f73-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b1f73-116">Child Elements</span></span>  
 <span data-ttu-id="b1f73-117">없음</span><span class="sxs-lookup"><span data-stu-id="b1f73-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1f73-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b1f73-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b1f73-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="b1f73-119">**Element**</span></span>|<span data-ttu-id="b1f73-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="b1f73-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b1f73-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="b1f73-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="b1f73-122">네트워크 호스트에서 정보를 요청 하는 데는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1f73-123">설명</span><span class="sxs-lookup"><span data-stu-id="b1f73-123">Remarks</span></span>  
 <span data-ttu-id="b1f73-124">`prefix` 특성은 지정된 된 웹 요청 모듈을 사용 하는 URI 접두사를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="b1f73-125">웹 요청 모듈은 일반적으로 HTTP 또는 FTP와 같은 특정 프로토콜을 처리 하도록 등록 되어 있지만 특정 서버 또는 서버의 경로 요청을 처리 하도록 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="b1f73-126">URI 일치 하는 접두사를 전달 되 면 웹 요청 모듈 만들어집니다는 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="b1f73-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="b1f73-127">에 대 한 값을 `prefix` 특성에는 유효한 URI의 선행 문자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="b1f73-128">예를 들어 `http` 또는 `http://www.contoso.com`로 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="b1f73-129">에 대 한 값을 `type` 특성은 유효한 형식 이름 및 쉼표로 구분 하 여 해당 어셈블리 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="b1f73-130">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b1f73-130">Configuration Files</span></span>  
 <span data-ttu-id="b1f73-131">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1f73-132">예제</span><span class="sxs-lookup"><span data-stu-id="b1f73-132">Example</span></span>  
 <span data-ttu-id="b1f73-133">다음 예제에서는 HTTP에 대 한 사용자 지정 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="b1f73-134">지정된 된 모듈에 대 한 올바른 값을 사용 하 여 PublicKeyToken 및 버전에 대 한 값을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f73-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b1f73-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1f73-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="b1f73-136">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b1f73-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
