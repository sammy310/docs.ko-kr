---
title: Like 연산자
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: 49dfe5cf5dbcf8dc6f79f569a92e36aa81806913
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866778"
---
# <a name="like-operator-visual-basic"></a>Like 연산자(Visual Basic)

문자열과 패턴을 비교 합니다.  

> [!IMPORTANT]
> `Like`연산자는 현재 .Net Core 및 .NET Standard 프로젝트에서 지원 되지 않습니다.

## <a name="syntax"></a>구문  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a>부분  

 `result`  
 필수 사항입니다. 모든 `Boolean` 변수. 결과는가를 `Boolean` 충족 하는지 여부를 나타내는 값입니다 `string` `pattern` .  
  
 `string`  
 필수 요소. 임의의 `String` 식입니다.  
  
 `pattern`  
 필수 요소. `String`"주의"에 설명 된 패턴 일치 규칙을 준수 하는 모든 식입니다.  
  
## <a name="remarks"></a>설명  

 의 값 `string` 이에 포함 된 패턴을 충족 `pattern` 하는 경우 `result` 는 `True` 입니다. 문자열이 패턴을 충족 하지 않는 경우 `result` 는 `False` 입니다. 및가 `string` 모두 `pattern` 빈 문자열인 경우 결과는 `True` 입니다.  
  
## <a name="comparison-method"></a>비교 방법  

 연산자의 동작은 `Like` [Option Compare 문에](../statements/option-compare-statement.md)따라 달라 집니다. 각 소스 파일에 대 한 기본 문자열 비교 방법은 `Option Compare Binary` 입니다.  
  
## <a name="pattern-options"></a>패턴 옵션  

 기본 제공 패턴 일치는 문자열 비교를 위한 다양 한 도구를 제공 합니다. 패턴 일치 기능을 사용 하면 `string` 특정 문자, 와일드 카드 문자, 문자 목록 또는 문자 범위에 대해의 각 문자를 일치 시킬 수 있습니다. 다음 표에서는에서 허용 되는 문자와 일치 하는 문자를 보여 줍니다 `pattern` .  
  
|문자 `pattern`|일치 항목 `string`|  
|-----------------------------|-------------------------|  
|`?`|임의의 단일 문자|  
|`*`|0 개 이상의 문자|  
|`#`|임의의 단일 숫자 (0-9)|  
|`[charlist]`|의 단일 문자 `charlist`|  
|`[!charlist]`|에 없는 모든 단일 문자 `charlist`|  
  
## <a name="character-lists"></a>문자 목록  

 대괄호 ()로 묶인 하나 이상의 문자 () 그룹을 `charlist` `[ ]` 사용 하 여의 단일 문자를 일치 `string` 시키고, 숫자를 비롯 한 거의 모든 문자 코드를 포함할 수 있습니다.  
  
 의 시작 부분에서 느낌표 ( `!` )는의 `charlist` 문자를 제외한 모든 문자를에서 찾을 수 있으면 일치가 수행 됨을 의미 `charlist` `string` 합니다. 대괄호 외부에서 사용 하는 경우 느낌표는 자체와 일치 합니다.  
  
## <a name="special-characters"></a>특수 문자  

 특수 문자 왼쪽 대괄호 ( `[` ), 물음표 ( `?` ), 숫자 기호 () `#` 및 별표 ()를 일치 시키려면 `*` 대괄호로 묶습니다. `]`그룹 내에서 오른쪽 대괄호 ()를 사용 하 여 자신을 일치 시킬 수는 없지만 그룹 외부에서 개별 문자로 사용할 수 있습니다.  
  
 문자 시퀀스는 `[]` 길이가 0 인 문자열 ()로 간주 됩니다 `""` . 그러나 대괄호로 묶은 문자 목록의 일부일 수는 없습니다. 의 위치에 `string` 문자 그룹 중 하나가 포함 되어 있는지 또는 문자가 없는지를 확인 하려는 경우 두 번 사용할 수 있습니다 `Like` . 예제는 [방법: 패턴에 대해 문자열 일치](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)를 참조 하세요.  
  
