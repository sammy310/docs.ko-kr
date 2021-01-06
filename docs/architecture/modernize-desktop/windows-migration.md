---
title: Windows 10 마이그레이션
description: 패키징 및 XAML 아일랜드와 같은 Windows 10 기능에 대해 자세히 알아봅니다.
ms.date: 09/16/2019
ms.openlocfilehash: cd17088b086a32fd3bb37e617d3a1047acedde0e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "97866547"
---
# <a name="windows-10-migration"></a>Windows 10 마이그레이션

Windows 7 일 내에 개발 된 데스크톱 응용 프로그램을 사용 하는 경우를 고려해 보세요. 해당 시점에 사용할 수 있는 WPF 기술을 사용 하 고 정상적으로 작동 하지만, Windows 10에서 실행 하는 경우 오래 된 UI 및 동작을 사용 합니다. 행렬과 같은 futuristic 동영상을 시청 하는 경우와 Nokia 8110 장치를 사용 하는 Neo가 표시 되는 것을 볼 수 있습니다. 필름이 20 년 후에는 잘 작동 하지만 장치 현대화 혜택을 받을 수 있습니다.

Microsoft는 Windows 10 릴리스부터 태블릿 및 터치 장치와 같은 시나리오를 지원 하 고 Microsoft 운영 체제의 사용자에 게 최상의 환경을 제공 하기 위해 많은 혁신을 도입 했습니다. 예를 들어, 다음을 수행할 수 있습니다.

- Windows Hello를 사용 하 여 얼굴에 로그인 합니다.
- 펜을 사용 하 여 자동으로 인식 되 고 digitalized 텍스트를 그리거나 필기할 수 있습니다.
- WinML을 사용 하 여 클라우드에서 작성 된 로컬로 사용자 지정 된 AI 모델을 실행 합니다.

이러한 모든 기능은 Windows 개발자가 WinRT (Windows 런타임) 라이브러리를 통해 사용할 수 있습니다. 라이브러리가 .NET Framework 및 .NET Core에 모두 노출 되므로 기존 데스크톱 앱에서 이러한 기능을 활용할 수 있습니다. XAML 아일랜드를 사용 하 여 UI를 현대화 시간에 따라 앱의 시각적 개체 및 동작을 향상 시킬 수도 있습니다.

중요 한 한 가지 중요 한 점은이 현대화 경로를 따르기 위해 .NET Framework 기술을 중단 하지 않아도 된다는 것입니다. 안전 하 게 유지 하 고 .NET Core로 마이그레이션하지 않고도 Windows 10의 모든 이점을 누릴 수 있습니다. 따라서 현대화 경로를 선택할 수 있는 기능과 유연성이 모두 있습니다.

## <a name="winrt-apis"></a>WinRT Api

WinRT Api는 Windows 10 개발자가 운영 체제에서 제공 해야 하는 모든 항목에 액세스할 수 있게 해 주는 잘 구성 된 개체 지향 Api (응용 프로그래밍 인터페이스)입니다. WinRT Api를 통해 사용자 데스크톱 앱에서 푸시 알림, 장치 Api, Microsoft 잉크 및 WinML과 같은 기능을 통합할 수 있습니다.

일반적으로 기존 데스크톱 앱에서 WinRT Api를 호출할 수 있습니다. 그러나 두 가지 주요 영역에서이 규칙에 대 한 예외를 표시 합니다.

* 패키지 id를 필요로 하는 Api입니다.
* XAML 또는 컴퍼지션과 같은 시각화를 필요로 하는 Api입니다.

### <a name="universal-windows-platform-uwp-packages"></a>UWP (유니버설 Windows 플랫폼) 패키지

#### <a name="application-package-identity"></a>응용 프로그램 패키지 Id

UWP 앱에는 OS에서 응용 프로그램의 설치 및 제거를 관리 하는 배포 시스템이 있습니다. 이렇게 하면 설치 하는 동안 사용자 코드가 실행 되지 않는다는 의미의 설치를 선언형으로 사용 해야 합니다. 대신 응용 프로그램은 프로토콜, 파일 형식 및 확장과 같은 시스템과 통합 하려는 모든 항목을 응용 프로그램 매니페스트에서 선언 합니다. 배포 시 배포 파이프라인은 이러한 통합 요소를 구성 합니다. OS에서이 기능을 모두 관리 하 고 추적을 유지 하는 유일한 방법은 응용 프로그램에 대 한 고유 식별자 인 id를 각 ' 패키지 '에 포함 하는 것입니다.

