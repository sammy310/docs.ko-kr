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
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154935"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="bcbd2-102">\<바이패스리스트에 대한> 요소 지우기(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="bcbd2-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="bcbd2-103">프록시 바이패스 목록을 지웁습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbd2-103">Clears the proxy bypass list.</span></span>  
  
<span data-ttu-id="bcbd2-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bcbd2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bcbd2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bcbd2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="bcbd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<기본 프록시>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bcbd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="bcbd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<바이패스리스트>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bcbd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>\
<span data-ttu-id="bcbd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<클리어>**</span><span class="sxs-lookup"><span data-stu-id="bcbd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bcbd2-109">구문</span><span class="sxs-lookup"><span data-stu-id="bcbd2-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcbd2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bcbd2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bcbd2-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbd2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcbd2-112">특성</span><span class="sxs-lookup"><span data-stu-id="bcbd2-112">Attributes</span></span>  
 <span data-ttu-id="bcbd2-113">없음</span><span class="sxs-lookup"><span data-stu-id="bcbd2-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bcbd2-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bcbd2-114">Child Elements</span></span>  
 <span data-ttu-id="bcbd2-115">없음</span><span class="sxs-lookup"><span data-stu-id="bcbd2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bcbd2-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bcbd2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bcbd2-117">**요소**</span><span class="sxs-lookup"><span data-stu-id="bcbd2-117">**Element**</span></span>|<span data-ttu-id="bcbd2-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="bcbd2-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bcbd2-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="bcbd2-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="bcbd2-120">프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbd2-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcbd2-121">설명</span><span class="sxs-lookup"><span data-stu-id="bcbd2-121">Remarks</span></span>  
 <span data-ttu-id="bcbd2-122">`clear` 요소는 바이패스 목록에서 모든 항목을 지웁히 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcbd2-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bcbd2-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="bcbd2-123">Configuration Files</span></span>  
 <span data-ttu-id="bcbd2-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcbd2-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcbd2-125">예제</span><span class="sxs-lookup"><span data-stu-id="bcbd2-125">Example</span></span>  
 <span data-ttu-id="bcbd2-126">다음 예제는 바이패스 목록을 지웁히 고 다음 바이패스 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbd2-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="bcbd2-127">첫 번째는 contoso.com 도메인의 모든 서버에 대한 프록시를 무시합니다. 두 번째는 IP 주소가 192.168로 시작하는 모든 서버의 프록시를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="bcbd2-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bcbd2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcbd2-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="bcbd2-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bcbd2-129">Network Settings Schema</span></span>](index.md)
