---
title: webRequestModules의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: 20a586e945a889d1fd8a8d4c5c09c8b790c56fc3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664024"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="89642-102">\<webRequestModules (네트워크 설정)에 대 한 > 요소 제거</span><span class="sxs-lookup"><span data-stu-id="89642-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="89642-103">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="89642-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="89642-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="89642-104">\<configuration></span></span>  
<span data-ttu-id="89642-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="89642-105">\<system.net></span></span>  
<span data-ttu-id="89642-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="89642-106">\<webRequestModules></span></span>  
<span data-ttu-id="89642-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="89642-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89642-108">구문</span><span class="sxs-lookup"><span data-stu-id="89642-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89642-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="89642-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89642-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89642-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89642-111">특성</span><span class="sxs-lookup"><span data-stu-id="89642-111">Attributes</span></span>  
  
|<span data-ttu-id="89642-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="89642-112">**Attribute**</span></span>|<span data-ttu-id="89642-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="89642-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="89642-114">이 웹 요청 모듈에서 처리 하는 요청의 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="89642-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89642-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="89642-115">Child Elements</span></span>  
 <span data-ttu-id="89642-116">없음</span><span class="sxs-lookup"><span data-stu-id="89642-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89642-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="89642-117">Parent Elements</span></span>  
  
|<span data-ttu-id="89642-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="89642-118">**Element**</span></span>|<span data-ttu-id="89642-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="89642-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="89642-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="89642-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="89642-121">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89642-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89642-122">설명</span><span class="sxs-lookup"><span data-stu-id="89642-122">Remarks</span></span>  
 <span data-ttu-id="89642-123">요소 `remove` 는 지정 된 URI 접두사에 대해 등록 된 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="89642-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="89642-124">`prefix` 특성의 값은 유효한 URI (예: "`http`" 또는 "`http://www.contoso.com`")의 선행 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89642-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="89642-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="89642-125">Configuration Files</span></span>  
 <span data-ttu-id="89642-126">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89642-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89642-127">예제</span><span class="sxs-lookup"><span data-stu-id="89642-127">Example</span></span>  

<span data-ttu-id="89642-128">다음 예에서는 HTTP에 대 한 기존 웹 요청 모듈을 제거한 다음에 `www.contoso.com`http 요청에 대 한 새 사용자 지정 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="89642-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89642-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="89642-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="89642-130">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="89642-130">Network Settings Schema</span></span>](index.md)