일부 WinRT Api는이 패키지 id가 예상 대로 작동 해야 합니다. 그러나 기본 c + + 또는 .NET 앱과 같은 클래식 데스크톱 앱은 패키지 id가 필요 없는 다른 배포 시스템을 사용 합니다. 데스크톱 응용 프로그램에서 이러한 WinRT Api를 사용 하려면 패키지 id를 제공 해야 합니다.

진행 하는 한 가지 방법은 추가 패키징 프로젝트를 빌드하는 것입니다. 패키징 프로젝트 내에서 원래 소스 코드 프로젝트를 가리키고 제공 하려는 Id 정보를 지정 합니다.패키지를 설치 하 고 설치 된 앱을 실행 하는 경우 코드에서 Id를 필요로 하는 모든 WinRT Api를 호출할 수 있도록 자동으로 식별을 가져옵니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10">
    <Identity Name="YOUR-APP-GUID "
              Publisher="CN=YOUR COMPANY"
              Version="1.x.x.x" />
</Package>
```

API를 포함 하는 형식이 [DualApiPartition](xref:Windows.Foundation.Metadata.DualApiPartitionAttribute) 특성으로 표시 되어 있는지 검사 하 여 패키지 된 응용 프로그램 id가 필요한 api를 확인할 수 있습니다.인 경우 패키지 되지 않은 기존 데스크톱 앱에서를 호출할 수 있습니다. 그렇지 않으면 패키징 프로젝트의 도움을 사용 하 여 클래식 데스크톱 앱을 UWP로 변환 해야 합니다.

<https://docs.microsoft.com/windows/desktop/apiindex/uwp-apis-callable-from-a-classic-desktop-app>

#### <a name="benefits-of-packaging"></a>포장의 이점

이러한 Api에 대 한 액세스를 제공 하는 것 외에도 다음을 포함 하 여 데스크톱 응용 프로그램에 대 한 Windows 앱 패키지를 만들어 몇 가지 이점을 얻을 수 있습니다

* **효율적인 배포**. 앱에는 사용자가 응용 프로그램을 안전 하 게 설치 하 고 업데이트할 수 있도록 하는 뛰어난 배포 환경이 있습니다. 사용자가 앱을 제거 하도록 선택 하는 경우 Windows rot 문제를 방지 하는 것이 남아 있는 추적 없이 완전히 제거 됩니다.

* **자동 업데이트 및 라이선스**. 응용 프로그램은 Microsoft Store의 기본 제공 라이선스 및 자동 업데이트 기능에 참여할 수 있습니다. 자동 업데이트는 파일의 변경 된 부분만 다운로드 하므로 매우 안정적이 고 효율적인 메커니즘입니다.

* **증가 된 도달 및 간소화 된 수익 화**. 사용자의 경우는 아니지만 Microsoft Store를 통해 응용 프로그램을 배포 하도록 선택 하는 경우 수백만 개의 Windows 10 사용자에 게 도달 합니다.

* **UWP 기능을 추가** 합니다. 사용자의 속도로 UWP 기능을 앱의 패키지에 추가할 수 있습니다.

#### <a name="prepare-for-packaging"></a>패키징 준비

데스크톱 응용 프로그램의 패키지를 계속 진행 하기 전에 프로세스를 시작 하기 전에 해결 해야 할 몇 가지 사항이 있습니다. 응용 프로그램은 모든 Microsoft Store 규칙 및 정책을 준수 하 고 UWP 응용 프로그램 모델에서 실행 되어야 합니다. 예를 들어 .NET Framework 4.6.2 이상에서 실행 해야 하 고 `HKEY_CURRENT_USER` 레지스트리 하이브에 쓰고 AppData 폴더가 사용자 특정 앱 로컬 위치에 가상화 됩니다.

패키징을 위한 디자인 목표는 다른 앱과의 호환성을 유지 하면서 응용 프로그램 상태를 시스템 상태와 분리 하는 것입니다. Windows 10에서는 응용 프로그램을 UWP 패키지 내에 배치 하 여이 목표를 달성 합니다. 패키지에서 제공 하는 응용 프로그램의 신뢰할 수 있고 깨끗 한 설치 및 제거 동작의 약속을 달성 하기 위해 런타임에 파일 시스템 및 레지스트리를 검색 하 고 이러한 변경 내용을 리디렉션합니다.

데스크톱 응용 프로그램에 대해 만드는 패키지는 응용 프로그램에 및에 대 한 쓰기에 적용 되는 경량 가상화가 있지만 샌드 박싱 되지 않는 데스크톱 전용 완전 신뢰 응용 프로그램입니다 `HKCU` `AppData` . 이러한 가상화를 통해 클래식 데스크톱 응용 프로그램에서 수행 하는 것과 동일한 방식으로 다른 앱과 상호 작용할 수 있습니다.

##### <a name="installation"></a>설치

앱 패키지는 ' 실행 파일 ' 이라는 이름의 *% ProgramFiles% \\ windowsapps \\ package_name* 아래에 설치 됩니다  `app_name.exe` . 각 패키지 폴더에는 `AppxManifest.xml` 패키지 된 앱에 대 한 특수 XML 네임 스페이스를 포함 하는 매니페스트 ()가 포함 되어 있습니다. 해당 매니페스트 파일 내에는  `<EntryPoint>`   완전 신뢰 앱을 참조 하는 요소가 있습니다. 응용 프로그램이 시작 되 면 앱 컨테이너 내에서 실행 되지 않고, 대신 일반적으로 사용자로 실행 됩니다.

배포 후 패키지 파일은 운영 체제에 의해 읽기 전용으로 표시 되 고 매우 잠깁니다. 이러한 파일이 변조 되 면 Windows에서 앱을 시작할 수 없습니다.

##### <a name="file-system"></a>파일 시스템

OS는 폴더 위치에 따라 패키지 된 데스크톱 응용 프로그램에 대해 서로 다른 수준의 파일 시스템 작업을 지원 합니다.

사용자의 *AppData* 폴더에 액세스 하려고 할 때 시스템은 백그라운드에서 사용자 단위, 앱 별 앱 위치를 만듭니다. 이렇게 하면 패키지 응용 프로그램에서 실제로 개인 복사를 수정할 때 실제 *AppData* 을 편집 하는 것과 같은 환상 효과를 만들 수 있습니다. 시스템은 이러한 방식으로 쓰기를 리디렉션하여 앱에서 수행 하는 모든 파일 수정 내용을 추적할 수 있습니다. 그러면 시스템 "rot"를 제거 하 고 사용자에 게 더 나은 응용 프로그램 제거 환경을 제공할 때 이러한 모든 파일을 정리할 수 있습니다.

##### <a name="registry"></a>레지스트리

앱 패키지에는  `HKLM\Software` 실제 레지스트리에서와 동등한 논리적으로 사용 되는 레지스트리 .dat 파일이 포함 되어 있습니다.   런타임에이 가상 레지스트리는이 hive의 내용을 네이티브 시스템 hive에 병합 하 여 두 항목의 단일 뷰를 제공 합니다.

모든 쓰기는 패키지를 업그레이드 하는 동안 유지 되며 응용 프로그램을 제거 하는 경우에만 삭제 됩니다.

##### <a name="uninstallation"></a>제거

사용자가 패키지를 제거 하면 아래에 있는 모든 파일 및 폴더가  `C:\Program Files\WindowsApps\package_name` 제거 되 고 AppData 또는 해당 프로세스 중에 캡처된 레지스트리에 리디렉션된 모든 파일이 제거 됩니다.

패키지 응용 프로그램에서 설치, 파일 액세스, 레지스트리 및 제거를 처리 하는 방법에 대 한 자세한 내용은을 참조 하십시오 <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-behind-the-scenes> .

확인할 항목의 전체 목록을 가져올 수 있습니다 <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-prepare> .

## <a name="how-to-add-winrt-apis-to-your-desktop-project"></a>데스크톱 프로젝트에 WinRT Api를 추가 하는 방법

이 섹션에서는 기존 WPF 응용 프로그램에서 알림 메시지를 통합 하는 방법에 대 한 연습을 찾을 수 있습니다. 코드 관점에서 간단 하지만 전체 프로세스를 설명 하는 데 도움이 됩니다. 알림은 .NET 앱에서 사용할 수 있는 사용 가능한 여러 WinRT Api 중 하나입니다. 이 경우 API에는 패키지 Id가 필요 합니다. Api에 패키지 Id가 필요 하지 않은 경우이 프로세스는 더 간단 합니다.

파일을 읽고 화면에 내용을 표시 하는 기존 WPF 샘플 앱을 살펴보겠습니다. 목표는 응용 프로그램이 시작 될 때 알림 메시지를 표시 하는 것입니다.

![실행 중인 샘플 응용 프로그램의 스크린샷](./media/windows-migration/sample-application.png)

먼저, 사용할 Windows 10 API에 패키지 Id가 필요한 지 여부에 대 한 다음 링크를 확인 해야 합니다.

<https://docs.microsoft.com/windows/apps/desktop/modernize/desktop-to-uwp-supported-api>

샘플은 <xref:Windows.UI.Notifications.Notification?displayProperty=nameWithType> 패키지 id가 필요한 API를 사용 합니다.

![Microsoft 설명서의 알림 클래스](./media/windows-migration/notification-class-documentation.png)

WinRT API에 액세스 하려면 NuGet 패키지에 대 한 참조를 추가 합니다 `Microsoft.Windows.SDK.Contracts`   .이 패키지는 백그라운드에서 자동으로 수행 됩니다 (자세한 내용은 참조 <https://blogs.windows.com/windowsdeveloper/2019/04/30/calling-windows-10-apis-from-a-desktop-application-just-got-easier/> ).

이제 일부 코드를 추가 하기 시작할 준비가 되었습니다.

`ShowToastNotification`응용 프로그램 시작 시 호출 되는 메서드를 만듭니다. XML 패턴에서 알림 메시지를 작성 합니다.

```csharp
private void ShowNotification(string title, string content, string image)
{
    string xmlString = $@"<toast><visual><binding template = 'ToastGeneric'><text>{title}</text><text>{content}</text><image src=>'{image}'</image></binding></visual></toast>";
    XmlDocument toastXml = new XmlDocument();
    toastXml.LoadXml(xmlString);
    ToastNotification toast = new ToastNotification(toastXml);
    ToastNotificationManager.CreateToastNotifier().Show(toast);
}
```

프로젝트에는 알림 API에 패키지 Id가 필요 하 고 제공 하지 않았기 때문에 오류가 발생 합니다. 솔루션에 Windows 패키징 프로젝트를 추가 하면 문제가 해결 됩니다.

![Visual Studio의 새 프로젝트 추가 대화 상자 스크린샷](./media/windows-migration/add-packaging-project.png)

지원할 최소 Windows 버전 및 대상으로 지정할 버전을 선택 합니다. 모든 WinRT Api가 모든 Windows 10 버전에서 지원 되는 것은 아닙니다. 각 Windows 10 업데이트는이 버전 에서만 사용할 수 있는 새 Api를 추가 합니다. 하위 수준 지원을 사용할 수 없습니다.

![최소 Windows 버전 선택](./media/windows-migration/select-versions.png)

다음 단계는 프로젝트 참조를 추가 하 여 Windows 패키징 프로젝트에 WPF 응용 프로그램을 추가 하는 것입니다.

![Windows 패키징 프로젝트에 WPF 응용 프로그램 추가](./media/windows-migration/add-application.png)

![참조 관리자](./media/windows-migration/reference-manager.png)

Windows 패키징 프로젝트는 여러 앱을 패키지할 수 있으므로 진입점을 설정 해야 합니다.

![진입점 설정](./media/windows-migration/set-entry-point.png)

다음 단계는 솔루션 구성에서 WPF 프로젝트를 시작 프로젝트로 설정 하는 것입니다. F5 키를 눌러 컴파일 및 작성 하 고 결과를 볼 수 있습니다.

![실행 중인 샘플 응용 프로그램 및 결과 표시](./media/windows-migration/sample-app-result.png)

앱을 설치할 수 있도록 패키지를 생성 해 보겠습니다. **스토어**  >  **앱 패키지 만들기** 를 마우스 오른쪽 단추로 클릭 합니다.

![앱 패키지 만들기 대화 상자](./media/windows-migration/create-app-packages.png)

컴퓨터에서 앱을 배포 하려면 테스트용 로드 옵션을 선택 합니다.

![테스트용 로드 옵션 선택](./media/windows-migration/select-sideloading-option.png)

앱의 응용 프로그램 아키텍처를 선택 합니다.

![응용 프로그램 아키텍처 선택](./media/windows-migration/select-app-architecture.png)

마지막으로 **만들기** 를 클릭 하 여 패키지를 만듭니다.

## <a name="xaml-islands"></a>XAML Islands

XAML 아일랜드는 Windows 데스크톱 개발자가 Windows Forms 및 WPF를 비롯 한 기존 Win32 응용 프로그램에서 UWP XAML 컨트롤을 사용할 수 있도록 하는 구성 요소 집합입니다.

![XAML 아일랜드의 구조](./media/windows-migration/xaml-islands.png)

표준 컨트롤을 사용 하 여 Win32 앱을 이미지 하 고 현대적인 세계의 컨트롤을 포함 하는 UWP UI의 "아일랜드"로 이미지를 만들 수 있습니다. 이 개념은에서 콘텐츠를 표시 하는 웹 페이지에 iFrame을 포함 하는 것과 유사 합니다. `different page.`

Windows 10 Api의 기능을 추가 하는 것 외에도 XAML 아일랜드를 사용 하 여 앱 내에 UWP XAML의 일부를 추가할 수 있습니다.

Windows 10 1903 업데이트에는 Win32 창에서 UWP XAML 콘텐츠 호스팅을 허용 하는 Api 집합이 도입 되었습니다. Windows 10 1903에서 실행 되는 앱에만 XAML 아일랜드를 사용할 수 있습니다.

### <a name="the-road-to-xaml-islands"></a>XAML로의 이동 제도

Microsoft에서 Win32 앱 (Windows Forms, WPF 및 네이티브 Win32 앱)을 현대화 하는 프레임 워크로 WinRT Api를 도입 하는 경우 XAML 아일랜드가 2012에서 시작 되었습니다. 그러나 WinRT 내부의 새 UI 컨트롤은 새 응용 프로그램에 사용할 수 있었지만 기존 응용 프로그램에 대해서는 사용할 수 없습니다.

2015에서는 Windows 10과 함께 UWP가 탄생 했습니다. UWP를 사용 하면 XBox, Mobile, Desktop 등의 Windows 장치에서 작동 하는 앱을 만들 수 있습니다. 1 년 후에 Microsoft는 데스크톱 브리지 (이전의 Project Centennial)를 발표 했습니다. 데스크톱 브리지는 개발자가 기존 Win32 앱을 Microsoft Store으로 가져올 수 있도록 하는 도구 집합입니다. 2017에 추가 기능이 추가 되어 개발자가 작업 센터의 라이브 타일 및 알림과 같은 새로운 Windows 10 Api를 활용 하는 Win32 앱을 향상 시킬 수 있습니다. 그러나 아직 새 UI 컨트롤은 없습니다.

빌드 2018에서 Microsoft는 개발자가 앱을 UWP로 완전히 마이그레이션하지 않고도 새 Windows 10 XAML 컨트롤을 현재 Win32 앱에 사용할 수 있는 방법을 발표 했습니다. UWP XAML 아일랜드의 브랜드 였습니다.

### <a name="how-it-works"></a>작동 방식

Windows 10 1903 업데이트에는 몇 가지 XAML 호스팅 Api가 도입 되었습니다. 그 중 두 가지는 `WindowsXamlManager`   및  `DesktopWindowXamlSource` 입니다.

 `WindowsXamlManager`   클래스는 UWP XAML 프레임 워크를 처리 합니다. 해당 `InitializeForCurrentThread` 메서드는 Win32 응용 프로그램의 현재 스레드 내에서 UWP XAML 프레임 워크를 로드 합니다.

는  `DesktopWindowXamlSource`   XAML 아일랜드 콘텐츠의 인스턴스입니다. 이 클래스에는 `Content` 인스턴스화하고 설정 해야 하는 속성이 있습니다. 는를 `DesktopWindowXamlSource`   렌더링 하 고 HWND에서 해당 입력을 가져옵니다. XAML 아일랜드를 연결할 다른 HWND를 알고 있어야 하며, 부모의 HWND 크기를 조정 하 고 위치를 지정 해야 합니다.

WPF 또는 Windows Forms 개발자는 일반적으로 코드 내에서 HWND를 처리 하지 않으므로 HWND 포인터를 이해 하 고 처리 하 고 Win32 및 UWP 환경을 전달 하는 기본 연결을 처리 하기 어려울 수 있습니다.

#### <a name="the-xaml-islands-net-wrappers"></a>XAML 아일랜드 .NET 래퍼

Windows 커뮤니티 도구 키트에는 XAML 아일랜드를 보다 쉽게 사용할 수 있도록 하는 WPF 또는 Windows Forms에 대 한 XAML 아일랜드 .NET 래퍼가 설정 되어 있습니다. 이러한 래퍼는 Hwnd, 포커스 관리 등을 관리 합니다. Windows Forms 및 WPF 개발자는 이러한 래퍼를 사용 해야 합니다.

Windows 커뮤니티 도구 키트는 래핑된 컨트롤과 호스트 컨트롤 이라는 두 가지 형식의 컨트롤을 제공 합니다.

##### <a name="wrapped-controls"></a>래핑된 컨트롤

이러한 래핑된 컨트롤은 일부 UWP 컨트롤을 Windows Forms 또는 WPF 컨트롤로 래핑하고 해당 개발자에 대 한 UWP 개념을 숨깁니다. 이러한 컨트롤은 다음과 같습니다.

* 웹 보기 및 WebViewCompatible
* InkCanvas 및 InkToolbar
* MediaPlayerElement
* MapControl

프로젝트에 패키지를 추가 하 고 `Microsoft.Toolkit.Wpf.UI.Controls` 네임 스페이스에 대 한 참조를 포함 한 다음 사용을 시작 합니다.

```xml
<Window
        ...
        xmlns:uwpControls="clr-namespace:Microsoft.Toolkit.Wpf.UI.Controls;assembly=Microsoft.Toolkit.Wpf.UI.Controls">
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="\*"/>
    </Grid.RowDefinitions>
    <uwpControls:InkToolbar TargetInkCanvas="{x:Reference Name=inkCanvas}"/>
    <uwpControls:InkCanvas Grid.Row="1" x:Name="inkCanvas" />
