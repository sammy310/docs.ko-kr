---
description: '자세히 알아보기: 형식 승격 (Visual Basic)'
title: 형식 승격
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: fd8a30fb7e442d82222ae55daabf70bd8e532138
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434721"
---
# <a name="type-promotion-visual-basic"></a>형식 승격(Visual Basic)

모듈에서 프로그래밍 요소를 선언 하는 경우 해당 범위를 모듈이 포함 된 네임 스페이스로 승격 Visual Basic. 이를 *유형 승격* 이라고 합니다.  
  
 다음 예제에서는 모듈의 기본 정의와 해당 모듈의 두 멤버를 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 에서 `projModule` 모듈 수준에 선언 된 프로그래밍 요소는로 승격 됩니다 `projNamespace` . 앞의 예제에서 `basicEnum` 및는 `innerClass` 승격 되지만 `numberSub` 모듈 수준에서 선언 되지 않았으므로는 그렇지 않습니다.  
  
## <a name="effect-of-type-promotion"></a>유형 승격의 효과  

 형식 승격의 효과는 정규화 문자열에 모듈 이름을 포함할 필요가 없다는 것입니다. 다음 예제에서는 앞의 예제에서 프로시저에 대 한 두 호출을 수행 합니다.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 앞의 예제에서 첫 번째 호출은 전체 한정 문자열을 사용 합니다. 그러나 형식 승격으로 인해이 작업이 필요 하지 않습니다. 또한 두 번째 호출은 한정 문자열에를 포함 하지 않고 모듈의 멤버에 액세스 합니다 `projModule` .  
  
## <a name="defeat-of-type-promotion"></a>유형 승격의 물리  

 네임 스페이스에 모듈 멤버와 이름이 같은 멤버가 이미 있는 경우 해당 모듈 멤버에 대해 형식 승격이 발생 하지 않습니다. 다음 예제에서는 동일한 네임 스페이스 내에서 열거형 및 모듈의 기본 정의를 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 앞의 예제에서 `abc` `thisNameSpace` 네임 스페이스 수준에 동일한 이름을 가진 열거가 이미 있기 때문에 클래스를로 승격할 수 Visual Basic. 에 액세스 하려면 `abcSub` 전체 한정 문자열을 사용 해야 합니다 `thisNamespace.thisModule.abc.abcSub` . 그러나 클래스 `xyz` 는 여전히 승격 되며, `xyzSub` 더 짧은 정규화 문자열로 액세스할 수 있습니다 `thisNamespace.xyz.xyzSub` .  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>부분 형식에 대 한 형식 승격의 물리  

 모듈 내의 클래스 또는 구조체에서 [Partial](../../../language-reference/modifiers/partial.md) 키워드를 사용 하는 경우 네임 스페이스에 이름이 같은 멤버가 포함 되어 있는지 여부에 관계 없이 해당 클래스 또는 구조체에 대해 형식 승격이 자동으로 무효화 됩니다. 모듈의 다른 요소는 형식 승격에 대 한 자격이 있습니다.  
  
 **미치는.** 부분 정의의 형식 승격을 물리 하면 예기치 않은 결과 및 컴파일러 오류가 발생할 수 있습니다. 다음 예제에서는 클래스의 기본 부분 정의를 보여 줍니다. 그 중 하나는 모듈 내에 있습니다.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 앞의 예제에서 개발자는 컴파일러에서의 두 부분 정의를 병합 하는 것을 예측할 수 있습니다 `sampleClass` . 그러나 컴파일러는 내의 부분 정의에 대 한 승격을 고려 하지 않습니다 `sampleModule` . 결과적으로 명명 `sampleClass` 되었지만 서로 다른 정규화 경로를 사용 하 여 두 개의 개별 및 고유 클래스를 컴파일하려고 시도 합니다.  
  
 컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.  
  
## <a name="recommendations"></a>권장 사항  

 다음 권장 사항은 바람직한 프로그래밍 습관을 나타냅니다.  
  
- **고유 이름.** 프로그래밍 요소의 명명에 대 한 모든 권한을 보유 한 경우 항상 고유한 이름을 사용 하는 것이 좋습니다. 동일한 이름에는 추가 한정자가 필요 하며 코드를 읽기 어렵게 만들 수 있습니다. 또한 미묘한 오류 및 예기치 않은 결과가 발생할 수 있습니다.  
  
- **모든 자격.** 같은 네임 스페이스에서 모듈 및 기타 요소를 사용 하는 경우 가장 안전한 방법은 항상 모든 프로그래밍 요소에 대 한 전체 한정자를 사용 하는 것입니다. 모듈 멤버에 대해 형식 승격을 사용할 수 없고 해당 멤버를 완전히 정규화 하지 않은 경우 실수로 다른 프로그래밍 요소에 액세스할 수 있습니다.  
  
## <a name="see-also"></a>추가 정보

- [Module 문](../../../language-reference/statements/module-statement.md)
- [Namespace 문](../../../language-reference/statements/namespace-statement.md)
- [부분](../../../language-reference/modifiers/partial.md)
- [Visual Basic의 범위](scope.md)
- [방법: 변수의 범위 제어](how-to-control-the-scope-of-a-variable.md)
- [References to Declared Elements](references-to-declared-elements.md)
