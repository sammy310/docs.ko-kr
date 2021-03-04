---
title: 데스크톱용 .NET의 새로운 기능
description: .NET, .NET과 .NET Framework의 차이점, 추가 된 새로운 기능에 대해 알아봅니다.
ms.date: 12/29/2020
ms.openlocfilehash: 03dea849ad8a797b917dca953d93be6878d7ec72
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106183"
---
# <a name="whats-new-with-net-for-desktop"></a>데스크톱용 .NET의 새로운 기능

.NET Core 3.0부터 .NET은 Windows Forms 및 WPF를 지원 합니다. 따라서 이제 데스크톱 응용 프로그램에 대 한 .NET Framework와 .NET 중에서 선택할 수 있습니다. 이 장에서는 .NET 정의 및 데스크톱 응용 프로그램에 대 한 이점에 대해 설명 합니다.

## <a name="the-motivation-behind-net-core"></a>.NET Core의 동기

2002에서의 출시는 Windows Forms, ASP.NET, Entity Framework, Windows 스토어 등의 많은 기술을 지원 하기 위해 .NET Framework 년까지 발전 했습니다. 이러한 모든 것은 본질적으로 다릅니다. 따라서 Microsoft는 .NET Framework의 일부를 수행 하 고 각 기술에 대해 다른 응용 프로그램 스택을 만들어 이러한 혁신에 참여 했습니다. 이렇게 하면 특정 스택의 요구에 맞게 개발 기능을 사용자 지정 하 여 모든 플랫폼의 잠재력을 최대화할 수 있습니다. 이로 인해 서로 다른 독립적인 팀에서 유지 관리 하는 .NET Framework 버전의 조각화가 발생 합니다. 이러한 모든 스택은 앱 모델, 프레임 워크 및 런타임을 포함 하는 공통 구조를 갖지만 이러한 각 파트의 구현에 차이가 있습니다.

이러한 플랫폼 중 하나만 대상으로 지정 하는 경우이 모델을 사용할 수 있습니다. 그러나 대부분의 경우 동일한 솔루션에 둘 이상의 대상 플랫폼이 필요할 수 있습니다. 예를 들어 응용 프로그램에는 서버에서 실행 되는 백 엔드 논리와 모바일 클라이언트를 공유 하는 고객 관련 웹 사이트인 데스크톱 관리자 파트가 있을 수 있습니다. 이 경우이 .NET 감축할 모두 확장할 수 있는 통합 코딩 환경이 필요 합니다.

