---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614686"
---
### <a name="changes-in-path-normalization"></a>경로 정규화의 변경

#### <a name="details"></a>설명

.NET Framework 4.6.2를 대상으로 하는 앱부터 런타임이 경로를 정규화하는 방식이 변경되었습니다. 경로 정규화 중에는 대상 운영 체제의 올바른 경로에 맞게 경로 또는 파일을 식별하는 문자열이 수정됩니다. 정규화에는 일반적으로 다음이 수행됩니다.

- 구성 요소 및 디렉터리 구분 기호 정규화
- 상대 경로에 현재 디렉터리 적용
- 경로의 상대 디렉터리(.) 또는 부모 디렉터리(..) 평가
- 지정된 문자 자르기
.NET Framework 4.6.2를 대상으로 하는 앱부터는 경로 정규화의 다음 변경이 기본적으로 사용됩니다.
  - 런타임은 운영 체제의 [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) 함수를 지연시켜 경로를 정규화합니다.
- 정규화 중에 더 이상 디렉터리 세그먼트의 끝(예: 디렉터리 이름 끝의 공백)이 잘리지 않습니다.
- 완전 신뢰의 디바이스 경로 구문(`\\.\` 포함) 지원 및 mscorlib.dll `\\?\`에서 파일 I/O API 지원
- 런타임에서 디바이스 구문 경로가 유효한지 확인하지 않습니다.
- 대체 데이터 스트림에 액세스하기 위해 디바이스 구문을 사용할 수 있습니다.
이 변경 내용을 통해 메서드에서 이전에 액세스할 수 없는 경로에 액세스할 수 있게 되며 성능이 향상됩니다. .NET Framework 4.6.1 이하 버전을 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱은 이러한 변경에 의해 영향을 받지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.6.2 이상을 대상으로 하는 앱은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음을 추가하여 이 변경을 옵트아웃하고 레거시 정규화를 사용할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

.NET Framework 4.6.1 이하를 대상으로 하지만 .NET Framework 4.6.2 이상에서 실행되는 앱은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 경로 정규화에 변경을 사용할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |
