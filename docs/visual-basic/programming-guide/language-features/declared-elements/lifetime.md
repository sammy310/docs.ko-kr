---
title: 수명
ms.date: 07/20/2015
helpviewer_keywords:
- static variables [Visual Basic], lifetime
- static variables [Visual Basic], Visual Basic
- declared elements [Visual Basic], lifetime
- Shared variable lifetime [Visual Basic]
- lifetime [Visual Basic], declared elements
- lifetime [Visual Basic], Visual Basic
- lifetime [Visual Basic]
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
ms.openlocfilehash: 293537ad33c8e751d49d820fc57ea525e68bc203
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347770"
---
# <a name="lifetime-in-visual-basic"></a>Visual Basic의 수명
선언 된 요소의 *수명은* 사용할 수 있는 기간입니다. 변수는 수명이 있는 유일한 요소입니다. 이러한 목적을 위해 컴파일러는 프로시저 매개 변수와 함수 반환을 변수의 특수 한 경우로 처리 합니다. 변수의 수명은 값을 보유할 수 있는 기간을 나타냅니다. 해당 값은 수명에 따라 변경 될 수 있지만 항상 일부 값을 포함 합니다.  
  
## <a name="different-lifetimes"></a>다른 수명  
 *멤버 변수* (프로시저 외부의 모듈 수준에서 선언 됨)는 일반적으로 선언 되는 요소의 수명과 동일 합니다. 클래스 또는 구조체에서 선언 된 비공유 변수가 선언 된 클래스 또는 구조체의 각 인스턴스에 대해 별도의 복사본으로 존재 합니다. 이러한 각 변수의 수명은 인스턴스와 동일 합니다. 그러나 `Shared` 변수에는 응용 프로그램이 실행 되는 전체 시간 동안 지속 되는 단일 수명이 있습니다.  
  
 프로시저 내에 선언 된 *지역 변수* 는 해당 변수가 선언 된 프로시저가 실행 되는 동안에만 존재 합니다. 이는 해당 프로시저의 매개 변수와 함수 반환에도 적용 됩니다. 그러나 해당 프로시저가 다른 프로시저를 호출 하는 경우 호출 된 프로시저를 실행 하는 동안에는 지역 변수가 해당 값을 유지 합니다.  
  
## <a name="beginning-of-lifetime"></a>수명 시작  
 지역 변수의 수명은 컨트롤이 선언 된 프로시저를 시작할 때 시작 됩니다. 모든 지역 변수는 프로시저 실행이 시작 되는 즉시 해당 데이터 형식에 대 한 기본값으로 초기화 됩니다. 프로시저에서 초기 값을 지정 하는 `Dim` 문이 발견 되 면 코드에 다른 값을 이미 할당 한 경우에도 해당 변수를 해당 값으로 설정 합니다.  
  
 구조체 변수의 각 멤버는 개별 변수인 것 처럼 초기화 됩니다. 마찬가지로 배열 변수의 각 요소는 개별적으로 초기화 됩니다.  
  
 프로시저 내의 블록 (예: `For` 루프) 내에서 선언 된 변수는 프로시저에 대 한 항목에서 초기화 됩니다. 이러한 초기화는 코드에서 블록을 실행 하는지 여부에 관계 없이 적용 됩니다.  
  
## <a name="end-of-lifetime"></a>수명 끝  
 프로시저가 종료 되 면 해당 지역 변수의 값은 유지 되지 않으며 Visual Basic 메모리를 회수 합니다. 다음 번에 프로시저를 호출 하면 모든 지역 변수가 새로 생성 되어 다시 초기화 됩니다.  
  
 클래스 또는 구조체의 인스턴스가 종료 되 면 비공유 변수의 메모리와 값이 손실 됩니다. 클래스 또는 구조체의 새 인스턴스는 모두 비공유 변수를 만들고 다시 초기화 합니다. 그러나 `Shared` 변수는 응용 프로그램 실행이 중지 될 때까지 유지 됩니다.  
  
