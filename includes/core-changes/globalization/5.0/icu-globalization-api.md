---
ms.openlocfilehash: 74c3d3247912dcd638a9379d54e682967c5e400b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302717"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a>Windows에서 세계화 API가 ICU 라이브러리를 사용

.NET 5.0 이상 버전에서는 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 세계화 기능에 [ICU(International Components for Unicode)](http://site.icu-project.org/home) 라이브러리를 사용합니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 .NET 라이브러리가 세계화 기능에 [NLS(국가별 언어 지원)](/windows/win32/intl/national-language-support) API를 사용했습니다. 예를 들어, NLS 함수는 날짜 및 시간 형식 패턴, 문자열 비교, 해당 문화권에서 문자열 대/소문자 구분 등의 문화권 데이터를 가져오는 데 사용되었습니다.

.NET 5.0부터 앱이 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 .NET 라이브러리가 [ICU](http://site.icu-project.org/home) 세계화 API를 사용합니다. Windows 10 2019년 5월 업데이트 이상 버전에는 ICU 네이티브 라이브러리가 함께 제공됩니다. .NET 런타임에서 ICU를 로드할 수 없는 경우 대신 NLS를 사용합니다.

이러한 변경 내용은 다음 두 가지 이유로 도입되었습니다.

- 앱은 Linux, macOS 및 Windows를 비롯한 여러 플랫폼에서 동일한 세계화 동작을 포함합니다.
- 앱은 사용자 지정 ICU 라이브러리를 사용하여 세계화 동작을 제어할 수 있습니다.

#### <a name="version-introduced"></a>도입된 버전

.NET 5.0 미리 보기 4

#### <a name="recommended-action"></a>권장 조치

개발자는 아무 작업도 수행하지 않아도 됩니다. 하지만 NLS 세계화 API를 계속 사용하려는 경우 [런타임 스위치](../../../../docs/core/run-time-config/globalization.md#nls)를 설정하여 해당 동작으로 되돌릴 수 있습니다. 사용 가능한 스위치에 대한 자세한 내용은 [.NET 세계화 및 ICU](/dotnet/standard/globalization-localization/globalization-icu) 문서를 참조하세요.

#### <a name="category"></a>범주

전역화

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <xref:System.Globalization?displayProperty=fullName> 네임스페이스의 대부분의 형식

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
