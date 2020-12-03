---
title: '호환성이 손상되는 변경: CA1417: P/Invoke에 대한 문자열 매개 변수의 OutAttribute'
description: 코드 분석 규칙 CA1417 사용으로 발생하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/29/2020
ms.openlocfilehash: 3316d07108ec7f9da985494413336cba6d560dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759588"
---
# <a name="warning-ca1417-outattribute-on-string-parameter-for-pinvoke"></a>경고 CA1417: P/Invoke에 대한 문자열 매개 변수의 OutAttribute

.NET 코드 분석기 규칙 [CA1417](/visualstudio/code-quality/ca1417)은 .NET 5.0부터 기본적으로 사용됩니다. <xref:System.String> 매개 변수가 값으로 전달되고 <xref:System.Runtime.InteropServices.OutAttribute>로 표시된 [P/Invoke(플랫폼 호출)](../../../../standard/native-interop/pinvoke.md) 메서드 정의에 대해 빌드 경고를 생성합니다.

## <a name="change-description"></a>변경 내용 설명

.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다. [CA1417](/visualstudio/code-quality/ca1417)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다. 해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.

규칙 CA1417은 <xref:System.String> 매개 변수가 <xref:System.Runtime.InteropServices.OutAttribute> 특성으로 표시되고 값으로 전달된 [P/Invoke](../../../../standard/native-interop/pinvoke.md) 메서드 정의를 플래그로 지정합니다. 예를 들어:

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

.NET 런타임은 특정 프로그램에서 고유한 각 리터럴 문자열에 대한 단일 참조를 포함하는 인턴 풀이라는 테이블을 유지 관리합니다. <xref:System.Runtime.InteropServices.OutAttribute>로 표시된 인터닝된 문자열이 P/Invoke 메서드에 숫자로 전달되는 경우 런타임은 불안정해질 수 있습니다. 문자열 인터닝에 대한 자세한 내용은 <xref:System.String.Intern(System.String)?displayProperty=nameWithType>에 대한 항목을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

- 수정된 문자열 데이터를 호출자로 다시 마샬링해야 하는 경우에는 대신 참조로 문자열을 전달해야 합니다.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- 수정된 문자열 데이터를 다시 호출자로 마샬링할 필요가 없는 경우에는 <xref:System.Runtime.InteropServices.OutAttribute>를 제거하면 됩니다.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  자세한 내용은 [CA1417](/visualstudio/code-quality/ca1417)을 참조하세요.

- 코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다. 자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.

## <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
