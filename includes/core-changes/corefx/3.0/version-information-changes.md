---
ms.openlocfilehash: 1580c8c8b7bdad91656f494537230293dbaaf93b
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021622"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함

.NET Core의 버전을 반환하는 대부분의 API가 이제 파일 버전이 아닌 제품 버전을 반환합니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Core 2.2 및 이전 버전에서는 <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> 등의 메서드와 .NET Core 어셈블리의 파일 속성 대화 상자에 파일 버전이 반영됩니다. .NET Core 3.0부터는 제품 버전이 반영됩니다.

다음 그림은 **Windows 탐색기** 파일 속성 대화 상자에 표시되는 .NET Core 2.2(왼쪽) 및 .NET Core 3.0(오른쪽)에 대한 *System.Runtime.dll* 어셈블리의 버전 정보 차이를 보여 줍니다.

![제품 버전 정보 차이](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

없음 이 변경을 통해 직관적인 버전 검색이 가능합니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
