---
title: '가져오기 선언: Open 키워드'
description: 에 대해 알아봅니다 F# 선언 및 모듈 또는 네임 스페이스 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 지정 하는 방법을 가져옵니다.
ms.date: 04/04/2019
ms.openlocfilehash: ad64190c3243c57a185f3b864270fca80590f079
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59055003"
---
# <a name="import-declarations-the-open-keyword"></a>가져오기 선언: `open` 키워드

> [!NOTE]
> 이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

*가져오기 선언* 모듈이 나 네임 스페이스 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 지정 합니다.

## <a name="syntax"></a>구문

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>설명

정규화 된 네임 스페이스 또는 모듈 경로 사용 하 여 코드를 참조 될 때마다 쓰기, 읽기 및 유지 관리 하기 어려운 코드를 만들 수 있습니다. 대신 사용할 수는 `open` 키워드에 대 한 자주 모듈 및 네임 스페이스를 사용 하 여 해당 모듈 또는 네임 스페이스의 멤버를 참조할 때 정규화 된 이름 대신 이름의 약식을 사용할 수 있습니다. 이 키워드는 비슷합니다는 `using` 키워드 C#를 `using namespace` 시각적 개체의 C++, 및 `Imports` Visual Basic의 합니다.

같은 프로젝트 또는 참조 된 프로젝트나 어셈블리에 모듈을 제공 하는 네임 스페이스 여야 합니다. 프로젝트에 대 한 참조를 추가 또는 사용할 수 없는 경우는 `-reference` 명령`-`명령줄 옵션 (또는 해당 약어 `-r`). 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.

가져오기 선언 바깥쪽 네임 스페이스, 모듈 또는 파일의 끝까지 선언 뒤에 오는 코드를 사용할 수 있는 이름을 만듭니다.

여러 가져오기 선언에 사용 하는 경우 별도 줄에 나타납니다.

다음 코드의 사용을 보여 줍니다.는 `open` 키워드 코드를 단순화 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

F# 컴파일러를 내보내지는지 않습니다 오류 또는 경고를 둘 이상 열려 모듈 또는 네임 스페이스 이름이 발생 하면 모호성이 발생 합니다. 모호성이 발생 하면 F# 기본 설정 보다 최근에 연 모듈 또는 네임 스페이스를 제공 합니다. 예를 들어, 다음 코드에서에서 `empty` 의미 `Seq.empty`경우에 `empty` 둘 다에 `List` 고 `Seq` 모듈.

```fsharp
open List
open Seq
printfn "%A" empty
```

따라서 주의 같은 모듈 또는 네임 스페이스를 열 때 `List` 또는 `Seq` 이름이 같더라도; 대신 정규화 된 이름을 사용 하는 것이 좋습니다는 멤버를 포함 하는 합니다. 코드는 가져오기 선언의 순서에 종속 된 모든 상황을 피해 야 합니다.

## <a name="namespaces-that-are-open-by-default"></a>기본적으로 열려 있는 네임 스페이스

일부 네임 스페이스에서 자주 사용 됩니다 F# 열리는 암시적 선언의 명시적으로 가져올 필요 없이 코드입니다. 다음 표에서 기본적으로 열려 있는 네임 스페이스를 보여 줍니다.

|네임스페이스|설명|
|---------|-----------|
|`Microsoft.FSharp.Core`|기본 포함 F# 와 같은 기본 제공 형식에 대 한 정의 입력 `int` 하 고 `float`합니다.|
|`Microsoft.FSharp.Core.Operators`|같은 기본 산술 연산이 포함 되어 있습니다 `+` 고 `*`입니다.|
|`Microsoft.FSharp.Collections`|변경 불가능 컬렉션 클래스를 같은 포함 `List` 고 `Array`입니다.|
|`Microsoft.FSharp.Control`|지연 계산 등 비동기 워크플로 제어 구문에 대 한 형식을 포함합니다.|
|`Microsoft.FSharp.Text`|서식이 지정 된 io와 같은 함수를 포함 합니다 `printf` 함수입니다.|

## <a name="autoopen-attribute"></a>AutoOpen 특성

적용할 수는 `AutoOpen` 어셈블리를 참조할 때 네임 스페이스 또는 모듈을 자동으로 열도록 하려면 특성을 어셈블리에 있습니다. 적용할 수도 있습니다는 `AutoOpen` 부모 모듈 또는 네임 스페이스를 열 때 해당 모듈을 자동으로 열려면 모듈에 특성입니다. 자세한 내용은 [Core.AutoOpenAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)합니다.

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess 특성

일부 모듈, 레코드 또는 공용 구조체 형식을 지정할 수는 `RequireQualifiedAccess` 특성입니다. 이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조할 때 가져오기 선언을 포함 여부에 관계 없이 정규화 된 이름을 사용 해야 합니다. 에 전략적으로이 특성을 사용 하면 일반적으로 정의 하는 형식 이름을 사용한 경우 이름 충돌을 방지 하 고 있으므로 복원 력을 코드 라이브러리의 변경 내용에 도움이 합니다. 자세한 내용은 [Core.RequireQualifiedAccessAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [네임스페이스](namespaces.md)
- [모듈](modules.md)
