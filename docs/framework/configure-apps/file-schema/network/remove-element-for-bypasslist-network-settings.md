---
description: '자세한 정보: <remove> bypasslist 요소에 대 한 요소 (네트워크 설정)'
title: bypasslist의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 48441f1b402b339a1bd2ea069678afb4b1d5f2e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740290"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="88d0f-103">bypasslist의 \<remove> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="88d0f-103">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="88d0f-104">프록시 바이패스 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-104">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  

## <a name="syntax"></a><span data-ttu-id="88d0f-105">구문</span><span class="sxs-lookup"><span data-stu-id="88d0f-105">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="88d0f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="88d0f-106">Attributes and Elements</span></span>

<span data-ttu-id="88d0f-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="88d0f-108">특성</span><span class="sxs-lookup"><span data-stu-id="88d0f-108">Attributes</span></span>

|<span data-ttu-id="88d0f-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="88d0f-109">**Attribute**</span></span>|<span data-ttu-id="88d0f-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="88d0f-110">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="88d0f-111">IP 주소 또는 DNS 이름을 설명 하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-111">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="88d0f-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="88d0f-112">Child Elements</span></span>

<span data-ttu-id="88d0f-113">없음</span><span class="sxs-lookup"><span data-stu-id="88d0f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="88d0f-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="88d0f-114">Parent Elements</span></span>

|<span data-ttu-id="88d0f-115">**요소**</span><span class="sxs-lookup"><span data-stu-id="88d0f-115">**Element**</span></span>|<span data-ttu-id="88d0f-116">**설명**</span><span class="sxs-lookup"><span data-stu-id="88d0f-116">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="88d0f-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="88d0f-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="88d0f-118">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="88d0f-119">설명</span><span class="sxs-lookup"><span data-stu-id="88d0f-119">Remarks</span></span>

<span data-ttu-id="88d0f-120">`remove`요소는 프록시 서버를 우회 하는 주소 목록에서 IP 주소 또는 DNS 서버 이름을 설명 하는 정규식을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-120">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="88d0f-121">주소가 구성 파일에서 이전에 정의 되었거나 구성 계층 구조의 상위 수준에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-121">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="88d0f-122">특성 값은 `address` IP 주소 또는 호스트 이름 집합을 설명 하는 정규식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-122">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="88d0f-123">정규식에 대 한 자세한 내용은을 참조 하십시오. [정규식을 .NET Framework](../../../../standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-123">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="88d0f-124">구성 파일</span><span class="sxs-lookup"><span data-stu-id="88d0f-124">Configuration Files</span></span>

<span data-ttu-id="88d0f-125">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="88d0f-126">예제</span><span class="sxs-lookup"><span data-stu-id="88d0f-126">Example</span></span>

<span data-ttu-id="88d0f-127">다음 예에서는 adventure-works.com 도메인에 대 한 이전 정의를 제거 하 고 contoso.com 도메인을 바이패스 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d0f-127">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="88d0f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88d0f-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="88d0f-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="88d0f-129">Network Settings Schema</span></span>](index.md)