## <a name="extension-of-lifetime"></a>수명 확장  
 `Static` 키워드를 사용 하 여 지역 변수를 선언 하는 경우 해당 수명은 프로시저의 실행 시간 보다 깁니다. 다음 표에서는 프로시저 선언에 `Static` 변수가 존재 하는 기간을 결정 하는 방법을 보여 줍니다.  
  
|프로시저 위치 및 공유|정적 변수 수명이 시작 됩니다.|정적 변수 수명 종료|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|모듈 (기본적으로 공유)|프로시저가 처음 호출 될 때|응용 프로그램 실행이 중지 되는 경우|  
|클래스에서 `Shared` (프로시저는 인스턴스 멤버가 아님)|프로시저가 특정 인스턴스나 클래스 또는 구조체 이름 자체에서 처음 호출 될 때|응용 프로그램 실행이 중지 되는 경우|  
|`Shared` 아닌 클래스의 인스턴스 (프로시저는 인스턴스 멤버)|프로시저가 특정 인스턴스에서 처음으로 호출 될 때|GC (가비지 수집)를 위해 인스턴스를 해제 하는 경우|  
  
## <a name="static-variables-of-the-same-name"></a>이름이 같은 정적 변수  
 둘 이상의 프로시저에서 동일한 이름으로 정적 변수를 선언할 수 있습니다. 이 작업을 수행 하는 경우 Visual Basic 컴파일러는 이러한 각 변수를 별도 요소로 간주 합니다. 이러한 변수 중 하나를 초기화 해도 다른 변수 값에는 영향을 주지 않습니다. 오버 로드 집합을 사용 하 여 프로시저를 정의 하 고 각 오버 로드에서 동일한 이름을 사용 하 여 정적 변수를 선언 하는 경우에도 마찬가지입니다.  
  
## <a name="containing-elements-for-static-variables"></a>정적 변수에 대 한 요소 포함  
 클래스 내에서, 즉 해당 클래스의 프로시저 내에서 정적 지역 변수를 선언할 수 있습니다. 그러나 구조체 내에서 정적 지역 변수를 구조체 멤버 또는 해당 구조 내 프로시저의 지역 변수로 선언할 수 없습니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 다음 예에서는 [Static](../../../../visual-basic/language-reference/modifiers/static.md) 키워드를 사용 하 여 변수를 선언 합니다. [Dim 문이](../../../../visual-basic/language-reference/statements/dim-statement.md) `Static`와 같은 한정자를 사용 하는 경우에는 `Dim` 키워드가 필요 하지 않습니다.  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbalrKeywords#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#13)]  
  
### <a name="comments"></a>설명  
 앞의 예제에서 `applesSold` 변수는 프로시저 `runningTotal` 호출 코드로 반환 된 후에도 계속 존재 합니다. 다음에 `runningTotal`를 호출 하면 `applesSold` 이전에 계산 된 값을 유지 합니다.  
  
 `Static`를 사용 하지 않고 `applesSold` 선언 된 경우 이전 누적 값은 `runningTotal`호출에서 유지 되지 않습니다. 다음에 `runningTotal`가 호출 되 면 `applesSold` 다시 생성 되 고 0으로 초기화 되며 `runningTotal`는 호출 된 것과 동일한 값을 반환 합니다.  
  
### <a name="compile-the-code"></a>코드 컴파일  
 정적 지역 변수의 값을 선언의 일부로 초기화할 수 있습니다. `Static`배열을 선언 하는 경우 차수 (차원 수), 각 차원의 길이 및 개별 요소의 값을 초기화할 수 있습니다.  
  
### <a name="security"></a>보안  
 위의 예제에서는 모듈 수준에서 `applesSold`를 선언 하 여 동일한 수명을 생성할 수 있습니다. 그러나 이러한 방식으로 변수의 범위를 변경한 경우 프로시저는 더 이상 단독으로 액세스할 수 없습니다. 다른 프로시저가 `applesSold`에 액세스 하 고 해당 값을 변경할 수 있기 때문에 누계는 안정적이 고 코드를 유지 관리 하기가 더 어려울 수 있습니다.  
  
## <a name="see-also"></a>참조

- [공유](../../../../visual-basic/language-reference/modifiers/shared.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Visual Basic 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