Windows 8이 출시 된 시간에는 PCLs (이식 가능한 클래스 라이브러리) 개념이 탄생 했습니다. .NET Framework 원래는 항상 단일 단위로 배포 될 것 이라는 가정을 중심으로 설계 [되었기 때문에](https://wikipedia.org/wiki/Decomposition_(computer_science)) 중요 한 것은 아닙니다. 감축할 간에 코드를 공유 하는 문제를 해결 하기 위해 프레임 워크를 리팩터링 하는 방법에 대 한 주행 힘이 있습니다. 계약의 아이디어는 잘 구분 된 API 노출 영역을 제공 하는 것입니다. 계약은 사용자가 컴파일하는 단순한 어셈블리 이며 적절 한 팩터링을 고려 하 여 디자인 되어 있습니다.

이로 인해 이전에 수행한 개별 API 수준과 달리 어셈블리 수준에서 감축할의 API 차이점을 알 수 있습니다. 이 측면에서는 이식 가능한 클래스 라이브러리 라고도 하는 여러 감축할를 대상으로 하는 클래스 라이브러리 환경을 사용 했습니다.

![.NET Framework의 릴리스 기록](./media/whats-new-dotnet-core/release-history.png)

PCL을 사용 하면 개발 환경이 API 셰이프를 기반으로 하는 감축할에서 통합 됩니다. 그리고 다른 감축할에서 실행 되는 라이브러리를 만들어야 하는 경우에도 주소가 지정 됩니다. 그러나 많은 문제를 해결 해야 합니다. Api는 구현을 모든 감축할에서 앞으로 이동할 때만 이식 가능 합니다.

잘 구분 된 뷰 대신 잘 구분 된 구현을 제공 하 여 감축할 간에 구현을 통합 하는 것이 더 나은 방법입니다. 특정 구성 요소를 소유 하는 각 팀에 게 일관 된 API 스택을 소급 하는 것 보다 모든 감축할에서 Api가 작동 하는 방식에 대해 생각 하는 것이 훨씬 더 간단 합니다. 여기서 .NET Standard 제공 됩니다. 다음 섹션에서 세부 정보를 참조 하세요.

또 다른 큰 문제는 .NET Framework 배포 되는 방법에 대 한 것입니다. .NET Framework는 시스템 수준 프레임 워크입니다. 이에 대 한 모든 변경 내용은 종속 된 모든 응용 프로그램에 영향을 줍니다. 이 배포 모델에는 디스크 공간 절감 및 서비스에 대 한 중앙 액세스와 같이 많은 이점이 있지만 몇 가지 문제가 있습니다.

먼저 응용 프로그램 개발자가 최근 출시 된 프레임 워크에 대 한 종속성을 사용 하기 어렵습니다. 최신 OS에 대 한 종속성을 사용 하거나 응용 프로그램과 함께 .NET Framework를 설치 하는 응용 프로그램 설치 관리자를 제공 해야 합니다. 웹 개발자 인 경우 IT 부서에서 서버 지원 버전을 설정 하는 경우에도이 옵션을 사용할 수 없습니다.

.NET Framework 설치 프로그램에 연결할 설치 관리자를 제공 하는 데 문제가 있는 경우에도 .NET Framework를 업그레이드 하면 다른 응용 프로그램이 중단 될 수 있습니다.

이전 버전과 호환 되는 프레임 워크 버전을 제공 하는 데에도 불구 하 고 응용 프로그램을 중단할 수 있는 호환 되는 변경 내용이 있습니다. 예를 들어 기존 형식에 인터페이스를 추가 하면이 형식이 serialize 되는 방식이 변경 되어 기존 코드에 따라 문제가 발생할 수 있습니다. .NET Framework가 설치 된 기본은 매우 다양 하기 때문에 이러한 주요 시나리오를 방지 하는 것이 .NET Framework 내 혁신의 속도를 저하 시킵니다.

이러한 모든 문제를 해결 하기 위해 Microsoft는 .net 플랫폼의 진화에 접근 하기 위해 .NET Core를 개발 했습니다.

## <a name="introduction-to-net-core"></a>.NET Core 소개

.NET Core는 Microsoft의 .NET 기술을 모듈식 플랫폼 간 오픈 소스 및 클라우드 준비 플랫폼으로 진화 하 고 있습니다. Windows, macOS 및 Linux에서 실행 되는 계획은 Android 및 IoT와 같은 ARM 기반 아키텍처 에서도 실행 됩니다.

.NET Core의 목적은 Windows, 플랫폼 간 및 모바일 응용 프로그램을 포함 하는 모든 유형의 응용 프로그램에 대해 통합 플랫폼을 제공 하는 것입니다. 이를 통해 모든 응용 프로그램 모델에 필요한 공유 기본 Api를 제공 하 고 응용 프로그램 모델용 API를 제외 하 여이 기능을 사용할 수 [.NET Standard](../../standard/net-standard.md) .

이 프레임 워크는 효율성과 성능 측면에서 많은 이점을 제공 하 여 지원 되는 다양 한 플랫폼에서 패키징 및 배포를 간소화 합니다.

.NET Core의 이점은 다음과 같은 세 가지 특성에서 제공 됩니다.

- **플랫폼 간:** 다른 플랫폼 (Windows, macOS 및 Linux)에서 응용 프로그램을 실행할 수 있습니다.
- **오픈 소스:** .net Core 플랫폼은 오픈 소스 이며 GitHub, 빠르게 수행 투명 및 커뮤니티 기여를 통해 사용할 수 있습니다.
- **지원 됨:** Microsoft는 공식적으로 .NET Core를 지원 합니다.

.NET Core 3.0부터 웹 및 클라우드의 기존 지원 외에 데스크톱, IoT 및 AI 도메인도 지원 됩니다. 이 프레임 워크에 대 한 목표는 모든 유형의 .NET 개발 및 미래를 대상으로 하는 것입니다. Microsoft는 2020의 끝에 .NET 5로이 비전을 완료할 계획입니다. .NET 환경의 고유성을 강화 하기 위해 "Core" 이름이 제거 되었습니다.

## <a name="net-5-is-net-core-vnext"></a>.NET 5는 .NET Core vNext

.Net 5는 .NET Core를 사용 하 여 다음 단계를 진행 합니다. .NET 5.0은 몇 가지 주요 방법으로 .NET을 개선 하는 것을 목표로 합니다.

- 어디서나 사용할 수 있고 일관성 있는 런타임 동작 및 개발자 환경을 제공하는 단일 .NET 런타임 및 프레임워크를 생성합니다.
- .NET Core, .NET Framework, Xamarin, Mono를 활용하여 .NET의 기능을 확장합니다.
- 개발자(Microsoft 및 커뮤니티)가 함께 작업하고 확장할 수 있으며 모든 시나리오를 개선하는 단일 코드 베이스에서 해당 제품을 빌드합니다.

이 새 릴리스와 방향은 .NET 용 게임 교환기입니다. .NET 5에서 코드와 프로젝트 파일은 빌드하는 앱의 형식에 관계 없이 모양과 느낌이 동일 합니다. 각 앱과 동일한 런타임, Api 및 언어 기능에 액세스할 수 있습니다. 여기에는 실제로 매일 매일 런타임에 커밋되는 새로운 [성능 향상](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/) 이 포함 됩니다. 자세한 내용은 [.net 5의 새로운 기능](../../core/dotnet-five.md)을 참조 하세요.

![.NET 5의 모든 도메인](./media/whats-new-dotnet-core/all-domains-of-dotnet5.png)

## <a name="net-framework-vs-net-5"></a>.NET Framework와 .NET 5 비교

이제 .NET의 관련성을 이해 했으므로 .NET Framework 어떻게 되는지 궁금할 수 있습니다. 다음과 같은 질문을 할 수 있습니다. 중단 해야 하나요? 사라져 갈 까 요? .NET Framework에 있는 응용 프로그램을 현대화 하기 위한 선택 사항은 무엇 인가요?

2019에서는 **.NET Framework-4.8** 의 마지막 버전이 릴리스 되었습니다. 데스크톱 응용 프로그램에 대 한 세 가지 주요 개선 사항이 포함 되어 있습니다.

- **최신 브라우저 및 미디어 컨트롤**: 오늘날 .net 데스크톱 응용 프로그램은 HTML을 표시 하 고 미디어 파일을 재생 하는 데 Internet Explorer 및 Windows Media Player를 사용 합니다. 이러한 레거시 컨트롤은 최신 HTML을 표시 하거나 최신 미디어 파일을 재생 하지 않으므로 최신 표준을 지 원하는 Microsoft Edge 및 최신 미디어 플레이어를 활용 하는 새 컨트롤이 추가 되었습니다.
- **Uwp 컨트롤에** 대 한 액세스: uwp에는 최신 Windows 기능 및 터치 디스플레이를 활용 하는 새로운 컨트롤이 포함 되어 있습니다. 이러한 새 기능 및 컨트롤을 사용 하도록 응용 프로그램을 다시 작성할 필요가 없으므로 기존 WPF 또는 Windows Forms 코드에서 이러한 새 기능을 사용할 수 있습니다.
- **높은 DPI의 향상 된 기능**: 디스플레이의 해상도는 4K 및 8k 해상도로 증가 합니다. 따라서 .NET Framework 4.8에는 새로운 HDPI 기능이 추가 되어 기존 Windows Forms 및 WPF 응용 프로그램이 이러한 새 디스플레이에서 잘 보이도록 할 수 있습니다.

.NET Framework는 수백만 대의 컴퓨터에 설치 되기 때문에 Microsoft는 계속 지원 하지만 새 기능을 추가 하지는 않습니다.

.NET 5는 오픈 소스, 플랫폼 간 및 빠른 이동 버전의 .NET 제품군입니다. Side-by-side 특성으로 인해 응용 프로그램을 중단 하지 않고도 변경 내용을 사용할 수 있습니다. 즉, .NET에서는 시간이 지남에 따라 새 Api 및 언어 기능을 .NET Framework 하지 않습니다. 또한 **.net** 에는 다음과 같이 .NET Framework에 불가능 한 기능이 이미 있습니다.

- **Windows Forms 및 WPF를 지 원하는 .net의 side-by-side 버전**: 컴퓨터의 프레임 워크 버전을 업데이트할 때 의도 하지 않은 결과가 발생 하는 문제를 해결 합니다. 여러 버전의 .NET을 동일한 컴퓨터에 설치할 수 있으며 각 응용 프로그램은 사용 해야 하는 .NET 버전을 지정 합니다. 이제 .NET을 기반으로 Windows Forms 및 WPF를 개발 하 고 실행할 수 있습니다.
- **.Net을 응용 프로그램에 직접 포함**: 응용 프로그램 패키지의 일부로 .net을 배포할 수 있습니다. 이렇게 하면 컴퓨터에 특정 버전이 설치 될 때까지 기다리지 않고도 최신 버전, 기능 및 Api를 활용할 수 있습니다.
- .Net **기능 활용**: .net Core는 .net의 빠른 이동 오픈 소스 버전입니다. 이러한 기능을 함께 사용 하면 새로운 혁신적인 Api 및 BCL (기본 클래스 라이브러리)을 빠르게 도입할 수 있으므로 호환성이 손상 될 위험이 없습니다. 이제 Windows Forms 및 WPF 응용 프로그램은 최신 .NET 기능을 활용할 수 있습니다. 여기에는 런타임 성능, 높은 DPI 지원 등을 위한 보다 기본적인 수정 사항도 포함 됩니다.

Microsoft에 대 한 로드맵의 핵심 부분은 개발자가 응용 프로그램을 .NET Core로 이동 하 고 나중에 .NET 5로 이동 하는 것 이었습니다. 그러나 기존 .NET Framework 응용 프로그램이 있는 경우 .NET 5로 이동 하지 늘어났습니다. .NET Framework 완전히 지원 되며 항상 Windows의 일부가 됩니다. 그러나 나중에 최신 언어 기능과 Api를 사용 하려는 경우 응용 프로그램을 .NET으로 이동 해야 합니다.

새로운 데스크톱 응용 프로그램의 경우 .NET 5에서 직접 시작 하는 것이 좋습니다. 경량이 고 크로스 플랫폼 이며, side-by-side로 실행 되며, 성능이 높고, 컨테이너 및 마이크로 서비스 아키텍처에 완벽 하 게 부합 합니다.

![최신 .NET Framework 버전을 사용 하거나 응용 프로그램을 .NET Core로 이식 하 여 .NET Framework 응용 프로그램을 업데이트할 수 있습니다.](./media/whats-new-dotnet-core/framework-vs-core.png)

## <a name="net-standard-vs-pcl"></a>.NET Standard 및 PCL

[.NET Standard](../../standard/net-standard.md)는 모든 .NET 구현체에서 사용할 수 있는 .NET API의 공식 규격입니다. .NET Standard는 .NET 에코시스템의 통일성을 높이기 위한 것입니다. .NET Standard은 코드를 컴파일할 일관 된 계약 집합을 구성 하는 .NET Api의 사양입니다. 이러한 계약은 각 .NET 버전에서 구현 되므로 다양 한 .NET 구현에서 이식성을 사용할 수 있습니다.

.NET Standard를 통해 다음과 같은 주요 시나리오를 사용할 수 있습니다.

- 작업에 독립적으로 구현할 모든 .NET 구현에 대해 일관 된 기본 클래스 라이브러리 Api 집합을 정의 합니다.
- 개발자가 이와 같은 API를 사용하여 다양한 .NET 구현체에서 사용할 수 있는 이식 가능한 라이브러리를 만들 수 있습니다.

.NET Standard는 PCLs의 진화 이며 다음 목록은 .NET Standard와 PCLs 간의 기본적인 차이점을 보여 줍니다.

- .NET Standard은 Microsoft에서 선택 하는 큐 레이트 Api의 집합입니다. PCLs는 그렇지 않습니다.
- PCL이 포함 하는 Api는이를 만들 때 대상으로 선택 하는 플랫폼에 따라 달라 집니다. 이렇게 하면 선택한 특정 대상에 대해서만 PCL을 공유할 수 있습니다.
- .NET Standard은 플랫폼에 구애 받지 않으며 Windows, macOS, Linux 등 어디에서 나 실행할 수 있습니다.
- PCLs는 플랫폼 간도 실행할 수 있지만 더 제한적인 접근 방식을 가집니다. PCLs는 제한 된 플랫폼 집합만 대상으로 지정할 수 있습니다.

## <a name="new-desktop-features-in-net-core"></a>.NET Core의 새로운 데스크톱 기능

### <a name="support-for-windows-forms-and-wpf"></a>Windows Forms 및 WPF 지원

Windows Forms 및 WPF는 버전 3.0부터 .NET Core의 일부입니다. 두 프레젠테이션 프레임 워크는 모두 Windows 전용 이므로 플랫폼 간이 아닙니다. WPF를 DirectX에 대 한 풍부한 계층으로 생각할 수 있으며, GDI +를 통해 더 가늘게 계층으로 Windows Forms 수 있습니다. WPF 및 Windows Forms Windows에서 많은 데스크톱 응용 프로그램 기능을 제공 하 고 실행 하는 데 많은 도움이 됩니다. 따라서 Windows Forms 및 WPF는 .NET Core 및 .NET Framework에서 사용할 수 있습니다. 이제 .NET Core를 대상으로 하는 새 데스크톱 응용 프로그램을 시작 하 고 .NET Framework에서 .NET Core로 기존 응용 프로그램을 마이그레이션할 수 있습니다.

.NET Standard 버전 2.1의 새 버전이 .NET Core 3.0와 동시에 출시 되었습니다. 예상 대로 .NET Core 2.x 버전은 .NET Standard 2.1 이전 버전을 지원 합니다.

또한 .NET Core에 대 한 Windows Forms 및 WPF 구현이 모두 오픈 소스 인지 확인 하는 것이 중요 합니다.

### <a name="xaml-islands"></a>XAML Islands

[XAML 아일랜드](/windows/apps/desktop/modernize/xaml-islands) 는 개발자가 현재 WPF, Windows Forms 및 네이티브 Win32 앱 (예: MFC)에서 새로운 Windows 10 컨트롤 (UWP XAML 컨트롤)을 사용할 수 있는 구성 요소 집합입니다. Win32 앱 내에서 원하는 모든 위치에서 UWP XAML 컨트롤의 "아일랜드"를 사용할 수 있습니다.

Windows 10, 버전 1903에서는 Hwnd (windows 처리기)를 사용 하 여 Win32 windows에서 UWP XAML 콘텐츠를 호스팅할 수 있도록 하는 Api 집합을 도입 하기 때문에 이러한 XAML 아일랜드를 사용할 수 있습니다. Windows 10 1903 이상에서 실행 되는 앱만 XAML 아일랜드를 사용할 수 있습니다.

Windows Forms 및 WPF 개발자를 위한 XAML 아일랜드를 보다 쉽게 만들 수 있도록 Windows 커뮤니티 도구 키트는 여러 NuGet 패키지에 일련의 .NET 래퍼를 도입 합니다. 이러한 래퍼는 래핑된 컨트롤과 호스팅 컨트롤입니다.

- [웹 보기](/windows/communitytoolkit/controls/wpf-winforms/webview), [webviewcompatible](/windows/communitytoolkit/controls/wpf-winforms/webviewcompatible), [InkCanvas](/windows/communitytoolkit/controls/wpf-winforms/inkcanvas), [MEDIAPLAYERELEMENT](/windows/communitytoolkit/controls/wpf-winforms/mediaplayerelement)및 [없습니다](/windows/communitytoolkit/controls/wpf-winforms/mapcontrol) 래핑된 컨트롤은 일부 uwp XAML 컨트롤을 WINDOWS FORMS 또는 WPF 컨트롤로 래핑하고 해당 개발자에 대 한 uwp 개념을 숨깁니다.
- Windows Forms 및 WPF를 위한 [Windowsxamlhost](/windows/communitytoolkit/controls/wpf-winforms/windowsxamlhost) 컨트롤은 래핑된 UWP xaml 컨트롤이 아닌 다른 사용자 지정 컨트롤을 사용할 수 있도록 합니다.

### <a name="access-to-all-windows-10-apis"></a>모든 Windows 10 Api에 대 한 액세스

Windows 10에는 개발자가 작업할 수 있는 많은 API가 있습니다. 이러한 Api는 인증, Bluetooth, 약속 및 연락처와 같은 다양 한 기능에 대 한 액세스를 제공 합니다. 이제 이러한 Api는 .NET Core를 통해 노출 되 고 windows 개발자에 게 Windows 10에 있는 기능을 활용 하 여 강력한 데스크톱 앱을 만들 수 있는 기회를 제공 합니다.

### <a name="side-by-side-support-and-self-contained-exes"></a>Side-by-side 지원 및 자체 포함 Exe

.NET Core 배포 모델은 Windows 데스크톱 개발자가 .NET Core를 통해 경험할 수 있는 가장 큰 이점 중 하나입니다. .NET Core를 전역적으로 설치 하는 기능은 .NET Framework의 중앙 설치 및 서비스의 많은 이점을 제공 하지만 내부 업데이트는 필요 하지 않습니다.

새 .NET Core 버전이 릴리스되면 다른 응용 프로그램에 영향을 주지 않으면 서 필요에 따라 컴퓨터의 각 앱을 업데이트할 수 있습니다. 새 .NET Core 버전은 자체 디렉터리에 설치 되며 서로 "나란히" 존재 합니다.

격리를 사용 하 여 배포 해야 하는 경우 응용 프로그램을 사용 하 여 .NET Core를 배포할 수 있습니다. .NET Core는 .NET Core 런타임을 사용 하 여 앱을 단일 실행 파일로 묶습니다.

이러한 배포 옵션은 오랜 시간 동안 개발자가 요청 했지만 .NET Framework를 사용 하는 것은 어렵습니다. .NET Core에서 사용 되는 모듈식 아키텍처는 이러한 유연한 배포 옵션을 가능 하 게 합니다.

### <a name="performance"></a>성능

웹 및 클라우드 워크 로드를 대상으로 하기 때문에 .NET Core는 해당 DNA에 연결 된 성능을 갖습니다. 서버 쪽 코드는 현재 업계 최고의 성능 웹 플랫폼으로 고성능 시나리오와 .NET Core 점수를 충족 하기에 충분 해야 합니다.

.NET Core를 사용 하 여 차세대 데스크톱 응용 프로그램을 빌드하는 경우 이러한 성능 향상을 활용할 수 있습니다.

## <a name="benefits-of-open-source"></a>오픈 소스 이점

오픈 소스를 대상으로 하는 .NET Core에 대 한 몇 가지 단어만 있습니다. 플랫폼 간 stack 빌드는 각 대상 플랫폼에서 특수 팀의 상호 작용이 필요한 복잡 한 작업입니다. 이러한 활동은 Microsoft 내부 및 외부에서 많은 공동 작업을 필요로 합니다. 오픈 소스를 만들어 공개 공동 작업을 진행 하면 궁극적으로 민첩 한 개발 스타일을 제공 하 여 방대한 개발자 커뮤니티에서 문제를 발견 한 후 품질 막대를 발생 시킬 수 있습니다.

이는 앞에서 언급 한 로드맵의 속도를 지속적으로 높일 수 있는 .NET Core의 주요 성공 요소입니다. 모든 개발자가 응용 프로그램을 빌드하는 데 필요한 단일 .NET 플랫폼으로 사용할 수 있습니다.

>[!div class="step-by-step"]
>[이전](why-modern-applications.md)
>[다음](migrate-modern-applications.md)
