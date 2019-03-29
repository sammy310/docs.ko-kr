---
title: 옵션
description: 사용 하는 방법을 알아봅니다 F# 명명 된 값 또는 변수를 실제 값이 존재 하지 않을 경우 형식 옵션입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 6d32693bccc74c2cab642e4f626c9463092e8a39
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634104"
---
# <a name="options"></a>옵션

옵션 형식 F# 명명 된 값 또는 변수를 실제 값이 존재 하지 않을 때 사용 됩니다. 옵션은 기본 형식이 고 해당 형식의 값을 보유할 수 또는 값이 없을 수 있습니다.

## <a name="remarks"></a>설명

다음 코드에서는 옵션 형식을 생성 하는 함수를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

알 수 있듯이, 경우 입력 `a` 가 0 보다 크면 `Some(a)` 생성 됩니다.  그렇지 않으면 `None` 생성 됩니다.

값 `None` 옵션을 실제 값이 없는 경우에 사용 됩니다. 그렇지 않으면 식 `Some( ... )` 옵션 값을 제공 합니다. 값 `Some` 하 고 `None` 다음 함수와 패턴 일치에 유용 `exists`를 반환 하는 `true` 옵션 값이 있으면 및 `false` 그렇지 않은 경우.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>옵션을 사용 하 여

옵션은 검색 일치 하는 결과 반환 하지 않는 경우 사용 일반적으로 다음 코드 에서처럼.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

이전 코드에서 목록을 재귀적으로 검색된 합니다. 함수 `tryFindMatch` 조건자 함수 `pred` 검색할 목록 및 부울 값을 반환 합니다. 조건자를 만족 하는 요소가 없으면 멈추고 함수 값을 반환 식의 옵션으로 `Some(head)`입니다. 재귀에는 빈 목록에 일치 하는 경우 종료 됩니다. 값을 해당 시점 `head` 검색 되지 않은 및 `None` 반환 됩니다.

많은 F# 수도 반환 존재 하지 않을 수 있는 값에 대 한 컬렉션을 검색 하는 라이브러리 함수는 `option` 형식입니다. 규칙에 따라 이러한 기능으로 시작 합니다 `try` 접두사, 예를 들어 [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)합니다.

예를 들어 값을 생성 하려고 할 때 예외가 throw 될 수 있으면 값을 존재 하지 않을 때에 옵션 유용할 수 있습니다. 다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

합니다 `openFile` 이전 예제의 함수 형식이 `string -> File option` 반환 하기 때문에 `File` 파일을 성공적으로 열리는 경우 개체 및 `None` 예외가 발생 한 경우. 상황에 따라 전파 되도록 허용 하는 대신 예외를 catch 하는 적절 한 설계 선택 되지 않습니다 수 있습니다.

또한 것도 가능 전달할 `null` 또는 null 값을 `Some` 옵션의 경우. 이 방법은 일반적으로 사용 하지 않아야 루틴에는 일반적으로 F# .net에서 참조 형식의 특성으로 인해 가능한 비슷하나 프로그래밍 합니다.

## <a name="option-properties-and-methods"></a>옵션 속성 및 메서드

옵션 종류는 다음 속성 및 메서드를 지원합니다.

|속성 또는 메서드|형식|설명|
|------------------|----|-----------|
|[없음](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|이 있는 옵션 값을 만들 수 있게 하는 정적 속성은 `None` 값입니다.|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|반환 `true` 옵션에는 `None` 값입니다.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|반환 `true` 옵션을 하지 않은 값이 있으면 `None`합니다.|
|[일부](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|옵션을 만드는 정적 멤버인 되지 않는 값이 `None`합니다.|
|[값](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|기본 값을 반환 하거나 throw 된 `System.NullReferenceException` 값이 `None`합니다.|

## <a name="option-module"></a>Option 모듈

모듈이 [옵션](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), 옵션에 대 한 작업을 수행 하는 유용한 함수를 포함 하는 합니다. 일부 함수 속성의 기능을 반복 하지만 함수가 필요한 상황에서 유용 합니다. [Option.isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) 하 고 [Option.isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) 옵션 값을 보유 하는지 여부를 테스트 하는 모듈 함수가 모두 합니다. [Option.get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) 있을 경우 값을 가져옵니다. 값이 없는 경우 throw `System.ArgumentException`합니다.

합니다 [Option.bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) 함수 값 이면 값의 함수를 실행 합니다. 함수는 정확히 하나의 인수를 취해야 및 해당 매개 변수 형식은 옵션 형식 이어야 합니다. 함수의 반환 값은 다른 옵션 종류입니다.

또한 옵션 모듈에는 목록, 배열, 시퀀스 및 기타 컬렉션 형식에 사용할 수 있는 함수에 해당 하는 함수가 포함 됩니다. 이러한 함수를 포함 [ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191)를 [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428)를 [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99)합니다 [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb)하십시오 [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), 및 [ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876)합니다. 이러한 함수를 0 개 또는 한 요소의 모음 처럼 사용할 옵션을 사용 합니다. 자세한 내용 및 예제에서 컬렉션 함수 설명을 참조 하십시오 [나열](lists.md)합니다.

## <a name="converting-to-other-types"></a>다른 형식으로 변환

옵션 목록 또는 배열에 변환할 수 있습니다. 이러한 데이터 구조를 옵션으로 변환 하는 경우 결과 데이터 구조에 0 개 이상의 요소가 있습니다. 사용 옵션을 배열로 변환할 [ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64)합니다. 사용 옵션 목록을 변환할 [ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1)합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [F# 형식](fsharp-types.md)