</Grid>
```

##### <a name="hosting-controls"></a>컨트롤 호스팅

XAML 아일랜드의 강력한 기능을 사용 하면 대부분의 자사 컨트롤, 타사 컨트롤 및 UWP 용으로 개발 된 사용자 지정 컨트롤을 확장할 수 있습니다 .이 컨트롤은 모든 기능을 갖춘 UI를 사용 하 여 "아일랜드"로 Windows Forms 및 WPF에 통합할 수 있습니다. `WindowsXamlHost`WPF 및 Windows Forms에 대 한 컨트롤을 통해이 작업을 수행할 수 있습니다.

예를 들어 `WindowsXamlHost` WPF에서 컨트롤을 사용 하려면 `Microsoft.Toolkit.Wpf.UI.XamlHost` Windows 커뮤니티 도구 키트에서 제공 하는 패키지에 대 한 참조를 추가 합니다.

을 `WindowsXamlHost` UI 코드에 배치한 후에는 로드 하려는 UWP 형식을 지정 합니다. `Button`사용자 지정 UWP 컨트롤인 여러 다른 컨트롤로 구성 된 또는 보다 복잡 한 컨트롤 처럼 래핑된 컨트롤을 사용 하도록 선택할 수 있습니다.

다음 예제에서는 UWP를 추가 하는 방법을 보여 줍니다 `Button` .

```xml
<Window
        ...
        xmlns:xamlhost="clr-namespace:Microsoft.Toolkit.Wpf.UI.XamlHost;assembly=Microsoft.Toolkit.Wpf.UI.XamlHost">

