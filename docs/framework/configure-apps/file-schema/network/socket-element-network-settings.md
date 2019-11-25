---
title: <socket> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 0e2b369eccfbc658a790ef61a961315a88361669
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089083"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="7bdc8-102">\<socket > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="7bdc8-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="7bdc8-103">소켓 작업에서 완료 포트를 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-103">Specifies whether socket operations use completion ports.</span></span>  

<span data-ttu-id="7bdc8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7bdc8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7bdc8-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="7bdc8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="7bdc8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<설정**](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="7bdc8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="7bdc8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**소켓 >**</span><span class="sxs-lookup"><span data-stu-id="7bdc8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7bdc8-108">구문</span><span class="sxs-lookup"><span data-stu-id="7bdc8-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bdc8-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7bdc8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7bdc8-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bdc8-111">특성</span><span class="sxs-lookup"><span data-stu-id="7bdc8-111">Attributes</span></span>  
  
|<span data-ttu-id="7bdc8-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="7bdc8-112">**Attribute**</span></span>|<span data-ttu-id="7bdc8-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="7bdc8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="7bdc8-114">소켓이 항상 허용 메서드 호출에 대해 완료 포트를 사용 해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="7bdc8-115">기본값은 `false`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="7bdc8-116">소켓이 연결 메서드 호출에 대해 항상 완료 포트를 사용 해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="7bdc8-117">기본값은 `false`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="7bdc8-118">소켓에 사용할 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="7bdc8-119">기본값은 Windows 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bdc8-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7bdc8-120">Child Elements</span></span>  
 <span data-ttu-id="7bdc8-121">없음.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7bdc8-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7bdc8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7bdc8-123">**요소**</span><span class="sxs-lookup"><span data-stu-id="7bdc8-123">**Element**</span></span>|<span data-ttu-id="7bdc8-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="7bdc8-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7bdc8-125">설정</span><span class="sxs-lookup"><span data-stu-id="7bdc8-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="7bdc8-126"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bdc8-127">주의</span><span class="sxs-lookup"><span data-stu-id="7bdc8-127">Remarks</span></span>  
 <span data-ttu-id="7bdc8-128">`alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성이 <xref:System.Net.Sockets?displayProperty=nameWithType> 네임스페이스에 있는 클래스에 의해 완료 포트의 사용과 관련된 기본 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="7bdc8-129">고성능 서버 응용 프로그램에는 완료 포트를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="7bdc8-130">`alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성의 기본값은 **false**입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="7bdc8-131"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>를 사용 하 여 적용 가능한 구성 파일에서 `alwaysUseCompletionPortsForAccept` 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="7bdc8-132"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>를 사용 하 여 적용 가능한 구성 파일에서 `alwaysUseCompletionPortsForConnect` 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="7bdc8-133">`ipProtectionLevel` 특성은 소켓에 사용할 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="7bdc8-134"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 속성을 사용 하면 동일한 링크 로컬 또는 사이트 로컬 접두사가 있는 주소와 같이 지정 된 범위에 대 한 IPv6 소켓 제한을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="7bdc8-135">이 옵션에는 애플리케이션을으로 IPv6 소켓에 대 한 액세스 제한을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="7bdc8-136">이러한 제한을 사용하면 사설 LAN에서 실행되는 애플리케이션을 간단하고 강력하게 외부 공격으로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="7bdc8-137">이 옵션은 수신 소켓의 범위를 확장 하거나 축소 하 여 적절 한 경우 공용 및 개인 사용자의 무제한 액세스를 허용 하거나 필요에 따라 같은 사이트로만 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="7bdc8-138">이 `ipProtectionLevel` 특성 설정은 초기 들어오는 트래픽에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="7bdc8-139">소켓에서 들어오는 연결을 수신 대기 하는 TCP 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="7bdc8-140">소켓에서 패킷을 수신 하는 UDP 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="7bdc8-141">이 구성 설정은 이미 설정 된 TCP 연결에는 영향을 주지 않습니다. (트래픽은 양방향으로 제한 되지 않음), UDP 패킷을 보내는 응용 프로그램에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="7bdc8-142">`ipProtectionLevel` 특성 설정에 사용할 수 있는 값은 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 열거에 지정 된 보호 수준에 따라 다음과 같이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="7bdc8-143">**특성 값**</span><span class="sxs-lookup"><span data-stu-id="7bdc8-143">**Attribute Value**</span></span>|<span data-ttu-id="7bdc8-144">**설명**</span><span class="sxs-lookup"><span data-stu-id="7bdc8-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="7bdc8-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="7bdc8-145">EdgeRestricted</span></span>|<span data-ttu-id="7bdc8-146">IP 보호 수준이 edge 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="7bdc8-147">이 값은 인터넷을 통해 작동하도록 디자인된 애플리케이션에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="7bdc8-148">이 설정은 Windows Teredo 구현을 사용한 NAT (네트워크 주소 변환) 통과를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="7bdc8-149">이러한 애플리케이션에서는 IPv4 방화벽이 무시될 수 있으므로 열린 포트로 향하는 인터넷 공격을 막기 위해 애플리케이션의 보안 기능을 강화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="7bdc8-150">Windows Server 2003 및 Windows XP에서 소켓의 IP 보호 수준에 대 한 기본값은에 지 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="7bdc8-151">액세스가</span><span class="sxs-lookup"><span data-stu-id="7bdc8-151">Restricted</span></span>|<span data-ttu-id="7bdc8-152">IP 보호 수준이 제한 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-152">The IP protection level is restricted.</span></span> <span data-ttu-id="7bdc8-153">이 값은 인터넷 시나리오를 구현하지 않는 인트라넷 애플리케이션에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="7bdc8-154">일반적으로 이러한 애플리케이션은 인터넷형 공격에 대해 테스트되거나 보안이 강화되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="7bdc8-155">이 설정은 수신 되는 트래픽을 링크 로컬 전용으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="7bdc8-156">제한 없음</span><span class="sxs-lookup"><span data-stu-id="7bdc8-156">Unrestricted</span></span>|<span data-ttu-id="7bdc8-157">IP 보호 수준이 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="7bdc8-158">이 값은 Windows에 구축된 IPv6 NAT 통과 기능(예: Teredo)을 이용하는 애플리케이션을 비롯하여 인터넷을 통해 작동하도록 디자인된 애플리케이션에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="7bdc8-159">이러한 애플리케이션에서는 IPv4 방화벽이 무시될 수 있으므로 열린 포트로 향하는 인터넷 공격을 막기 위해 애플리케이션의 보안 기능을 강화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="7bdc8-160">Windows Server 2008 R2 및 Windows Vista에서 소켓의 IP 보호 수준에 대 한 기본값은 무제한입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="7bdc8-161">지정 되지 않은</span><span class="sxs-lookup"><span data-stu-id="7bdc8-161">Unspecified</span></span>|<span data-ttu-id="7bdc8-162">IP 보호 수준이 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="7bdc8-163">Windows 7 및 Windows Server 2008 r 2에서 소켓의 IP 보호 수준에 대 한 기본값은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="7bdc8-164">`ipProtectionLevel` 특성의 기본값은 **지정**되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="7bdc8-165"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 속성을 사용 하 여 적용 가능한 구성 파일에서 `ipProtectionLevel` 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7bdc8-166">구성 파일</span><span class="sxs-lookup"><span data-stu-id="7bdc8-166">Configuration Files</span></span>  
 <span data-ttu-id="7bdc8-167">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bdc8-168">예제</span><span class="sxs-lookup"><span data-stu-id="7bdc8-168">Example</span></span>  
 <span data-ttu-id="7bdc8-169">다음 예에서는 완료 포트를 사용 하도록 지정 하 고 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 제한 되지 않아야 함을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bdc8-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bdc8-170">참조</span><span class="sxs-lookup"><span data-stu-id="7bdc8-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="7bdc8-171">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7bdc8-171">Network Settings Schema</span></span>](index.md)
