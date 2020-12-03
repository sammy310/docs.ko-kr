---
title: '호환성이 손상되는 변경: CA1416: 플랫폼 호환성'
description: 코드 분석 규칙 CA1416 사용으로 발생하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/29/2020
ms.openlocfilehash: ec3fc809b8de382a2093fc9f2d33c2f96b91613d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759595"
---
# <a name="warning-ca1416-platform-compatibility"></a>경고 CA1416: 플랫폼 호환성

.NET 코드 분석기 규칙 [CA1416](/visualstudio/code-quality/ca1416)은 .NET 5.0부터 기본적으로 사용됩니다. 운영 체제를 확인하지 않는 호출 사이트에서 플랫폼별 API에 대한 호출의 빌드 경고를 생성합니다.

## <a name="change-description"></a>변경 내용 설명

.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다. [CA1416](/visualstudio/code-quality/ca1416)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다. 규칙 CA1416은 플랫폼 컨텍스트가 확인되지 않는 위치에서 플랫폼별 API를 사용하는 경우 알림을 제공합니다.

규칙 [CA1416](/visualstudio/code-quality/ca1416), 플랫폼 호환성 분석기는 .NET 5.0에 새로 도입된 다른 일부 기능과 함께 작동합니다. .NET 5.0에는 API를 ‘지원’하거나 ‘지원하지 않는’ 플랫폼을 지정할 수 있는 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 및 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>가 도입되었습니다.  이러한 특성이 없으면 API는 모든 플랫폼에서 지원되는 것으로 간주됩니다. 해당 특성은 핵심 .NET 라이브러리의 플랫폼별 API에 적용되었습니다.

해당 API를 사용할 수 없는 플랫폼을 대상으로 하는 프로젝트에서 규칙 [CA1416](/visualstudio/code-quality/ca1416)은 플랫폼 컨텍스트가 확인되지 않는 플랫폼별 API 호출을 플래그로 지정합니다. 현재 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 및 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> 특성으로 데코레이트된 대부분의 API는 지원되지 않는 운영 체제에서 호출되는 경우 <xref:System.PlatformNotSupportedException> 예외를 throw합니다. 이러한 API는 플랫폼별로 표시되어 있으므로 규칙 [CA1416](/visualstudio/code-quality/ca1416)을 사용하면 호출 사이트에 OS 검사를 추가하여 런타임 <xref:System.PlatformNotSupportedException> 예외를 방지하는 데 도움이 됩니다.

## <a name="examples"></a>예제

- <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> 메서드는 Windows에서만 지원되고 `[SupportedOSPlatform("windows")]`으로 데코레이트됩니다. 다음 코드는 프로젝트가 `net5.0-windows`가 아닌 `net5.0`을 [대상](../../../../standard/frameworks.md)으로 하는 경우 빌드 시 CA1416 경고를 생성합니다. 경고를 방지하기 위해 수행할 수 있는 작업은 [권장 조치](#recommended-action)를 참조하세요.

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> 메서드는 브라우저에서 지원되지 않으며 `[UnsupportedOSPlatform("browser")]`으로 데코레이트됩니다. 다음 코드는 프로젝트가 브라우저 플랫폼을 지원하는 경우 빌드 시 CA1416 경고를 생성합니다.

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - Blazor WebAssembly 프로젝트 및 Razor 클래스 라이브러리 프로젝트에는 브라우저 지원이 자동으로 포함됩니다.
  > - 프로젝트에 지원되는 플랫폼으로 수동으로 브라우저를 추가하려면 프로젝트 파일에 다음 항목을 추가하세요.
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

적절한 플랫폼에서 코드가 실행되는 경우에만 플랫폼별 API가 호출되도록 합니다. 플랫폼별 API를 호출하기 전에 <xref:System.OperatingSystem?displayProperty=nameWithType> 클래스에서 `Is<Platform>` 메서드 중 하나(예: <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>)를 사용하여 현재 운영 체제를 확인할 수 있습니다.

`if` 문의 조건에 `Is<Platform>` 메서드 중 하나를 사용할 수 있습니다.

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

또는 런타임에 추가 `if` 문의 오버헤드를 원하지 않는다면 대신 <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>를 호출합니다.

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

라이브러리를 제작하는 경우 API를 플랫폼별로 표시할 수 있습니다. 이 경우 요구 사항을 확인하는 것은 호출자의 책임입니다. 특정 메서드나 유형 또는 전체 어셈블리를 표시할 수 있습니다.

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

모든 호출 사이트를 수정하지는 않으려면 다음 옵션 중 하나를 선택하여 경고를 중지할 수 있습니다.

- 규칙 CA1416을 중지하려면 `#pragma` 또는 [-nowarn](../../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) 컴파일러 플래그를 사용하거나 editorconfig 파일에서 [규칙의 심각도](../../../../fundamentals/code-analysis/configuration-options.md#severity-level)를 `none`으로 설정하면 됩니다.

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

Windows 플랫폼:

- <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>에 나열된 모든 API
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

Blazor WebAssembly 플랫폼:

- <https://github.com/dotnet/runtime/issues/41087>에 나열된 모든 API

<!--

### Affected APIs

- ``

### Category

- Code analysis
- Core .NET libraries

-->

## <a name="see-also"></a>참고 항목

- [CA1416: 플랫폼 호환성 유효성 검사](/visualstudio/code-quality/ca1416)
- [.NET API 분석기](../../../../standard/analyzers/api-analyzer.md)
