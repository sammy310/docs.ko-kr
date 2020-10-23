---
ms.openlocfilehash: 47c676122df4f0990949a7bfbcd7af8c6144d870
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160547"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a>WinRT의 기본 제공 지원이 .NET에서 제거됨

.NET에서 [WinRT(Windows 런타임)](/uwp/winrt-cref/winrt-type-system) API 사용을 위한 기본 제공 지원이 제거되었습니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 6

#### <a name="change-description"></a>변경 내용 설명

이전에는 CoreCLR이 [WinMD(Windows 메타데이터) 파일](/uwp/winrt-cref/winmd-files)을 사용하여 WinRT 형식을 활성화하고 사용할 수 있었습니다. .NET 5.0부터 CoreCLR은 더 이상 WinMD 파일을 직접 사용할 수 없습니다.

지원되지 않는 어셈블리를 참조하려고 하면 <xref:System.IO.FileNotFoundException>이 발생합니다. WinRT 클래스를 활성화하는 경우 <xref:System.PlatformNotSupportedException>이 발생합니다.

이 호환성이 손상되는 변경은 다음과 같은 이유로 적용되었습니다.

- WinRT를 .NET 런타임과 별도로 개발하고 개선할 수 있습니다.
- iOS, Android 등의 다른 운영 체제용으로 제공되는 interop 시스템과의 대칭을 이룰 수 있습니다.
- C# 기능, IL(중간 언어) 연결 및 AOT(Ahead-Of-Time) 컴파일과 같은 다른 .NET 기능을 활용할 수 있습니다.
- .NET 런타임 코드베이스를 간소화하기 위해서입니다.

#### <a name="recommended-action"></a>권장 조치

- [Microsoft.Windows.SDK.Contracts 패키지](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts)에 대한 참조를 제거합니다.  대신 프로젝트의 `TargetFramework` 속성을 통해 액세스하려는 Windows API의 버전을 지정합니다.  예를 들면 다음과 같습니다.

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- [C#/WinRT](/windows/uwp/csharp-winrt/) 도구 체인을 사용하여 .NET 5.0 이상 버전용 WinRT API 및 형식을 생성하거나 사용자 지정합니다.

#### <a name="category"></a>범주

Interop

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
