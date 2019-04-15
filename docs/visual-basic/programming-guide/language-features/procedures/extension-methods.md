---
title: 확장 메서드(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 9e005d0dc7da154fbaffbf7e02c55445a1213195
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296240"
---
# <a name="extension-methods-visual-basic"></a>확장 메서드(Visual Basic)
확장 메서드는 파생된 형식을 새로 만들지 않고 이미 정의 되어 있는 데이터 형식에 사용자 지정 기능을 추가 하는 개발자를 사용 합니다. 확장 메서드 수 있도록 기존 형식의 인스턴스 메서드인 것 처럼 호출할 수 있는 메서드를 작성 합니다.  
  
## <a name="remarks"></a>설명  
 확장 메서드이기 뿐일 수는 `Sub` 프로시저 또는 `Function` 프로시저입니다. 확장 속성, 필드 또는 이벤트를 정의할 수 없습니다. 모든 확장 메서드가 확장 특성으로 표시 되어야 합니다 `<Extension()>` 에서 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임 스페이스입니다.  
  
 확장 메서드 정의의 첫 번째 매개 변수는 메서드가 확장 하는 데이터 형식을 지정 합니다. 메서드를 실행 하는 경우 첫 번째 매개 변수 메서드를 호출 하는 데이터 형식의 인스턴스에 바인딩됩니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 정의 `Print` 확장을 <xref:System.String> 데이터 형식입니다. 메서드를 사용 하 여 `Console.WriteLine` 문자열로 표시 합니다. 매개 변수를 `Print` 메서드를 `aString`를 확장 하도록 설정 된 <xref:System.String> 클래스입니다.  
  
 [!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]  
  
 확장 특성을 사용 하 여 확장 메서드 정의가 표시 됩니다 `<Extension()>`합니다. 메서드가 정의 된 모듈을 표시 하는 것은 선택적 이지만 각 확장 메서드를 표시 합니다. <xref:System.Runtime.CompilerServices> 확장 특성에 액세스 하기 위해 가져올 수 있어야 합니다.  
  
 확장 메서드는 모듈 안에만 선언할 수 있습니다. 일반적으로 확장 메서드가 정의 되어 있는 모듈 호출 되는 것과 동일한 모듈이 아닙니다. 대신 확장 메서드를 포함 하는 모듈을 가져온 가져와야 범위로 가져와야 할 경우. 포함 된 모듈 뒤 `Print` 는 범위에 메서드를 호출할 수와 같은 인수를 사용 하는 일반 인스턴스 메서드인 것 처럼 `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]  
  
 다음 예에서 `PrintAndPunctuate`, 확장 이기도 <xref:System.String>,이 이번에 두 개의 매개 변수를 사용 하 여 정의 합니다. 첫 번째 매개 변수를 `aString`를 설정 하는 확장 메서드에서 확장할 <xref:System.String>합니다. 두 번째 매개 변수를 `punc`, 문장 부호 중 여 메서드를 호출할 때 인수로 전달 되는 문자열 이어야 것입니다. 메서드는 문장 뒤에 문자열을 표시 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]  
  
 메서드는 문자열 인수에 대 한 전송 하 여 `punc`: `example.PrintAndPunctuate(".")`  
  
 다음 예와 `Print` 고 `PrintAndPunctuate` 정의 및 호출 합니다. <xref:System.Runtime.CompilerServices> 확장 특성에 대 한 액세스를 사용 하도록 설정 하려면 정의 모듈로 가져오게 됩니다.  
  
### <a name="code"></a>코드  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 그런 다음 확장 메서드 범위로 되며 호출 됩니다.  
  
```vb  
Imports ConsoleApplication2.StringExtensions  
Module Module1  
  
    Sub Main()  
  
        Dim example As String = "Example string"  
        example.Print()  
  
        example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>설명  
 이 실행할 수 있도록 하는 데 필요한 모든 것 또는 유사한 확장 메서드는 범위에 포함 된 되도록 합니다. 확장 메서드를 포함 하는 모듈 범위에 있으면 IntelliSense에 표시 되며 일반 인스턴스 메서드인 것 처럼 호출할 수 있습니다.  
  
 메서드를 호출할 때 인수가 전송 되지 첫 번째 매개 변수를 확인 합니다. 매개 변수 `aString` 이전 메서드의 정의에 바인딩되어 `example`, 인스턴스의 `String` 호출 하는 합니다. 컴파일러를 사용 하 여 `example` 첫 번째 매개 변수에 전달 되는 인수로 합니다.  
  
 로 설정 된 개체는 확장 메서드를 호출 하는 경우 `Nothing`, 확장 메서드를 실행 합니다. 이 값은 일반 인스턴스 메서드에 적용 되지 않습니다. 명시적으로 확인할 수 있습니다 `Nothing` 확장 메서드에서.  
  
## <a name="types-that-can-be-extended"></a>확장할 수 있는 형식  
 다음과 같은 Visual Basic 매개 변수 목록에 표시할 수 있는 대부분의 형식에 확장 메서드를 정의할 수 있습니다.  
  
-   클래스 (참조 형식)  
  
-   구조체 (값 형식)  
  
-   인터페이스  
  
-   대리자  
  
-   ByRef 및 ByVal 인수  
  
-   제네릭 메서드 매개 변수  
  
-   배열  
  
 확장 메서드를 확장 하는 데이터 형식으로 지정 하므로 첫 번째 매개 변수는 필요 하며 선택 사항일 수 없습니다. 이런 이유로 `Optional` 매개 변수 및 `ParamArray` 매개 변수는 매개 변수 목록의 첫 번째 매개 변수 수 없습니다.  
  
 런타임에 바인딩에서는 확장 메서드를 사용 하는 것이 아닙니다. 다음 예에서 문은 `anObject.PrintMe()` 발생을 <xref:System.MissingMemberException> 예외, 표시 되는 경우 동일한 예외를 두 번째 `PrintMe` 확장 메서드 정의가 삭제 되었습니다.  
  
 [!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]  
  
## <a name="best-practices"></a>모범 사례  
 확장 메서드는 기존 형식을 확장 하는 편리 하 고 강력한 방법을 제공 합니다. 그러나이 성공적으로 사용 하려면 일부의 사항이 있습니다 고려해 야 합니다. 이러한 고려 사항은 주로 클래스 라이브러리 작성에 적용 되지만 확장 메서드를 사용 하는 모든 응용 프로그램에 영향을 줄 수 있습니다.  
  
 가장 일반적으로 소유 하지 않은 형식에 추가 하는 확장 메서드는 제어할 수 있는 형식에 추가 하는 확장 메서드보다 더 취약 합니다. 확장 메서드를 방해할 수 있는 클래스가 소유 하지 않은 몇 가지 발생할 수 있습니다.  
  
-   매개 변수에 인수에서 필요 없는 축소 변환을 사용 하 여 호출 하는 문의 인수를 사용 하 여 호환 되는 시그니처가 있는 모든 액세스 가능한 인스턴스 멤버가 있으면 인스턴스 메서드는 모든 확장 메서드보다 사용 됩니다. 따라서 적절 한 인스턴스 메서드를 특정 시점 클래스에 추가 되 면에 의존 하는 기존 확장 멤버를 액세스할 수 없게 될 수 있습니다.  
  
-   확장 메서드 작성자는 원래 확장 우선 순위를 있을 수 있는 충돌 하는 확장명 메서드 작성에서 다른 프로그래머가 막을 수 없습니다.  
  
-   고유한 네임 스페이스의 확장 메서드를 배치 하 여 견고성을 개선할 수 있습니다. 라이브러리의 소비자 수 다음 네임 스페이스 또는 포함 하거나 제외, 라이브러리의 나머지 부분에서 개별적으로 네임 스페이스 중에서 선택 합니다.  
  
-   인터페이스를 확장 하는 인터페이스 또는 클래스를 소유 하지 않은 경우에 특히 클래스를 확장 하는 것 보다 안전할 수도 있습니다. 인터페이스 변경 구현 하는 모든 클래스를 영향을 줍니다. 따라서 작성자 가능성이 적습니다를 추가 하거나 인터페이스의 메서드를 변경 합니다. 그러나 동일한 서명 사용 하 여 확장 메서드가 있는 두 가지 인터페이스를 구현 하는 클래스 확장 메서드 모두 표시 됩니다.  
  
-   하면 가장 구체적인 형식을 확장 합니다. 형식 계층 구조를, 다른 많은 형식 파생 되는 형식을 선택 하는 경우는 계층의 인스턴스 메서드 또는 사용자 방해가 될 수 있는 다른 확장 메서드가 생길 가능성이 있습니다.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>확장 메서드, 인스턴스 메서드 및 속성  
 범위 내 인스턴스 메서드에 호출 문의 인수와 호환 되는 서명에 있는 경우 인스턴스 메서드는 모든 확장 메서드보다 선택 됩니다. 인스턴스 메서드가 확장 메서드를 더 잘 일치 하는 경우에 우선 순위를 있습니다. 다음 예에서 `ExampleClass` 라는 인스턴스 메서드를 포함 `ExampleMethod` 매개 변수 형식이 있는 `Integer`합니다. 확장 메서드 `ExampleMethod` 확장 `ExampleClass`, 형식의 매개 변수가 하나이 고 `Long`입니다.  
  
 [!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]  
  
 첫 번째 호출은 `ExampleMethod` 하기 때문에 다음 코드에서 확장 메서드를 호출 `arg1` 됩니다 `Long` 와 호환 됩니다는 `Long` 확장 메서드의 매개 변수입니다. 두 번째 호출 `ExampleMethod` 에 `Integer` 인수를 `arg2`, 인스턴스 메서드를 호출 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]  
  
 이제 역방향 두 메서드에 있는 매개 변수의 데이터 형식:  
  
 [!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]  
  
 이번 `Main` 번 모두 인스턴스 메서드를 호출 합니다. 이므로 둘 다 `arg1` 및 `arg2` 확대 변환이 있는 `Long`, 인스턴스 메서드가 확장 메서드 두 경우 모두 보다 우선 합니다.  
  
 [!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]  
  
 따라서 확장 메서드는 기존 인스턴스 메서드를 바꿀 수 없습니다. 그러나 확장 메서드가 인스턴스 메서드와 동일한 이름이 되었으나 서명을 충돌 하지 않는 경우 두 방법 모두를 액세스할 수 있습니다. 예를 들어 경우 클래스 `ExampleClass` 라는 메서드가 있는 `ExampleMethod` 아니요 인수, 동일한 이름의 확장 메서드를 사용 하지만 다음 코드와 같이 서로 다른 서명 허용 됩니다.  
  
 [!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]  
  
 이 코드에서 출력을 아래와 같습니다.  
  
 `Extension method`  
  
 `Instance method`  
  
 상황은 속성을 사용 하 여 간단한: 확장 하는 클래스의 속성으로 확장 메서드를 사용 하는 동일한 이름이 있는 경우 확장 메서드가 표시 되지 않으며 액세스할 수 없습니다.  
  
