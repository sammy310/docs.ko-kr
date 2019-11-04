---
title: '방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정'
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: 98fb57abfff985ab96cb5139f15ae4c29c986a18
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040616"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a><span data-ttu-id="9d03d-102">방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정</span><span class="sxs-lookup"><span data-stu-id="9d03d-102">How to: Modify the Computer Configuration File to Enable IPv6 Support</span></span>
<span data-ttu-id="9d03d-103">다음 코드 예제에서는 컴퓨터 구성 파일 *machine.config*를 수정하여 IPv6 지원을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-103">The following code example shows how to modify the computer configuration file, *machine.config*, to enable IPv6 support.</span></span> <span data-ttu-id="9d03d-104">*machine.config* 파일은 Windows가 설치된 디렉터리의 *%Windir%\Microsoft.NET\Framework* 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-104">The *machine.config* file is stored in the *%Windir%\Microsoft.NET\Framework* folder in the directory where Windows was installed.</span></span> <span data-ttu-id="9d03d-105">컴퓨터에 설치된 .NET Framework의 각 버전에 해당하는 *%Windir%\Microsoft.NET\Framework* 아래의 폴더에는 개별 *machine.config* 파일이 있습니다(예: *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span><span class="sxs-lookup"><span data-stu-id="9d03d-105">There is a separate *machine.config* file in the folders under *%Windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer (for example, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span></span>  
  
 <span data-ttu-id="9d03d-106">이러한 설정은 컴퓨터 구성 파일보다 우선하는 애플리케이션의 구성 파일에서 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-106">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="9d03d-107">.NET Framework 버전 1.1 이하의 경우 **ipv6 enabled** 구성 스위치 값은 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 멤버가 IPv6 주소를 반환하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-107">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="9d03d-108">.NET Framework 버전 2.0 이상의 경우 Windows에서 IPv6을 지원하면 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 모든 멤버(예: <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> 메서드)는 한 가지 제한과 함께 IPv6 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-108">For .NET Framework version 2.0 and later, if Windows supports IPv6, then all members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="9d03d-109"><xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 사용되지 않는 멤버(예: <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> 메서드)는 구성 파일에서 값을 읽고 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-109">Obsolete members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d03d-110">.NET Framework 버전 2.0 이상의 경우 기본적으로 IPv6이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-110">For .NET Framework version 2.0 and later, IPv6 is enabled by default.</span></span> <span data-ttu-id="9d03d-111">.NET Framework 버전 1.1 이하의 경우 IPv6은 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d03d-111">For .NET Framework version 1.1 and earlier, IPv6 is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d03d-112">예</span><span class="sxs-lookup"><span data-stu-id="9d03d-112">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d03d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d03d-113">See also</span></span>

- [<span data-ttu-id="9d03d-114">IPv6 주소 지정</span><span class="sxs-lookup"><span data-stu-id="9d03d-114">IPv6 Addressing</span></span>](ipv6-addressing.md)
- [<span data-ttu-id="9d03d-115">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9d03d-115">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="9d03d-116">\<ipv6> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9d03d-116">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