## <a name="character-ranges"></a>문자 범위  

 하이픈 ()을 사용 하 여 `–` 범위의 하 한 및 상한을 구분 하면에서 `charlist` 문자 범위를 지정할 수 있습니다. 예를 `[A–Z]` 들어,의 해당 문자 위치에 –의 모든 문자가 포함 된 경우 일치 항목이 반환 되 `string` `A` `Z` 고 `[!H–L]` 해당 문자 위치에-범위를 벗어난 문자가 포함 된 경우 일치 항목이 반환 `H` `L` 됩니다.  
  
 문자 범위를 지정 하는 경우 오름차순 정렬 순서로 표시 되어야 합니다. 따라서 `[A–Z]` 는 유효한 패턴 이지만 `[Z–A]` 는 그렇지 않습니다.  
  
### <a name="multiple-character-ranges"></a>여러 문자 범위  

 동일한 문자 위치에 여러 범위를 지정 하려면 구분 기호 없이 동일한 대괄호 안에 배치 합니다. 예를 `[A–CX–Z]` 들어의 해당 문자 위치에 `string` 범위 또는 범위 내에 있는 문자가 포함 된 경우는 일치 하는 항목을 반환 합니다 `A` `C` `X` `Z` .  
  
### <a name="usage-of-the-hyphen"></a>하이픈 사용  

 하이픈 ( `–` )은 시작 부분 (느낌표 이후) 또는 끝 부분 (의 끝)에 표시 될 수 있습니다 `charlist` . 다른 위치에서 하이픈은 하이픈 양쪽의 문자로 구분 되는 문자 범위를 식별 합니다.  
  
## <a name="collating-sequence"></a>데이터 정렬 순서  

 지정 된 범위의 의미는 런타임에의 문자 순서 `Option Compare` 와 코드를 실행 하는 시스템의 로캘 설정에 따라 달라 집니다. 에서 `Option Compare Binary` 범위는,,, `[A–E]` 및와 일치 `A` `B` `C` `D` `E` 합니다. 에서,,,,,,,,,, `Option Compare Text` `[A–E]` 및를 일치 시킵니다 `A` `a` `À` `à` `B` `b` `C` `c` `D` `d` `E` `e` . 범위가 일치 하지 않거나 `Ê` , `ê` 악센트 부호가 있는 문자가 정렬 순서에서 악센트가 없는 문자 다음에 정렬 되기 때문입니다.  
  
## <a name="digraph-characters"></a>D i g 문자  

 일부 언어에는 두 개의 개별 문자를 나타내는 영문자가 있습니다. 예를 들어 여러 언어는 문자를 사용 `æ` 하 여 문자를 나타내고 `a` `e` 함께 표시 될 때 문자를 사용 합니다. `Like`연산자는 단일 d i g 문자 및 두 개의 개별 문자가 동일 하다는 것을 인식 합니다.  
  
 D i g 문자를 사용 하는 언어가 시스템 로캘 설정에 지정 된 경우 또는의 단일 d i g 문자가 `pattern` `string` 다른 문자열의 두 문자 시퀀스와 일치 합니다. 마찬가지로 `pattern` 대괄호 안에 포함 된 d i g 문자 (목록 또는 범위)는의 두 문자 시퀀스와 일치 합니다 `string` .  
  
## <a name="overloading"></a>오버로딩  

 `Like`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  

 이 예제에서는 연산자를 사용 하 여 `Like` 문자열을 다양 한 패턴과 비교 합니다. 결과는 `Boolean` 각 문자열이 패턴을 충족 하는지 여부를 나타내는 변수로 이동 합니다.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [비교 연산자](comparison-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [Option Compare 문](../statements/option-compare-statement.md)
- [연산자 및 식](../../programming-guide/language-features/operators-and-expressions/index.md)
- [방법: 패턴에 대해 문자열 비교](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