## <a name="extension-method-precedence"></a>확장 메서드 우선 순위  
 시그니처가 동일한 두 확장 메서드가 범위에 액세스할 수 있는 경우 우선 순위가 높은 것이 호출 됩니다. 확장 메서드의 우선 순위는 메서드를 범위로 사용 하는 메커니즘을 기반으로 합니다. 다음 목록에는 최고부터 최하까지 우선 순위 계층을 보여 줍니다.  
  
1. 현재 모듈 안에 정의 된 확장 메서드입니다.  
  
2. 확장 메서드 정의 된 데이터 내 형식 현재 네임 스페이스 또는 부모 중 하나에서 자식 네임 스페이스가 부모 네임 스페이스 보다 우선 순위가 높습니다.  
  
3. 현재 파일에서 형식 가져오기 안에 정의 된 확장 메서드.  
  
4. 현재 파일에서 네임 스페이스 가져오기 안에 정의 된 확장 메서드.  
  
5. 프로젝트 수준의 형식 가져오기 안에 정의 된 확장 메서드.  
  
6. 프로젝트 수준의 네임 스페이스 가져오기 안에 정의 된 확장 메서드.  
  
 우선 순위는 모호성을 해결 되지 않으면, 호출 하는 방법을 지정 하는 정규화 된 이름을 사용할 수 있습니다. 경우는 `Print` 앞의 예제에서는 메서드가 라는 모듈에 정의 되어 `StringExtensions`, 정규화 된 이름은 `StringExtensions.Print(example)` 대신 `example.Print()`합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [확장명 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Module 문](../../../../visual-basic/language-reference/statements/module-statement.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [선택적 매개 변수](./optional-parameters.md)
- [매개 변수 배열](./parameter-arrays.md)
- [특성 개요](../../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
