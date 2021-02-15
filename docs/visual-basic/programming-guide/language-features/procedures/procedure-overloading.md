---
description: '자세한 정보: 프로시저 오버 로드 (Visual Basic)'
title: 프로시저 오버로딩
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 27e79e12153bc7ac6a9e3b3b5997a50c1c354195
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466642"
---
# <a name="procedure-overloading-visual-basic"></a>프로시저 오버로딩(Visual Basic)

프로시저를 *오버 로드* 하는 것은 동일한 이름을 사용 하지만 매개 변수 목록을 사용 하 여 여러 버전으로 정의 하는 것을 의미 합니다. 오버 로드의 목적은 프로시저를 이름으로 구분 하지 않고도 긴밀 하 게 관련 된 여러 버전을 정의 하는 것입니다. 매개 변수 목록을 변경 하 여이 작업을 수행 합니다.

## <a name="overloading-rules"></a>오버 로드 규칙

프로시저를 오버 로드 하는 경우 다음 규칙이 적용 됩니다.

- **동일한 이름** 입니다. 오버 로드 된 각 버전은 동일한 프로시저 이름을 사용 해야 합니다.

- **서명이 다릅니다**. 오버 로드 된 각 버전은 다음 중 하나 이상의 오버 로드 된 버전과 달라 야 합니다.

  - 매개 변수 수

  - 매개 변수의 순서

  - 매개 변수의 데이터 형식

  - 제네릭 프로시저에 대 한 형식 매개 변수 수

  - 반환 형식 (변환 연산자의 경우에만)

  프로시저 이름과 함께 위의 항목을 통칭 하 여 프로시저의 *시그니처* 라고 합니다. 오버 로드 된 프로시저를 호출 하면 컴파일러는 서명을 사용 하 여 호출이 정의와 정확히 일치 하는지 확인 합니다.

- **항목은 시그니처의 일부가 아닙니다**. 시그니처를 변경 하지 않고 프로시저를 오버 로드할 수 없습니다. 특히 다음 항목 중 하나 이상을 변경 하 여 프로시저를 오버 로드할 수 없습니다.

  - 프로시저 한정자 키워드 (예: `Public` , `Shared` 및) `Static`

  - 매개 변수 또는 형식 매개 변수 이름

  - 형식 매개 변수 제약 조건 (제네릭 프로시저의 경우)

  - 매개 변수 한정자 키워드 (예: `ByRef` 및) `Optional`

  - 값을 반환 하는지 여부

  - 반환 값의 데이터 형식 (변환 연산자 제외)

  위의 목록에 있는 항목은 시그니처의 일부가 아닙니다. 오버 로드 된 버전을 구분 하는 데 사용할 수는 없지만 해당 시그니처로 적절히 구분 되는 오버 로드 된 버전 간에는 이러한 버전을 변경할 수 있습니다.

- **런타임에 바인딩된 인수** 입니다. 런타임에 바인딩된 개체 변수를 오버 로드 된 버전에 전달 하려는 경우에는 적절 한 매개 변수를로 선언 해야 합니다 <xref:System.Object> .

## <a name="multiple-versions-of-a-procedure"></a>프로시저의 여러 버전

`Sub`고객의 잔액에 대해 트랜잭션을 게시 하는 프로시저를 작성 하는 경우 이름 또는 계정 번호를 기준으로 고객을 참조할 수 있습니다. 이를 수용 하기 위해 `Sub` 다음 예제와 같이 두 가지 다른 프로시저를 정의할 수 있습니다.

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a>오버 로드 된 버전

또 다른 방법은 단일 프로시저 이름을 오버 로드 하는 것입니다. 다음과 같이 [Overloads](../../../language-reference/modifiers/overloads.md) 키워드를 사용 하 여 각 매개 변수 목록에 대 한 프로시저의 버전을 정의할 수 있습니다.

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a>추가 오버 로드

또는에서 트랜잭션 양을 허용 하려는 경우 `Decimal` `Single` `post` 이 변형에 대해 허용할 추가 오버 로드를 수행할 수 있습니다. 앞의 예제에서 각 오버 로드에 대해이를 수행한 경우 네 가지 `Sub` 절차를 모두 포함 하 고 네 개의 다른 서명을 사용 합니다.

## <a name="advantages-of-overloading"></a>오버 로드의 이점

프로시저 오버 로드의 이점은 호출의 유연성을 제공 합니다. `post`앞의 예제에서 선언한 프로시저를 사용 하려면 호출 하는 코드에서 또는로 고객 id를 가져온 `String` `Integer` 다음 두 경우 모두 동일한 프로시저를 호출할 수 있습니다. 다음 예제에서는 이에 대해 설명합니다.

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a>추가 정보

- [절차](./index.md)
- [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)
- [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)
- [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [프로시저 오버로드에서 고려해야 할 사항](./considerations-in-overloading-procedures.md)
- [Overload Resolution](./overload-resolution.md)
- [오버로드](../../../language-reference/modifiers/overloads.md)
- [Visual Basic의 제네릭 형식](../data-types/generic-types.md)
