---
title: '방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정'
description: .NET Framework에서 IPv6 지원을 사용하도록 컴퓨터 구성 파일 machine.config를 수정하는 방법을 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: eb7b3665c0dbcf0edefa8c48a9e69297d7259067
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502524"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a><span data-ttu-id="80a65-103">방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정</span><span class="sxs-lookup"><span data-stu-id="80a65-103">How to: Modify the Computer Configuration File to Enable IPv6 Support</span></span>
<span data-ttu-id="80a65-104">다음 코드 예제에서는 컴퓨터 구성 파일 *machine.config*를 수정하여 IPv6 지원을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-104">The following code example shows how to modify the computer configuration file, *machine.config*, to enable IPv6 support.</span></span> <span data-ttu-id="80a65-105">*machine.config* 파일은 Windows가 설치된 디렉터리의 *%Windir%\Microsoft.NET\Framework* 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-105">The *machine.config* file is stored in the *%Windir%\Microsoft.NET\Framework* folder in the directory where Windows was installed.</span></span> <span data-ttu-id="80a65-106">컴퓨터에 설치된 .NET Framework의 각 버전에 해당하는 *%Windir%\Microsoft.NET\Framework* 아래의 폴더에는 개별 *machine.config* 파일이 있습니다(예: *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span><span class="sxs-lookup"><span data-stu-id="80a65-106">There is a separate *machine.config* file in the folders under *%Windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer (for example, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span></span>  
  
 <span data-ttu-id="80a65-107">이러한 설정은 컴퓨터 구성 파일보다 우선하는 애플리케이션의 구성 파일에서 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-107">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="80a65-108">.NET Framework 버전 1.1 이하의 경우 **ipv6 enabled** 구성 스위치 값은 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 멤버가 IPv6 주소를 반환하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-108">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="80a65-109">.NET Framework 버전 2.0 이상의 경우 Windows에서 IPv6을 지원하면 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 모든 멤버(예: <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> 메서드)는 한 가지 제한과 함께 IPv6 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-109">For .NET Framework version 2.0 and later, if Windows supports IPv6, then all members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="80a65-110"><xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 사용되지 않는 멤버(예: <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> 메서드)는 구성 파일에서 값을 읽고 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-110">Obsolete members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80a65-111">.NET Framework 버전 2.0 이상의 경우 기본적으로 IPv6이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-111">For .NET Framework version 2.0 and later, IPv6 is enabled by default.</span></span> <span data-ttu-id="80a65-112">.NET Framework 버전 1.1 이하의 경우 IPv6은 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80a65-112">For .NET Framework version 1.1 and earlier, IPv6 is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a65-113">예제</span><span class="sxs-lookup"><span data-stu-id="80a65-113">Example</span></span>  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>
    ……………  
    </settings>  
    ………………  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80a65-114">참조</span><span class="sxs-lookup"><span data-stu-id="80a65-114">See also</span></span>

- [<span data-ttu-id="80a65-115">IPv6 주소 지정</span><span class="sxs-lookup"><span data-stu-id="80a65-115">IPv6 Addressing</span></span>](ipv6-addressing.md)
- [<span data-ttu-id="80a65-116">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="80a65-116">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="80a65-117">\<ipv6> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="80a65-117">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
