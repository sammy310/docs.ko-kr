---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366858"
---
### <a name="exclude-specific-symbols"></a>특정 기호 제외

분석에서 형식 및 메서드와 같은 특정 기호를 제외할 수 있습니다. 예를 들어 이름이 인 형식 내의 코드에서 규칙이 실행 되지 않도록 지정 하려면 `MyType` 프로젝트의 *editorconfig* 파일에 다음 키-값 쌍을 추가 합니다.

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

옵션 값의 허용 되는 기호 이름 형식 (로 구분 `|` ):

- 기호 이름만 (포함 하는 형식 또는 네임 스페이스에 관계 없이 이름이 인 모든 기호 포함).
- 기호의 [문서 ID 형식](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)에 대 한 정규화 된 이름입니다. 각 기호 이름에는 `M:` 메서드, `T:` 형식 및 네임 스페이스에 대 한 기호 종류 접두사가 필요 합니다 `N:` .
- `.ctor` 생성자의 경우이 고, `.cctor` 정적 생성자의 경우입니다.

예제:

| 옵션 값 | 요약 |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | 이라는 모든 기호와 일치 `MyType` 합니다. |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | 또는 중 하나에 해당 하는 모든 기호 `MyType1` 를 찾습니다 `MyType2` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | 지정 된 정규화 된 시그니처와 특정 메서드를 일치 시킵니다 `MyMethod` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | 특정 메서드와 `MyMethod1` 해당 하 `MyMethod2` 는 정규화 된 시그니처를 일치 시킵니다. |
