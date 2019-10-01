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
ms.openlocfilehash: 95a190dac3a9512b404a054c60c48de9c4574790
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698337"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="3e3a8-102">webRequestModules의 \<clear > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="3e3a8-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="3e3a8-103">응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-103">Removes all registered Web request modules from the application.</span></span>  
  
[<span data-ttu-id="3e3a8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3e3a8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3e3a8-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3e3a8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="3e3a8-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3e3a8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="3e3a8-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="3e3a8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e3a8-108">구문</span><span class="sxs-lookup"><span data-stu-id="3e3a8-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e3a8-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3e3a8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3e3a8-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e3a8-111">특성</span><span class="sxs-lookup"><span data-stu-id="3e3a8-111">Attributes</span></span>  
 <span data-ttu-id="3e3a8-112">없음</span><span class="sxs-lookup"><span data-stu-id="3e3a8-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3e3a8-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3e3a8-113">Child Elements</span></span>  
 <span data-ttu-id="3e3a8-114">없음</span><span class="sxs-lookup"><span data-stu-id="3e3a8-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e3a8-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3e3a8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3e3a8-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="3e3a8-116">**Element**</span></span>|<span data-ttu-id="3e3a8-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="3e3a8-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3e3a8-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="3e3a8-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="3e3a8-119">네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e3a8-120">설명</span><span class="sxs-lookup"><span data-stu-id="3e3a8-120">Remarks</span></span>  
 <span data-ttu-id="3e3a8-121">@No__t-0 요소는 구성 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 등록 된 모든 웹 요청 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3e3a8-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="3e3a8-122">Configuration Files</span></span>  
 <span data-ttu-id="3e3a8-123">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e3a8-124">예제</span><span class="sxs-lookup"><span data-stu-id="3e3a8-124">Example</span></span>  
 <span data-ttu-id="3e3a8-125">다음 예제에서는 모든 웹 요청 모듈을 지운 다음 HTTP에 대 한 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3a8-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3e3a8-126">참조</span><span class="sxs-lookup"><span data-stu-id="3e3a8-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="3e3a8-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3e3a8-127">Network Settings Schema</span></span>](index.md)
