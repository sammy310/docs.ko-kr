---
title: bypasslist의 <clear> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: e5305d9aed09b6c4d1ad4201e5e08e007a14c7c0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664194"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="52e6f-102">\<bypasslist 요소에 대 한 clear > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="52e6f-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="52e6f-103">프록시 무시 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="52e6f-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="52e6f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="52e6f-104">\<configuration></span></span>  
<span data-ttu-id="52e6f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="52e6f-105">\<system.net></span></span>  
<span data-ttu-id="52e6f-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="52e6f-106">\<defaultProxy></span></span>  
<span data-ttu-id="52e6f-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="52e6f-107">\<bypasslist></span></span>  
<span data-ttu-id="52e6f-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="52e6f-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e6f-109">구문</span><span class="sxs-lookup"><span data-stu-id="52e6f-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52e6f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52e6f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="52e6f-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52e6f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52e6f-112">특성</span><span class="sxs-lookup"><span data-stu-id="52e6f-112">Attributes</span></span>  
 <span data-ttu-id="52e6f-113">없음</span><span class="sxs-lookup"><span data-stu-id="52e6f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52e6f-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52e6f-114">Child Elements</span></span>  
 <span data-ttu-id="52e6f-115">없음</span><span class="sxs-lookup"><span data-stu-id="52e6f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52e6f-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52e6f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="52e6f-117">**요소**</span><span class="sxs-lookup"><span data-stu-id="52e6f-117">**Element**</span></span>|<span data-ttu-id="52e6f-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="52e6f-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="52e6f-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="52e6f-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="52e6f-120">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e6f-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52e6f-121">설명</span><span class="sxs-lookup"><span data-stu-id="52e6f-121">Remarks</span></span>  
 <span data-ttu-id="52e6f-122">요소 `clear` 는 바이패스 목록에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="52e6f-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="52e6f-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="52e6f-123">Configuration Files</span></span>  
 <span data-ttu-id="52e6f-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e6f-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52e6f-125">예제</span><span class="sxs-lookup"><span data-stu-id="52e6f-125">Example</span></span>  
 <span data-ttu-id="52e6f-126">다음 예에서는 바이패스 목록을 지운 다음 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e6f-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="52e6f-127">첫 번째는 contoso.com 도메인에 있는 모든 서버에 대 한 프록시를 무시 합니다. 두 번째는 IP 주소가 192.168으로 시작 하는 모든 서버에 대해 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="52e6f-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="52e6f-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="52e6f-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="52e6f-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="52e6f-129">Network Settings Schema</span></span>](index.md)
