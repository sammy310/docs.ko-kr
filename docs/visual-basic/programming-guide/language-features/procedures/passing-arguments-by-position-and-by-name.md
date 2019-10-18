---
title: 위치 및 이름으로 인수 전달(Visual Basic)
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: 2fa07a4ecf31b9dc0fee91593e793f3b00c5a83b
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524438"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>위치 및 이름으로 인수 전달(Visual Basic)

@No__t_0 또는 `Function` 프로시저를 호출 하는 경우 프로시저 정의에 표시 되는 순서 대로 *위치를 기준으로* 인수를 전달 하거나 위치에 관계 없이 *이름을*사용 하 여 인수를 전달할 수 있습니다.

이름으로 인수를 전달 하는 경우 인수의 선언 된 이름, 콜론 및 등호 (`:=`), 인수 값을 차례로 지정 합니다. 순서에 관계 없이 명명 된 인수를 제공할 수 있습니다.

예를 들어 다음 `Sub` 프로시저는 세 개의 인수를 사용 합니다.

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

이 프로시저를 호출 하는 경우 인수를 이름으로 지정 하거나 둘의 조합을 사용 하 여 지정할 수 있습니다.

## <a name="passing-arguments-by-position"></a>위치로 인수 전달

다음 예제와 같이 위치에 의해 전달 되 고 쉼표로 구분 된 인수를 사용 하 여 `Display` 메서드를 호출할 수 있습니다.

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

위치 인수 목록에서 선택적 인수를 생략 하는 경우에는 쉼표를 사용 하 여 위치를 유지 해야 합니다. 다음 예제에서는 `age` 인수를 사용 하지 않고 `Display` 메서드를 호출 합니다.

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>이름으로 인수 전달

또는 다음 예제와 같이 쉼표로 구분 된 이름으로 전달 된 인수를 사용 하 여 `Display`를 호출할 수 있습니다.

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

이러한 방법으로 인수를 전달 하는 것은 둘 이상의 선택적 인수가 있는 프로시저를 호출할 때 특히 유용 합니다. 이름으로 인수를 제공 하는 경우 연속 쉼표를 사용 하 여 누락 된 위치 인수를 나타낼 필요가 없습니다. 인수를 이름으로 전달 하면 전달 하는 인수와 생략 한 인수를 쉽게 추적할 수 있습니다.

## <a name="mixing-arguments-by-position-and-by-name"></a>위치 및 이름으로 인수 혼합

다음 예제와 같이 단일 프로시저 호출에서 위치 및 이름으로 인수를 제공할 수 있습니다.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

앞의 예제에서는 `birth` 이름으로 전달 되기 때문에 생략 된 `age` 인수 대신 추가 쉼표가 필요 하지 않습니다.

15.5 이전의 Visual Basic 버전에서는 위치와 이름을 혼합 하 여 인수를 제공 하면 모두 위치 인수가 먼저와 야 합니다. 이름으로 인수를 제공한 후에는 모든 나머지 인수를 이름으로 전달 해야 합니다.  예를 들어 `Display` 메서드에 대 한 다음 호출에서는 컴파일러 오류 [BC30241: 명명 된 인수가 필요](../../../misc/bc30241.md)합니다.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

Visual Basic 15.5부터 끝 위치 인수가 올바른 위치에 있는 경우 위치 인수는 명명 된 인수 뒤에 올 수 있습니다. Visual Basic 15.5에서 컴파일된 경우 `Display` 메서드에 대 한 이전 호출이 성공적으로 컴파일되고 더 이상 컴파일러 오류 [BC30241](../../../misc/bc30241.md)를 생성 하지 않습니다.

명명 된 인수와 위치 인수를 순서 대로 혼합 하 고 일치 시키는이 기능은 명명 된 인수를 사용 하 여 코드를 보다 읽기 쉽게 만드는 경우에 특히 유용 합니다. 예를 들어 다음 `Person` 클래스 생성자에는 `Person` 형식의 인수가 두 개 필요 하며, 둘 다 `Nothing` 수 있습니다.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

명명 된 인수와 위치 인수를 함께 사용 하면 `father` 및 `mother` 인수의 값이 `Nothing` 때 코드의 의도를 명확 하 게 파악할 수 있습니다.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

명명 된 인수를 사용 하 여 위치 인수를 따르려면 Visual Basic 프로젝트 (\* .vbproj) 파일에 다음 요소를 추가 해야 합니다.

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

자세한 내용은 [Visual Basic 언어 버전 설정](../../../language-reference/configure-language-version.md)을 참조 하세요.

## <a name="restrictions-on-supplying-arguments-by-name"></a>이름으로 인수를 제공 하는 경우의 제한 사항

필요한 인수가 입력 되지 않도록 하려면 인수를 이름으로 전달할 수 없습니다. 선택적 인수만 생략할 수 있습니다.

매개 변수 배열을 이름으로 전달할 수 없습니다. 이는 프로시저를 호출할 때 매개 변수 배열에 대해 쉼표로 구분 된 인수를 무제한으로 제공 하 고, 컴파일러는 단일 이름에 둘 이상의 인수를 연결할 수 없기 때문입니다.

## <a name="see-also"></a>참조

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [선택적 매개 변수](./optional-parameters.md)
- [매개 변수 배열](./parameter-arrays.md)
- [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
