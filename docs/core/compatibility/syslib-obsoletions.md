---
title: .NET 5+에서 사용되지 않는 기능
description: .NET 5.0 이상 버전에서 SYSLIB 컴파일러 경고를 생성하고 사용되지 않는 것으로 표시되는 API에 대해 알아봅니다.
ms.date: 10/20/2020
ms.openlocfilehash: aa5716ba8fe46c7c4ae2faafe7cc963551eecef7
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440766"
---
# <a name="obsolete-features-in-net-5"></a>.NET 5+에서 사용되지 않는 기능

.NET 5.0부터 사용되지 않는 것으로 새로 표시되는 일부 API는 <xref:System.ObsoleteAttribute>에서 두 개의 새 속성을 사용합니다.

- <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> 속성은 사용자 지정 진단 ID를 사용하여 빌드 경로를 생성하도록 컴파일러에 알립니다. 사용자 지정 ID를 사용하면 사용되지 않음 경고를 별도로 표시하지 않을 수 있습니다. .NET 5+ 사용되지 않음에서 사용자 지정 진단 ID의 형식은 `SYSLIBxxxx`입니다.

- <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> 속성은 사용되지 않음에 대한 자세한 정보를 제공하는 URL 링크를 포함하도록 컴파일러에 알립니다.

사용되지 않는 API 사용으로 인해 빌드 경고나 오류가 발생하면 [참조](#reference) 섹션에 나열된 진단 ID에 대해 제공되는 특정 지침을 따르세요. 이러한 사용되지 않음에 대한 경고나 오류는 사용되지 않는 형식이나 멤버에 대한 [표준 진단 ID(CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md)를 사용하여 표시하지 않을 수 ‘없으며’, 사용자 지정 `SYSLIBxxxx` 진단 ID를 대신 사용해야 합니다. 자세한 내용은 [경고 표시 안 함](#suppress-warnings)을 참조하세요.

## <a name="reference"></a>참조

다음 표에서는 .NET 5+의 `SYSLIBxxxx` 사용되지 않음에 대한 인덱스를 제공합니다.

| 진단 ID | Description |
| - | - |
| [SYSLIB0001](syslib0001.md) | UTF-7 인코딩은 안전하지 않으므로 사용해서는 안 됩니다. 대신 UTF-8을 사용하세요. |
| [SYSLIB0002](syslib0002.md) | <xref:System.Security.Permissions.PrincipalPermissionAttribute>는 런타임에 적용되지 않으며 사용해서는 안 됩니다. |
| [SYSLIB0003](syslib0003.md) | CAS(코드 액세스 보안)가 런타임에 지원되거나 적용되지 않습니다. |
| [SYSLIB0004](syslib0004.md) | CER(제약이 있는 실행 영역) 기능이 지원되지 않습니다. |
| [SYSLIB0005](syslib0005.md) | GAC(전역 어셈블리 캐시)가 지원되지 않습니다. |
| [SYSLIB0006](syslib0006.md) | <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>이 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다. |
| [SYSLIB0007](syslib0007.md) | 이 암호화 알고리즘의 기본 구현이 지원되지 않습니다. |
| [SYSLIB0008](syslib0008.md) | <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다. |
| [SYSLIB0009](syslib0009.md) | <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> 및 <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> 메서드가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다. |
| [SYSLIB0010](syslib0010.md) | 일부 원격 API가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다. |
| [SYSLIB0011](syslib0011.md) | <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization이 사용되지 않으며 사용해서는 안 됩니다. |
| [SYSLIB0012](syslib0012.md) | <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> 및 <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>은 .NET Framework 호환성을 위해서만 포함됩니다. 대신 <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>를 사용하세요. |

## <a name="suppress-warnings"></a>경고 표시 안 함

사용되지 않는 API를 사용해야 하고 `SYSLIBxxxx` 진단에서 오류로 표시되는 경우 코드 또는 프로젝트 파일에서 경고를 표시하지 않을 수 있습니다.

코드

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

프로젝트 파일:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
   <!-- To suppress multiple warnings, you can use multiple NoWarn elements -->
   <NoWarn>$(NoWarn);SYSLIB0002</NoWarn>
   <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
   <!-- Alternatively, you can suppress multiple warnings by using a semicolon-delimited list -->
   <NoWarn>$(NoWarn);SYSLIB0001;SYSLIB0002;SYSLIB0003</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> 이런 식으로 경고를 표시하지 않으면 지정한 사용하지 않음 경고만 사용하지 않도록 설정됩니다. 진단 ID가 다른 사용하지 않음 경고를 포함하여 다른 모든 경고는 사용하지 않도록 설정되지 않습니다.
