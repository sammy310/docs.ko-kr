---
title: webRequestModules의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: e175c70bd4932d6a8f9428e8cd9159a47df52558
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659433"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="da010-102">\<webRequestModules의 clear > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="da010-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="da010-103">응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="da010-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="da010-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="da010-104">\<configuration></span></span>  
<span data-ttu-id="da010-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="da010-105">\<system.net></span></span>  
<span data-ttu-id="da010-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="da010-106">\<webRequestModules></span></span>  
<span data-ttu-id="da010-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="da010-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da010-108">구문</span><span class="sxs-lookup"><span data-stu-id="da010-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da010-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="da010-109">Attributes and Elements</span></span>  
 <span data-ttu-id="da010-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="da010-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da010-111">특성</span><span class="sxs-lookup"><span data-stu-id="da010-111">Attributes</span></span>  
 <span data-ttu-id="da010-112">없음</span><span class="sxs-lookup"><span data-stu-id="da010-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da010-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="da010-113">Child Elements</span></span>  
 <span data-ttu-id="da010-114">없음</span><span class="sxs-lookup"><span data-stu-id="da010-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da010-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="da010-115">Parent Elements</span></span>  
  
|<span data-ttu-id="da010-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="da010-116">**Element**</span></span>|<span data-ttu-id="da010-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="da010-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="da010-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="da010-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="da010-119">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da010-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da010-120">설명</span><span class="sxs-lookup"><span data-stu-id="da010-120">Remarks</span></span>  
 <span data-ttu-id="da010-121">요소 `clear` 는 구성 파일 또는 구성 계층 구조에서 상위 수준에 정의 된 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="da010-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="da010-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="da010-122">Configuration Files</span></span>  
 <span data-ttu-id="da010-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da010-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da010-124">예제</span><span class="sxs-lookup"><span data-stu-id="da010-124">Example</span></span>  
 <span data-ttu-id="da010-125">다음 예제에서는 모든 웹 요청 모듈을 지운 다음 HTTP에 대 한 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="da010-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="da010-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="da010-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="da010-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="da010-127">Network Settings Schema</span></span>](index.md)
