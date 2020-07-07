---
ms.openlocfilehash: 148312743dd274728b178951548889dc3a680528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614695"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>ZipArchiveEntry 개체의 FullName 속성에서 경로 구분 기호 문자 변경

#### <a name="details"></a>설명

.NET Framework 4.6.1 이상 버전을 대상으로 하는 앱의 경우 <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> 메서드의 오버로드를 통해 생성된 <xref:System.IO.Compression.ZipArchiveEntry> 개체의 <xref:System.IO.Compression.ZipArchiveEntry.FullName> 속성에서 경로 구분 기호 문자가 백슬래시(\")에서 슬래시(/)로 변경되었습니다. 이 변경으로 인해 .NET 구현은 [.ZIP 파일 형식 사양](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)의 섹션 4.4.17.1과 일치하게 되고 비 Windows 시스템에서.ZIP 아카이브의 압축이 풀리게 됩니다.<br />Macintosh와 같은 비 Windows 운영 체제에서 이전 버전의 .NET Framework를 대상으로 하는 앱이 생성한 zip 파일의 압축을 풀면 디렉터리 구조가 유지되지 않습니다. 예를 들어 Macintosh에서는 해당 파일 이름이 디렉터리 경로, 백슬래시("") 문자 및 파일 이름으로 연결된 파일 집합이 만들어집니다. 결과적으로 압축을 푼 파일의 디렉터리 구조는 유지되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework <xref:System.IO?displayProperty=nameWithType> 네임스페이스의 API는 슬래시("/") 또는 백슬래시("\"")를 경로 구분 기호 문자로 원활하게 처리할 수 있으므로 이러한 API에 의해 Windows 운영 체제에서 압축 해제된 .ZIP 파일에 이러한 변경이 미치는 영향은 최소로 유지될 것입니다.<br />이 변경을 원치 않을 경우 애플리케이션 구성 파일의 [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 옵트아웃할 수 있습니다. 다음 예제에서는 `<runtime>` 섹션 및 `Switch.System.IO.Compression.ZipFile.UseBackslash` 옵트아웃 스위치를 모두 보여줍니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.1 이상 버전에서 실행되는 앱은 애플리케이션 구성 파일의 [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 구성 설정을 추가하여 이 동작을 옵트인할 수 있습니다. 다음에서는 `<runtime>` 섹션 및 `Switch.System.IO.Compression.ZipFile.UseBackslash` 옵트인 스위치를 모두 보여줍니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6.1       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
