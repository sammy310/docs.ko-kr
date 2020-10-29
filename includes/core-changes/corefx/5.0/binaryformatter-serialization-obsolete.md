---
ms.openlocfilehash: 43bd1481ca6c3d3444afda2e2a2c67e7236b4402
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434904"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a>ASP.NET 앱에서 BinaryFormatter serialization 메서드가 사용되지 않고 금지됨

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> 및 <xref:System.Runtime.Serialization.IFormatter>에 대한 `Serialize` 및 `Deserialize` 메서드는 이제 경고로 표시되며 더 이상 사용되지 않습니다. 또한 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization은 ASP.NET 앱에서 기본적으로 금지됩니다.

#### <a name="change-description"></a>변경 내용 설명

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>의 [보안 취약성](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) 때문에 다음 메서드는 이제 사용되지 않으며 `SYSLIB0011` ID를 사용하여 컴파일 시간 경고를 생성합니다. 또한 ASP.NET Core 5.0 이상 앱에서 웹앱이 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 기능을 다시 사용하도록 설정하지 않는 한 <xref:System.NotSupportedException>이 throw됩니다.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

다음 serialization 메서드도 더 이상 사용되지 않으며 `SYSLIB0011` 경고를 생성하지만 동작은 변경되지 않습니다.

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

#### <a name="reason-for-change"></a>변경 이유

이러한 메서드는 .NET 에코시스템에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 사용을 줄이기 위한 노력의 일환으로 사용되지 않음으로 표시됩니다.

#### <a name="recommended-action"></a>권장 조치

- 코드에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 사용을 중단합니다. 대신, <xref:System.Text.Json.JsonSerializer> 또는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하는 것이 좋습니다. 자세한 내용은 [BinaryFormatter 보안 가이드](../../../../docs/standard/serialization/binaryformatter-security-guide.md)를 참조하세요.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 컴파일 시간 경고 `SYSLIB0011`을 일시적으로 표시하지 않을 수 있습니다. 이 옵션을 선택하기 전에 코드에서 위험을 철저히 평가하는 것이 좋습니다. 경고를 표시하지 않는 가장 쉬운 방법은 개별 호출 사이트를 `#pragma` 지시문으로 묶는 것입니다.

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  프로젝트 파일에서도 경고를 표시하지 않을 수 있습니다.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  프로젝트 파일에서 경고를 표시하지 않으면 프로젝트의 모든 코드 파일에서 경고가 표시되지 않습니다. `SYSLIB0011`을 표시하지 않아도 다른 사용되지 않는 API를 사용하여 발생하는 경고는 표시됩니다.

- ASP.NET 앱에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>를 계속 사용하려면 프로젝트 파일에서 다시 사용하도록 설정할 수 있습니다. 그러나 이렇게 하지 않는 것이 좋습니다. 자세한 내용은 [BinaryFormatter 보안 가이드](../../../../docs/standard/serialization/binaryformatter-security-guide.md)를 참조하세요.

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

권장 작업에 대한 자세한 내용은 [BinaryFormatter 사용 중지 및 비활성화 오류 해결](https://aka.ms/binaryformatter)을 참조하세요.

#### <a name="category"></a>범주

- 핵심 .NET 라이브러리
- ASP.NET

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
