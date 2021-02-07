---
description: '다음에 대 한 자세한 정보: <ipv6> 요소 (네트워크 설정)'
title: <ipv6> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 667acaebdb290140f67ea36020bb191cd1a44f34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698650"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="b92c2-103">\<ipv6> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b92c2-103">\<ipv6> Element (Network Settings)</span></span>

<span data-ttu-id="b92c2-104">클래스의 사용 되지 않는 멤버에서 IPv6 (인터넷 프로토콜 버전 6) 응답을 사용 하도록 설정 <xref:System.Net.Dns> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-104">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="b92c2-105">구문</span><span class="sxs-lookup"><span data-stu-id="b92c2-105">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b92c2-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b92c2-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b92c2-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b92c2-108">특성</span><span class="sxs-lookup"><span data-stu-id="b92c2-108">Attributes</span></span>  
  
|<span data-ttu-id="b92c2-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="b92c2-109">**Attribute**</span></span>|<span data-ttu-id="b92c2-110">**설명**</span><span class="sxs-lookup"><span data-stu-id="b92c2-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="b92c2-111">클래스의 멤버가 <xref:System.Net.Dns> IPv6 (인터넷 프로토콜 버전 6) 주소를 반환 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-111">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="b92c2-112">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-112">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b92c2-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b92c2-113">Child Elements</span></span>  

 <span data-ttu-id="b92c2-114">없음</span><span class="sxs-lookup"><span data-stu-id="b92c2-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b92c2-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b92c2-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b92c2-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="b92c2-116">**Element**</span></span>|<span data-ttu-id="b92c2-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="b92c2-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b92c2-118">설정</span><span class="sxs-lookup"><span data-stu-id="b92c2-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="b92c2-119"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b92c2-120">설명</span><span class="sxs-lookup"><span data-stu-id="b92c2-120">Remarks</span></span>  

 <span data-ttu-id="b92c2-121">이 설정은,,,,, 및 클래스의 사용 되지 않는 멤버에 대 한 IPv6 지원을 사용 하도록 설정 <xref:System.Net.Dns> <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndGetHostByName%2A> <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.GetHostByAddress%2A> <xref:System.Net.Dns.GetHostByName%2A> <xref:System.Net.Dns.Resolve%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-121">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="b92c2-122">네임 스페이스의 다른 구성원의 경우 ipv6 <xref:System.Net?displayProperty=nameWithType> 주소가 운영 체제에서 사용 하도록 설정 된 경우 ipv6 주소가 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-122">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b92c2-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b92c2-123">Configuration Files</span></span>  

 <span data-ttu-id="b92c2-124">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92c2-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b92c2-125">예제</span><span class="sxs-lookup"><span data-stu-id="b92c2-125">Example</span></span>  

 <span data-ttu-id="b92c2-126">다음 예제에서는 클래스에 대 한 IPv6 지원을 사용 하도록 설정 하는 방법을 보여 줍니다 <xref:System.Net.Dns> .</span><span class="sxs-lookup"><span data-stu-id="b92c2-126">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b92c2-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b92c2-127">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b92c2-128">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b92c2-128">Network Settings Schema</span></span>](index.md)
