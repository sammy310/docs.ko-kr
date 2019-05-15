---
title: 액세스 제어
description: 형식, 메서드 및 함수 등 프로그래밍 요소에 대 한 액세스를 제어 하는 방법을 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: a284d2fa4f98e444279276f58b70a15560537ca4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645604"
---
# <a name="access-control"></a>액세스 제어

*액세스 제어* 선언 형식, 메서드 및 함수 같은 특정 프로그램 요소를 사용할 수 있는 클라이언트를 가리킵니다.

## <a name="basics-of-access-control"></a>Access Control의 기본 사항

F#, 액세스 제어 지정자 `public`, `internal`, 및 `private` 모듈, 형식, 메서드, 값 정의 함수, 속성 및 명시적 필드에 적용할 수 있습니다.

- `public` 엔터티의 모든 호출자가 액세스할 수 있는지를 나타냅니다.

- `internal` 엔터티는 동일한 어셈블리 에서만에서 액세스할 수 있는지를 나타냅니다.

- `private` 엔터티 바깥쪽 형식이 나 모듈 에서만 액세스할 수 있는지를 나타냅니다.

> [!NOTE]
> 액세스 지정자 `protected` 에서 사용 되지 않습니다 F#이지만 지 원하는 언어로 작성 된 형식을 사용 하는 경우 적합 `protected` 액세스 합니다. 따라서 보호 된 메서드를 재정의 하는 경우 메서드 계속 클래스 및 해당 하위 항목 내 에서만 액세스할 수 있습니다.

지정자는 때를 제외 하 고 엔터티 이름 앞에 옵니다 일반적으로 `mutable` 또는 `inline` 지정자만 사용 하는 액세스 제어 지정자 뒤에 표시 합니다.

응용 프로그램이 사용 되는 액세스 지정 자가 없는 경우 기본값은 `public`를 제외 하 고 `let` 항상는 바인딩 형식에서 `private` 형식입니다.

서명에서 F# 에 대 한 액세스를 제어 하기 위한 다른 메커니즘을 제공 F# 요소를 프로그래밍 합니다. 서명은 액세스 제어에 대 한 필요 하지 않습니다. 자세한 내용은 [시그니처](signatures.md)를 참조하세요.

## <a name="rules-for-access-control"></a>Access Control에 대 한 규칙

액세스 제어는 다음 규칙이 적용 됩니다.

- 상속 선언 (즉, 사용 `inherit` 클래스에 대 한 기본 클래스를 지정 하), (즉를 지정 하는 클래스 인터페이스를 구현 하는) 선언, 인터페이스 및 추상 멤버는 항상 바깥쪽 형식으로 동일한 수준의 액세스 권한이 있습니다. 따라서 이러한 구문에 대해 액세스 제어 지정자를 사용할 수 없습니다.

- 구별된 된 공용 구조체의 개별 사례에 대 한 내게 필요한 옵션 자체 구별 된 공용 구조체의 액세스 가능성에 의해 결정 됩니다. 즉, 공용 구조체 케이스는 공용 구조체 자체 보다 액세스 하기 더 어렵습니다.

- 내게 필요한 옵션 없습니다 레코드 형식의 각 필드에 대 한 레코드 자체의 액세스 가능성에 의해 결정 됩니다. 즉, 특정 레코드 레이블은입니다는 레코드 자체 보다 액세스 하기 더 어렵습니다.

## <a name="example"></a>예제

다음 코드를 액세스 제어 지정자의 사용을 보여 줍니다. 프로젝트에서 두 개의 파일이 `Module1.fs` 고 `Module2.fs`입니다. 각 파일은 암시적으로 모듈. 따라서 두 모듈은 `Module1` 고 `Module2`입니다. 개인 유형 및 내부 형식에 정의 된 `Module1`합니다. 전용 형식에서 액세스할 수 없습니다 `Module2`, 내부 형식 수입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]

다음 코드에서 만든 형식의 액세스 가능성을 테스트 `Module1.fs`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [서명](signatures.md)
