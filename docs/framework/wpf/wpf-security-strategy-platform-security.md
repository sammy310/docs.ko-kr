---
title: 플랫폼 보안 전략
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform security model [WPF]
- Common Language Runtime (CLR) security features
- operating system security model [WPF]
- Internet Explorer security features [WPF]
- Security-Critical method
- CLR security features [WPF]
- security model [WPF]
- security model [WPF], platform
- WPF [WPF], about security model
- Windows Presentation Foundation [WPF], about security model
- security model [WPF], operating system
ms.assetid: 2a39a054-3e2a-4659-bcb7-8bcea490ba31
ms.openlocfilehash: 258fcd7c51ea59de03fe60a4eeb9a82dd1c7efca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174604"
---
# <a name="wpf-security-strategy---platform-security"></a>WPF 보안 전략 - 플랫폼 보안
WPF(Windows 프레젠테이션 재단)는 다양한 보안 서비스를 제공하지만 운영 체제, CLR 및 Internet Explorer를 포함하는 기본 플랫폼의 보안 기능도 활용합니다. 다음 그림과 같이 이러한 계층이 결합되어 WPF에 단일 실패 지점을 피하려고 하는 강력한 심층 방어 보안 모델을 제공합니다.  
  
 ![WPF 보안 모델을 보여 주는 다이어그램입니다.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 이 항목의 나머지 부분에서는 WPF와 관련된 각 계층의 기능에 대해 설명합니다.  

## <a name="operating-system-security"></a>운영 체제 보안  
Windows의 핵심은 WPF로 빌드된 응용 프로그램을 포함하여 모든 Windows 응용 프로그램에 대한 보안 기반을 형성하는 몇 가지 보안 기능을 제공합니다. 이 항목에서는 WPF에 중요한 이러한 보안 기능의 폭과 WPF가 이러한 보안 기능과 통합하여 심층 방어를 제공하는 방법에 대해 설명합니다.  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP SP2(서비스 팩 2)  
 Windows의 일반적인 검토 및 강화 외에도 이 항목에서 논의할 Windows XP SP2의 세 가지 주요 기능이 있습니다.  
  
- /GS 컴파일  
  
- 마이크로 소프트 윈도우 업데이트.  
  
#### <a name="gs-compilation"></a>/GS 컴파일  
 Windows XP SP2는 CLR과 같은 모든 WPF 종속성을 포함하여 많은 핵심 시스템 라이브러리를 다시 컴파일하여 버퍼 오버런을 완화하여 보호합니다. 이 작업을 위해 /GS 매개 변수와 C/C++ 명령줄 컴파일러를 함께 사용합니다. 버퍼 오버런을 명시적으로 피해야 하지만 /GS 컴파일은 실수 또는 악의적으로 만들어진 잠재적인 취약성에 대한 심층 방어의 예를 제공합니다.  
  
 지금까지 버퍼 오버런은 많은 강력한 보안 익스플로이트의 원인이 되었습니다. 버퍼 오버런은 공격자는 버퍼의 경계를 지나서 쓰는 악성 코드의 삽입을 허용하는 코드 취약성을 활용하는 경우에 발생합니다. 이 경우 공격자의 코드가 실행되도록 함수의 반환 주소를 덮어써서 코드가 실행되는 프로세스를 공격자가 가로챌 수 있습니다. 그 결과, 가로챈 프로세스와 동일한 권한으로 임의 코드를 실행하는 악성 코드가 생깁니다.  
  
 상위 수준에서 -GS 컴파일러 플래그는 로컬 문자열 버퍼가 있는 함수의 반환 주소를 보호하기 위해 특수 보안 쿠키를 삽입하여 일부 잠재적인 버퍼 오버런으로부터 보호합니다. 함수가 반환된 후 보안 쿠키를 이전 값과 비교합니다. 값이 변경된 경우 버퍼 오버런이 발생했을 수 있으며 프로세스가 오류 상태로 중지됩니다. 프로세스를 중지하면 잠재적인 악성 코드의 실행이 방지됩니다. 자세한 내용은 [-GS(버퍼 보안 검사)를](/cpp/build/reference/gs-buffer-security-check) 참조하십시오.  
  
 WPF는 WPF 응용 프로그램에 또 다른 방어 계층을 추가하기 위해 /GS 플래그로 컴파일됩니다.  
  
### <a name="windows-vista"></a>Windows Vista  
Windows Vista의 WPF 사용자는 "최소 권한 사용자 액세스", 코드 무결성 검사 및 권한 격리를 비롯한 운영 체제의 추가 보안 향상의 이점을 누릴 수 있습니다.  
  
#### <a name="user-account-control-uac"></a>UAC(사용자 계정 컨트롤)  
 오늘날 Windows 사용자는 많은 응용 프로그램에서 설치 또는 실행 또는 둘 다에 대해 관리자 권한을 필요로 하기 때문에 관리자 권한으로 실행하는 경향이 있습니다. 한 가지 예로 기본 애플리케이션 설정을 레지스트리에 쓸 수 있습니다.  
  
 관리자 권한으로 실행은 실제로 관리자 권한이 부여된 프로세스에서 애플리케이션이 실행됨을 의미합니다. 이 경우 보안에 미치는 영향은 관리자 권한으로 실행되는 프로세스를 가로챈 악성 코드가 중요한 시스템 리소스에 대한 액세스를 포함하여 해당 권한을 자동으로 상속하게 된다는 것입니다.  
  
 이 보안 위협으로부터 보호하는 한 가지 방법은 필요한 최소한의 권한으로 애플리케이션을 실행하는 것입니다. 이를 최소 권한 원칙이라고 하며 Windows 운영 체제의 핵심 기능입니다. 이 기능을 UAC(사용자 계정 제어)라고 하며 Windows UAC에서 다음과 같은 두 가지 주요 방법으로 사용됩니다.  
  
- 사용자가 관리자인 경우에도 기본적으로 대부분의 애플리케이션을 UAC 권한으로 실행합니다. 관리자 권한이 필요한 애플리케이션만 관리자 권한으로 실행됩니다. 관리자 권한으로 실행하려면 애플리케이션 매니페스트에서 또는 보안 정책의 항목으로 애플리케이션에 명시적으로 표시해야 합니다.  
  
- 가상화와 같은 호환성 솔루션을 제공합니다. 예를 들어 많은 애플리케이션이 C:\Program Files와 같은 제한된 위치에 쓰려고 합니다. UAC로 실행되는 애플리케이션의 경우 쓰는 데 관리자 권한이 필요하지 않은 사용자별 대체 위치가 있습니다. UAC로 실행되는 애플리케이션의 경우 해당 위치에 쓰고 있다고 생각하는 애플리케이션이 실제로는 사용자별 대체 위치에 쓰도록 UAC에서 C:\Program Files를 가상화합니다. 이러한 종류의 호환성 작업을 통해 운영 체제가 UAC에서 이전에 실행할 수 없었던 많은 애플리케이션을 실행할 수 있습니다.  
  
#### <a name="code-integrity-checks"></a>코드 무결성 검사  
 Windows Vista는 더 깊은 코드 무결성 검사를 통합하여 악성 코드가 로드/런타임에 시스템 파일이나 커널에 주입되는 것을 방지합니다. 이는 시스템 파일 보호 수준을 벗어납니다.  

### <a name="limited-rights-process-for-browser-hosted-applications"></a>브라우저에서 호스트된 애플리케이션에 대한 제한된 권한 프로세스  
 브라우저에서 호스팅되는 WPF 응용 프로그램은 인터넷 영역 샌드박스 내에서 실행됩니다. Microsoft 인터넷 익스플로러와의 WPF 통합은 추가 지원을 통해 이 보호 기능을 확장합니다.  
  
 XAML 브라우저 응용 프로그램(XBAPs)은 일반적으로 인터넷 영역 권한 집합에 의해 샌드박스되므로 이러한 권한을 제거해도 XAML 브라우저 응용 프로그램(XBAPs)은 호환성 측면에서 해를 끼치지 않습니다. 대신, 추가 심층 방어 계층이 만들어집니다. 샌드박스 애플리케이션이 다른 계층을 악용하고 프로세스를 가로챌 수 있는 경우 프로세스에 여전히 제한된 권한만 포함됩니다.  
  
 [최소 권한 사용자 계정 사용을](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29)참조하십시오.  
  
## <a name="common-language-runtime-security"></a>공용 언어 런타임 보안  
 공통 언어 런타임(CLR)은 유효성 검사 및 확인, CAS(코드 액세스 보안) 및 보안 에 중요한 방법론을 포함하는 여러 가지 주요 보안 이점을 제공합니다.  

### <a name="validation-and-verification"></a>유효성 검사 및 확인  
 어셈블리 격리 및 무결성을 제공하기 위해 CLR은 유효성 검사 프로세스를 사용합니다. CLR 유효성 검사는 어셈블리 외부를 가리키는 주소에 대한 PE(이식 실행 파일) 파일 형식의 유효성을 검사하여 어셈블리가 격리되도록 합니다. CLR 유효성 검사는 어셈블리 내에 포함된 메타데이터의 무결성도 검증합니다.  
  
 형식 안전성을 보장하고, 일반적인 보안 문제(예: 버퍼 오버런)를 방지하고, 하위 프로세스 격리를 통해 샌드박싱을 활성화하기 위해 CLR 보안은 확인 개념을 사용합니다.  
  
 관리되는 애플리케이션은 MSIL(Microsoft Intermediate Language)로 컴파일됩니다. 관리되는 애플리케이션의 메서드를 실행하면 해당 MSIL이 JIT(Just-In-Time) 컴파일을 통해 네이티브 코드로 컴파일됩니다. JIT 컴파일에는 코드에서 다음이 발생하지 않도록 하는 다양한 안정성 및 견고성 규칙을 적용하는 검증 프로세스가 포함됩니다.  
  
- 형식 계약 위반  
  
- 버퍼 오버런 도입  
  
- 무분별한 메모리 액세스  
  
 검증 규칙을 준수하지 않는 관리 코드는 신뢰할 수 있는 코드로 간주되지 않을 경우 실행할 수 없습니다.  
  
 확인 가능한 코드의 장점은 WPF가 .NET 프레임워크를 기반으로 하는 중요한 이유입니다. 검증할 수 있는 코드를 사용하면 가능한 취약성이 악용될 가능성이 훨씬 줄어듭니다.  
  
### <a name="code-access-security"></a>코드 액세스 보안  
 클라이언트 컴퓨터는 파일 시스템, 레지스트리, 인쇄 서비스, 사용자 인터페이스, 리플렉션 및 환경 변수를 포함하여 관리되는 애플리케이션이 액세스할 수 있는 다양한 리소스를 노출합니다. 관리되는 응용 프로그램이 클라이언트 컴퓨터의 리소스에 액세스하려면 .NET Framework 권한이 있어야 합니다. CAS의 <xref:System.Security.CodeAccessPermission>권한은; CAS는 관리되는 응용 프로그램이 액세스할 수 있는 각 리소스에 대해 하나의 하위 클래스를 구현합니다.  
  
 실행을 시작할 때 관리되는 응용 프로그램이 부여되는 권한 집합을 사용 권한 집합이라고 하며 응용 프로그램에서 제공하는 증명 파일에 의해 결정됩니다. WPF 응용 프로그램의 경우 제공된 증거는 응용 프로그램이 시작되는 위치 또는 영역입니다. CAS는 다음 영역을 식별합니다.  
  
- **내 컴퓨터**. 클라이언트 컴퓨터에서 시작된 애플리케이션입니다(완전 신뢰).  
  
- **로컬 인트라넷** 인트라넷에서 시작된 애플리케이션입니다. (다소 신뢰).  
  
- **인터넷**. 인터넷에서 시작된 애플리케이션입니다. (최소 신뢰).  
  
- **신뢰할 수 있는 사이트** 사용자가 신뢰할 수 있는 것으로 식별한 애플리케이션입니다. (최소 신뢰).  
  
- **신뢰할 수 없는 사이트** 사용자가 신뢰할 수 없는 것으로 식별한 애플리케이션입니다. (신뢰할 수 없음).  
  
 이러한 각 영역에 대해 CAS는 각각과 연결된 신뢰 수준과 일치하는 사용 권한을 포함하는 미리 정의된 권한 집합을 제공합니다. 이러한 개체는 다음과 같습니다.  
  
- **FullTrust** **내 컴퓨터** 영역에서 시작된 응용 프로그램의 경우. 가능한 모든 권한은 부여됩니다.  
  
- **로컬인트라넷**. **로컬 인트라넷** 영역에서 시작된 응용 프로그램의 경우 격리된 스토리지, 무제한 UI 액세스, 무제한 파일 대화 상자, 제한된 리플렉션, 환경 변수에 대한 제한된 액세스를 포함하여 클라이언트 머신의 리소스에 대해 보통 액세스 권한을 제공하도록 권한 하위 집합이 부여됩니다. 레지스트리와 같은 중요한 리소스에 대한 권한은 제공되지 않습니다.  
  
- **인터넷**. **인터넷** 또는 신뢰할 수 **있는 사이트** 영역에서 시작된 응용 프로그램의 경우 격리된 스토리지, 파일 열기 전용 및 제한된 UI를 포함하여 클라이언트 머신의 리소스에 대해 제한된 액세스 권한을 제공하도록 권한 하위 집합이 부여됩니다. 기본적으로 이 권한 집합은 클라이언트 컴퓨터에서 응용 프로그램을 격리합니다.  
  
 **신뢰할 수 없는 사이트** 영역에서 확인된 응용 프로그램에는 CAS에 의해 사용 권한이 전혀 부여되지 않습니다. 따라서 미리 정의된 해당 권한 집합이 없습니다.  
  
 다음 그림에서는 영역, 사용 권한 집합, 사용 권한 및 리소스 간의 관계를 보여 줍니다.  
  
 ![CAS 권한 집합을 보여 주는 다이어그램입니다.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 인터넷 영역 보안 샌드박스의 제한은 XBAP가 WPF를 포함하여 시스템 라이브러리에서 가져오는 모든 코드에도 동일하게 적용됩니다. 이렇게 하면 코드의 모든 비트가 잠겨 있고 WPF도 잠깁니다. 안타깝게도 XBAP를 실행하려면 인터넷 영역 보안 샌드박스에서 활성화한 것보다 더 많은 권한이 필요한 기능을 실행해야 합니다.  
  
 다음 페이지를 포함하는 XBAP 응용 프로그램을 고려하십시오.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 이 XBAP를 실행하려면 기본 WPF 코드가 다음을 포함하여 XBAP 호출에서 사용할 수 있는 것보다 더 많은 기능을 실행해야 합니다.  
  
- 렌더링을 위한 HWND(창 핸들 만들기)  
  
- 메시지 디스패치  
  
- Tahoma 글꼴 로드  
  
 샌드박스 애플리케이션에서 이러한 작업에 직접 액세스할 수 있도록 허용하면 보안상 치명적일 수 있습니다.  
  
 다행히 WPF는 샌드박스 응용 프로그램을 대신하여 높은 권한으로 이러한 작업을 실행할 수 있도록 하여 이러한 상황을 충족시킵니다. 모든 WPF 작업은 XBAP의 응용 프로그램 도메인의 제한된 인터넷 영역 보안 권한에 대해 검사되지만 WPF(다른 시스템 라이브러리와 마찬가지로)에는 가능한 모든 사용 권한이 포함된 권한 집합이 부여됩니다.
  
 이렇게 하려면 WPF가 호스트 응용 프로그램 도메인의 인터넷 영역 권한 집합에 의해 해당 권한이 제어되지 않도록 하면서 높은 권한을 받아야 합니다.  
  
 WPF는 권한의 **Assert** 메서드를 사용하여 이 작업을 수행합니다. 다음 코드에서는 이렇게 되는 방식을 보여 줍니다.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 **어설션은** 기본적으로 WPF에 필요한 무제한 사용 권한이 XBAP의 인터넷 영역 권한에 의해 제한되는 것을 방지합니다.  
  
 플랫폼 관점에서 WPF는 **어설션을** 올바르게 사용할 책임이 있습니다. **Assert를** 잘못 사용하면 악성 코드가 권한을 상승시킬 수 있습니다. 따라서 필요한 경우에만 **Assert를** 호출하고 샌드박스 제한이 그대로 유지되도록 하는 것이 중요합니다. 예를 들어 샌드박스 코드는 임의의 파일을 열 수 없지만 글꼴을 사용할 수 있습니다. WPF를 사용하면 샌드박스 응용 프로그램에서 **Assert를**호출하여 글꼴 기능을 사용하고 WPF는 샌드박스 응용 프로그램을 대신하여 해당 글꼴을 포함하는 것으로 알려진 파일을 읽을 수 있습니다.  
  
### <a name="clickonce-deployment"></a>ClickOnce 배포  
 ClickOnce는 .NET Framework에 포함되어 있으며 Visual Studio와 통합되는 포괄적인 배포 기술입니다(자세한 내용은 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment) 참조). 독립 실행형 WPF 응용 프로그램은 ClickOnce를 사용하여 배포할 수 있으며 브라우저 호스팅 응용 프로그램은 ClickOnce를 사용하여 배포해야 합니다.  
  
 ClickOnce를 사용하여 배포된 응용 프로그램에는 CAS(코드 액세스 보안)에 대한 추가 보안 계층이 제공됩니다. 기본적으로 ClickOnce 배포된 응용 프로그램은 필요한 권한을 요청합니다. 애플리케이션이 배포된 소스 영역에 대한 권한 집합을 초과하지 않는 경우에만 해당 권한이 부여됩니다. 사용 권한 집합을 시작 영역의 사용 권한 집합에서 제공하는 것보다 적더라도 필요한 권한 집합으로 줄이면 응용 프로그램에서 액세스할 수 있는 리소스 수가 최소로 줄어듭니다. 따라서 애플리케이션을 가로채는 경우 클라이언트 컴퓨터의 손상 가능성이 줄어듭니다.  
  
### <a name="security-critical-methodology"></a>보안에 중요한 방법론  
 XBAP 응용 프로그램에 대한 인터넷 영역 샌드박스를 사용하도록 사용 권한을 사용하는 WPF 코드는 가능한 한 높은 수준의 보안 감사 및 제어를 유지해야 합니다. 이러한 요구 사항을 용이하게 하기 위해 .NET Framework는 권한을 높이는 코드 관리에 대한 새로운 지원을 제공합니다. 특히 CLR을 사용하면 권한을 높이는 코드를 식별하고 을 로 <xref:System.Security.SecurityCriticalAttribute>표시할 수 있습니다. 이 방법론을 <xref:System.Security.SecurityCriticalAttribute> 사용하여 표시되지 않은 코드는 *투명해집니다.* 반대로, <xref:System.Security.SecurityCriticalAttribute>로 표시되지 않은 관리 코드는 권한을 높일 수 있습니다.  
  
 보안에 중요한 방법론을 사용하면 권한을 *보안에 중요한 커널로*승격하는 WPF 코드 의 구성을 허용하고 나머지는 투명하게 사용할 수 있습니다. 보안에 중요한 코드를 격리하면 WPF 엔지니어링 팀이 표준 보안 관행 을 넘어 보안에 중요한 커널에 대한 추가 보안 분석 및 소스 제어에 집중할 수 [있습니다(WPF 보안 전략 - 보안 엔지니어링](wpf-security-strategy-security-engineering.md)참조).  
  
 .NET Framework는 개발자가 APTCA(APTCA)로 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 표시되고 사용자의 GAC(전역 어셈블리 캐시)에 배포된 관리되는 어셈블리를 작성할 수 있도록 하여 신뢰할 수 있는 코드가 XBAP 인터넷 영역 샌드박스를 확장할 수 있도록 합니다. 어셈블리에 APTCA로 표시하는 경우 인터넷의 악성 코드를 비롯한 모든 코드에서 해당 어셈블리를 호출할 수 있으므로 중요한 보안 작업입니다. 이 작업을 수행할 때는 주의해서 최선의 방법을 사용해야 하며, 사용자가 해당 소프트웨어를 신뢰해야 설치됩니다.  
  
## <a name="microsoft-internet-explorer-security"></a>Microsoft Internet Explorer 보안  
 Microsoft Internet Explorer 6(SP2)에는 보안 문제를 줄이고 보안 구성을 단순화하는 것 외에도 XAML 브라우저 응용 프로그램(XBAPs) 사용자의 보안을 강화하는 몇 가지 기능이 포함되어 있습니다. 이러한 기능은 사용자가 검색 환경을 보다 효율적으로 제어할 수 있도록 하기 위한 것입니다.  
  
 IE6 SP2 이전에는 다음과 같은 사항의 적용을 받을 수 있습니다.  
  
- 무작위 팝업 창  
  
- 혼란스러운 스크립트 리디렉션  
  
- 일부 웹 사이트의 수많은 보안 대화 상자  
  
 경우에 따라 신뢰할 수 없는 웹 사이트는 사용자가 설치를 취소했더라도 설치를 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 스푸핑하거나 Microsoft ActiveX 설치 대화 상자를 반복적으로 표시하여 사용자를 속이려고 합니다. 이러한 기술을 사용하면 다수의 사용자가 속아서 잘못된 결정을 내리고 스파이웨어 애플리케이션을 설치할 수 있습니다.  
  
 IE6 SP2에는 이러한 유형의 문제를 완화하는 몇 가지 기능이 포함되어 있으며, 이는 사용자 개시 개념을 중심으로 진행됩니다. IE6 SP2는 사용자가 *작업*시작이라고 하는 작업 전에 링크 또는 페이지 요소를 클릭한 경우를 감지하고 페이지의 스크립트에 의해 유사한 작업이 트리거될 때와 다르게 처리합니다. 예를 들어 IE6 SP2에는 사용자가 팝업을 만들기 전에 단추를 클릭할 때 이를 감지하는 팝업 **차단이** 통합됩니다. 이를 통해 IE6 SP2는 사용자가 요청하거나 원하지 않는 팝업을 방지하는 동시에 대부분의 무해한 팝업을 허용할 수 있습니다. 차단된 팝업은 사용자가 수동으로 블록을 재정의하고 팝업을 볼 수 있는 새로운 **정보 표시줄**아래에 갇혀 있습니다.  
  
 **Open**/**Save** 보안 프롬프트에도 동일한 사용자 개시 논리가 적용됩니다. ActiveX 설치 대화 상자는 이전에 설치된 컨트롤의 업그레이드를 나타내지 않는 한 항상 정보 표시줄 아래에 갇혀 있습니다. 이러한 조치가 결합되어 사용자에게 더 안전하고 제어된 사용자 환경을 제공합니다. 사용자가 원하지 않는 소프트웨어나 악성 소프트웨어를 설치하도록 유인하는 사이트로부터 보호되기 때문입니다.  
  
 또한 IE6 SP2를 사용하여 WPF 응용 프로그램을 다운로드하고 설치할 수 있는 웹 사이트를 탐색하는 고객을 보호합니다. 특히 IE6 SP2는 WPF를 포함하여 어떤 기술을 사용했는지여부에 관계없이 사용자가 악의적이거나 악의적인 응용 프로그램을 설치할 수 있는 더 나은 사용자 환경을 제공하므로 이 기능을 사용할 수 있습니다. WPF는 ClickOnce를 사용하여 인터넷을 통해 응용 프로그램의 다운로드를 용이하게하여 이러한 보호에 추가합니다. XAML 브라우저 응용 프로그램(XBAPs)은 인터넷 영역 보안 샌드박스 내에서 실행되므로 원활하게 시작할 수 있습니다. 반면에 독립 실행형 WPF 응용 프로그램을 실행하려면 완전 신뢰가 필요합니다. 이러한 응용 프로그램의 경우 ClickOnce는 응용 프로그램의 추가 보안 요구 사항을 사용하도록 알리는 시작 프로세스 중에 보안 대화 상자가 표시됩니다. 그러나 사용자가 시작해야 하고, 사용자가 시작한 논리에 의해 제어되며, 취소할 수 있습니다.  
  
 Internet Explorer 7은 보안에 대한 지속적인 노력의 일환으로 IE6 SP2의 보안 기능을 통합하고 확장합니다.  
  
## <a name="see-also"></a>참고 항목

- [코드 액세스 보안](../misc/code-access-security.md)
- [보안](security-wpf.md)
- [WPF 부분 신뢰 보안](wpf-partial-trust-security.md)
- [WPF 보안 전략 - 보안 엔지니어링](wpf-security-strategy-security-engineering.md)