<xamlhost:WindowsXamlHost x:Name="myUwpButton"
                          InitialTypeName="Windows.UI.Xaml.Controls.Button" />
```

이에 접근 하는 방법에 대 한 명확한 권장 사항이 있으므로 사용자 지정 복합 컨트롤을 포함 하는 하나 이상의 단일 XAML 아일랜드에는 하나의 컨트롤을 포함 하는 여러 개의 아일랜드를 포함 하는 것이 좋습니다.

XAML의 핵심 기능 중 하나는 바인딩 이며 Win32 코드와 아일랜드 간에 작동 합니다. 따라서 UWP를 사용 하 여 Win32를 바인딩할 수 있습니다 `Textbox` `Textbox` . 고려해 야 할 중요 한 한 가지 사항은 이러한 바인딩이 UWP에서 Win32에 이르기까지 단방향 바인딩 이기 때문입니다. XAML 아일랜드 내에서를 업데이트 하는 경우에는 `Textbox` Win32 텍스트 상자가 업데이트 되지만 그 밖의 방법은 업데이트 되지 않습니다.

XAML 아일랜드를 사용 하는 방법에 대 한 연습은 다음을 참조 하세요.

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-standard-control-with-xaml-islands>

#### <a name="adding-uwp-xaml-custom-controls"></a>UWP XAML 사용자 지정 컨트롤 추가

XAML 사용자 지정 컨트롤은 사용자 또는 제 3 자가 만든 컨트롤 (또는 사용자 정의 컨트롤)입니다 (WinUI 2.x 컨트롤 포함). Windows Forms 또는 WPF 앱에서 사용자 지정 UWP 컨트롤을 호스트 하려면 다음이 필요 합니다.

- `WindowsXamlHost`.Net Core 2.x 앱에서 UWP 컨트롤을 사용 하려면
- 개체를 정의 하는 UWP 앱 프로젝트를 만듭니다 `XamlApplication` .

WPF 또는 Windows Forms 프로젝트에 `Microsoft.Toolkit.Win32.UI.XamlHost.XamlApplication` 는 Windows 커뮤니티 도구 키트에서 제공 하는 클래스의 인스턴스에 대 한 액세스 권한이 있어야 합니다. 이 개체는 응용 프로그램의 현재 디렉터리에 있는 어셈블리의 사용자 지정 UWP XAML 형식에 대 한 메타 데이터를 로드 하기 위한 루트 메타 데이터 공급자로 작동 합니다. 이렇게 하려면 빈 앱 (유니버설 Windows) 프로젝트를 WPF 또는 Windows Forms 프로젝트와 동일한 솔루션에 추가 하 고이 프로젝트의 기본 App 클래스를 수정 합니다.

사용자 지정 UWP XAML 컨트롤은이 UWP 앱 또는 WPF 또는 Windows Forms 프로젝트와 동일한 솔루션에서 참조 하는 독립 UWP 클래스 라이브러리 프로젝트에 포함 될 수 있습니다.

자세한 단계별 프로세스 설명은 다음에서 확인할 수 있습니다.

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

#### <a name="the-windows-ui-library-winui-2"></a>Windows UI 라이브러리 (WinUI 2)

OS와 함께 제공 되는 수신함 Windows 10 컨트롤 외에도 동일한 UWP XAML 팀은 Windows UI 라이브러리 (**WinUI 2**)에서 추가 컨트롤을 제공 합니다. WinUI 2는 Windows UWP 앱에 대 한 공식적인 네이티브 Microsoft UI 컨트롤 및 기능을 제공 하며, 이러한 컨트롤은 XAML 아일랜드 내에서 사용할 수 있습니다.

WinUI 2는 오픈 소스 이며에서 정보를 찾을 수 있습니다 <https://github.com/microsoft/microsoft-ui-xaml> .

다음 문서에서는 WinUI 2 라이브러리에서 UWP XAML 컨트롤을 호스트 하는 방법을 보여 줍니다. <https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

### <a name="do-you-need-xaml-islands"></a>XAML 아일랜드가 필요 합니다.

XAML 아일랜드는 응용 프로그램을 완전히 다시 작성 하지 않고도 새 UWP 컨트롤 및 동작을 활용 하 여 사용자 환경을 개선 하고자 하는 기존 Win32 앱을 위한 것입니다.  [Windows 10 api](/windows/uwp/porting/desktop-to-uwp-enhance)를 이미 활용할 수 있지만 XAML 아일랜드 까지는 UI가 아닌 api를 사용할 수 있습니다.

새 Windows 앱을 개발 하는 경우 [UWP 앱](/windows/uwp/get-started/universal-application-platform-guide)   이 올바른 방법일 수 있습니다.

### <a name="the-road-ahead-xaml-islands-winui-30"></a>XAML 아일랜드 앞으로 이동: WinUI 3.0

Windows 8부터 XAML UI 프레임 워크, 시각적 컴퍼지션 계층 및 입력 처리를 비롯 한 Windows UI 플랫폼은 Windows의 필수적인 부분으로 제공 됩니다. 즉, UI 기술의 최신 향상 기능을 활용 하려면 최신 버전의 UI로 업그레이드 하 여 앱을 개발할 때 혁신의 속도를 저하 해야 합니다. 이러한 두 가지 진화 주기를 분리 하 고 혁신을 촉진 하기 위해 Microsoft는 적극적으로 WinUI 프로젝트를 진행 하 고 있습니다.

2018에서 WinUI 2부터 Microsoft는 UWP SDK를 기반으로 구축 되는 별도의 NuGet 패키지로 몇 가지 새로운 XAML UI 컨트롤 및 기능을 출시 하기 시작 했습니다.

![WinUI 2.0의 구조](./media/windows-migration/winui2.png)

WinUI 3은 활성 개발 중 이며, 전체 UI 플랫폼을 포함 하도록 WinUI의 범위를 크게 확장 하며,이는 UWP SDK와 완전히 분리 됩니다.

![WinUI 3.0의 구조](./media/windows-migration/winui3.png)

이제 GitHub에서 XAML 프레임 워크가 개발 되 고 [NuGet](/nuget/what-is-nuget)패키지로 대역 외에서 제공 됩니다   .

OS의 일부로 제공되는 기존 UWP XAML API는 더 이상 새로운 기능 업데이트를 받지 않습니다. Windows 10 지원 주기에 따라 보안 업데이트 및 중요 한 수정이 계속 수신 됩니다.

유니버설 Windows 플랫폼에는 XAML 프레임 워크 (예: 응용 프로그램 및 보안 모델, 미디어 파이프라인, Xbox 및 Windows 10 shell 통합, 광범위 한 장치 지원)가 포함 되며 계속 해 서 진화 하 고 있습니다. 모든 새 XAML 기능이 개발 되 고 대신 WinUI의 일부로 제공 됩니다.

#### <a name="winui-3-in-desktop-app-and-winui-xaml-islands"></a>WinUI 3 (데스크톱 앱 및 WinUI XAML 제도)

여기서 볼 수 있듯이 WinUI 3은 UWP XAML의 진화 이며 UWP 앱 모델 및 해당 요구 사항 (MSIX 패키지 ID, 샌드박스, CoreWindow 등) 내에서 자연스럽 게 작동 합니다. WinUI 3을 Win32 앱 모델에서 사용 하려면 WinUI 콘텐츠를 **WINUI XAML 아일랜드** 를 사용 하는 다른 UI 프레임 워크 (WINDOWS FORMS, WPF 등)에서 호스팅해야 합니다. 앱을 개선 하 고 기술을 혼합 하려는 경우 적합 한 경로입니다. 그러나 WinUI에 대 한 전체 이전 UI를 대체 하려는 경우 응용 프로그램에서 WinUI 호스트에 대 한 UI 프레임 워크를 로드 하지 않아야 합니다.

WinUI 3은 **데스크톱 앱에서 WinUI를** 추가 하는이 중요 한 피드백을 해결 합니다. 이렇게 하면 Win32 앱이 독립 실행형 UI 프레임 워크로 WinUI 3을 사용할 수 있습니다. Windows Forms 또는 WPF를 로드할 필요가 없습니다.

이 집계 내에서 WinUI 3을 통해 개발자는 다음의 오른쪽 조합을 쉽게 조합 하 고 일치 시킬 수 있습니다.

* 앱 모델: UWP, Win32
* 플랫폼: .NET Core 또는 네이티브
* 언어: .NET (C \# , Visual Basic), 표준 c + +
* 패키징: MSIX, Microsoft Store에 대 한 AppX, 패키지 되지 않은
* Interop: WinUI 3을 사용 하 여 WinUI XAML 아일랜드를 사용 하는 기존 WPF, WinForms 및 MFC 앱을 확장 합니다.

자세한 정보를 확인 하려는 경우 Microsoft는에서이 로드맵을 공유 하 고 있습니다 <https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md> .

>[!div class="step-by-step"]
>[이전](migrate-modern-applications.md)
>[다음](example-migration-core.md)
