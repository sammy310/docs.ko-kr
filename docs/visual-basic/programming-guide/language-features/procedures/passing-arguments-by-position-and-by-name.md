---
title: 위치 및 이름으로 인수 전달
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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401438"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>위치 및 이름으로 인수 전달(Visual Basic)

`Sub` 또는 `Function` 프로시저를 호출할 때 인수가 프로시저의 정의에 표시되는 순서대로 *위치별로* 전달하거나 위치에 관계없이 *이름으로 전달할*수 있습니다.

이름으로 인수를 전달할 때 인수의 선언된 이름 뒤에 콜론과 같음`:=`() 다음에 인수 값을 지정합니다. 명명된 인수를 원하는 순서로 제공할 수 있습니다.

예를 들어 다음 `Sub` 절차에는 세 가지 인수가 필요합니다.

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

이 프로시저를 호출할 때 위치, 이름 또는 둘 다의 혼합을 사용하여 인수를 제공할 수 있습니다.

## <a name="passing-arguments-by-position"></a>위치별 인수 전달

다음 예제와 `Display` 같이 해당 인수가 위치로 전달되고 쉼표로 구분된 메서드를 호출할 수 있습니다.

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

위치 인수 목록에서 선택적 인수를 생략하는 경우 쉼표로 해당 위치를 유지해야 합니다. 다음 예제는 `Display` 인수 없이 `age` 메서드를 호출합니다.

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>이름으로 인수 전달

또는 다음 예제와 `Display` 같이 이름으로 전달된 인수를 쉼표로 구분하여 호출할 수 있습니다.

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

이러한 방식으로 인수를 이름으로 전달하는 것은 두 개 이상의 선택적 인수가 있는 프로시저를 호출할 때 특히 유용합니다. 이름으로 인수를 제공하는 경우 누락된 위치 인수를 나타내기 위해 연속 쉼표를 사용할 필요가 없습니다. 또한 인수를 이름으로 전달하면 전달하는 인수와 생략중인 인수를 쉽게 추적할 수 있습니다.

## <a name="mixing-arguments-by-position-and-by-name"></a>위치 및 이름으로 인수 혼합

다음 예제와 같이 단일 프로시저 호출에서 위치 및 이름별 인수를 모두 제공할 수 있습니다.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

앞의 예제에서는 이름으로 `age` `birth` 전달되므로 생략된 인수의 위치를 유지하기 위해 추가 쉼표가 필요하지 않습니다.

15.5 이전의 Visual Basic 버전에서는 위치와 이름을 혼합하여 인수를 제공할 때 위치 인수가 모두 먼저 제공되어야 합니다. 이름으로 인수를 제공하면 나머지 인수는 모두 이름으로 전달되어야 합니다.  예를 들어 메서드에 대한 `Display` 다음 호출에는 컴파일러 오류 [BC30241: 명명된 인수가 예상됩니다.](../../../misc/bc30241.md)

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

Visual Basic 15.5부터 시작하여 끝 위치 인수가 올바른 위치에 있는 경우 위치 인수는 명명된 인수를 따를 수 있습니다. Visual Basic 15.5에서 컴파일된 경우 메서드에 대한 이전 호출이 `Display` 성공적으로 컴파일되고 더 이상 컴파일러 오류 [BC30241을](../../../misc/bc30241.md)생성하지 않습니다.

명명된 인수와 위치 인수를 순서대로 혼합하고 일치시킬 수 있는 이 기능은 명명된 인수를 사용하여 코드를 더 읽기 쉽게 만들려는 경우에 특히 유용합니다. 예를 들어 다음 `Person` 클래스 생성자는 형식의 `Person`두 인수를 필요로 `Nothing`하며 둘 다 .

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

혼합 명명 된 위치 인수를 사용 하 여 `father` 코드의 의도를 명확 `mother` 하 게 `Nothing`하는 데 도움이 때 는 인수의 값 :

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

명명 된 인수와 위치 인수를 따라, Visual Basic 프로젝트 (.vbproj)\*파일에 다음 요소를 추가 해야 합니다.

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

자세한 내용은 [Visual Basic 언어 버전 설정을](../../../language-reference/configure-language-version.md)참조하십시오.

## <a name="restrictions-on-supplying-arguments-by-name"></a>이름으로 인수 제공에 대한 제한

필요한 인수를 입력하지 않으려면 이름으로 인수를 전달할 수 없습니다. 선택적 인수만 생략할 수 있습니다.

매개 변수 배열을 이름으로 전달할 수 없습니다. 프로시저를 호출할 때 매개 변수 배열에 대해 무기한 으로 구분된 인수를 제공하고 컴파일러가 두 개 이상의 인수를 단일 이름과 연결할 수 없기 때문입니다.

## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [선택적 매개 변수](./optional-parameters.md)
- [매개 변수 배열](./parameter-arrays.md)
- [선택적](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
