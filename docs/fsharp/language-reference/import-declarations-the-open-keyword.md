---
title: '선언 가져오기: open 키워드'
description: F# 가져오기 선언에 대해 알아보고 정규화된 이름을 사용하지 않고 참조할 수 있는 요소가 있는 모듈 또는 네임스페이스를 지정하는 방법에 대해 알아봅니다.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021537"
---
# <a name="import-declarations-the-open-keyword"></a>가져오기 선언: `open` 키워드

> [!NOTE]
> 이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

*가져오기 선언은* 정규화된 이름을 사용하지 않고 참조할 수 있는 요소를 지정하는 모듈 또는 네임스페이스를 지정합니다.

## <a name="syntax"></a>구문

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>설명

매번 정규화된 네임스페이스 또는 모듈 경로를 사용하여 코드를 참조하면 작성, 읽기 및 유지 관리하기 어려운 코드를 만들 수 있습니다. 대신 자주 사용하는 `open` 모듈 및 네임스페이스에 키워드를 사용하여 해당 모듈 또는 네임스페이스의 멤버를 참조할 때 정규화된 이름 대신 짧은 형식의 이름을 사용할 수 있습니다. 이 키워드는 C#, `using` `using namespace` Visual C++및 Visual Basic의 `Imports` 키워드와 유사합니다.

제공된 모듈 또는 네임스페이스는 동일한 프로젝트 또는 참조된 프로젝트 또는 어셈블리에 있어야 합니다. 그렇지 않은 경우 프로젝트에 대한 참조를 추가하거나 `-reference` 명령줄 옵션(또는 `-r`약어)을 사용할 수 있습니다. 자세한 내용은 [컴파일러 옵션을](compiler-options.md)참조하십시오.

import 선언은 둘러싸는 네임스페이스, 모듈 또는 파일의 끝까지 선언 다음에 오는 코드에서 이름을 사용할 수 있게 합니다.

여러 가져오기 선언을 사용하는 경우 별도의 줄에 표시되어야 합니다.

다음 코드는 코드를 단순화하기 위해 키워드를 `open` 사용하는 방법을 보여 주십니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

F# 컴파일러는 둘 이상의 열린 모듈 또는 네임스페이스에서 동일한 이름이 발생할 때 모호성이 발생할 때 오류 또는 경고를 내보내지 않습니다. 모호성이 발생하면 F#은 최근에 열린 모듈 또는 네임스페이스에 우선권을 부여합니다. 예를 들어 다음 코드에서 `empty` `Seq.empty`는 `empty` `List` 와 `Seq` 모듈 모두에 있더라도 을 의미합니다.

```fsharp
open List
open Seq
printfn "%A" empty
```

따라서 이름이 동일한 멤버를 포함하거나 `List` `Seq` 모듈이나 네임스페이스를 열 때는 주의해야 합니다. 대신 정규화된 이름을 사용하는 것이 좋습니다. 코드가 가져오기 선언의 순서에 종속되는 상황은 피해야 합니다.

## <a name="namespaces-that-are-open-by-default"></a>기본적으로 열려 있는 네임스페이스

일부 네임스페이스는 F# 코드에서 자주 사용되므로 명시적 가져오기 선언없이 암시적으로 열립니다. 다음 표에는 기본적으로 열려 있는 네임스페이스가 표시됩니다.

|네임스페이스|설명|
|---------|-----------|
|`Microsoft.FSharp.Core`|`int` 와 `float`같은 기본 제공 형식에 대한 기본 F# 형식 정의가 포함되어 있습니다.|
|`Microsoft.FSharp.Core.Operators`|`+` 및 와 `*`같은 기본 산술 연산을 포함합니다.|
|`Microsoft.FSharp.Collections`|`List` 와 같은 변경할 수 없는 `Array`컬렉션 클래스가 포함되어 있습니다.|
|`Microsoft.FSharp.Control`|지연 평가 및 비동기 워크플로와 같은 제어 구문에 대한 형식을 포함합니다.|
|`Microsoft.FSharp.Text`|함수와 같이 서식이 지정된 IO에 대한 함수를 `printf` 포함합니다.|

## <a name="autoopen-attribute"></a>자동 열기 특성

어셈블리를 `AutoOpen` 참조할 때 네임스페이스 또는 모듈을 자동으로 열려면 어셈블리에 특성을 적용할 수 있습니다. 상위 모듈 또는 `AutoOpen` 네임스페이스가 열릴 때 모듈에 특성을 적용하여 해당 모듈을 자동으로 열 수도 있습니다. 자세한 내용은 [Core.AutoOpenAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)를 참조하십시오.

## <a name="requirequalifiedaccess-attribute"></a>요구정규어특성액세스 특성

일부 모듈, 레코드 또는 공용 구조체 형식은 특성을 지정할 `RequireQualifiedAccess` 수 있습니다. 이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조할 때 가져오기 선언을 포함하는지 여부에 관계없이 정규화된 이름을 사용해야 합니다. 일반적으로 사용되는 이름을 정의하는 형식에서 이 특성을 전략적으로 사용하는 경우 이름 충돌을 방지하고 라이브러리의 변경 사항에 대한 코드 복원력을 높일 수 있습니다. 자세한 내용은 [Core.RequireQualifiedAccess속성 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)를 참조하십시오.

## <a name="see-also"></a>참조

- [F # 언어 참조](index.md)
- [네임스페이스](namespaces.md)
- [모듈](modules.md)
