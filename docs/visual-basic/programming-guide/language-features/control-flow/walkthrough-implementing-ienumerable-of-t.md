---
title: IEnumerable 구현
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266913"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>연습: 시각적 기본에서 IEnumerable(T) 구현
인터페이스는 <xref:System.Collections.Generic.IEnumerable%601> 한 번에 하나의 항목값 시퀀스를 반환할 수 있는 클래스에 의해 구현됩니다. 한 번에 하나의 항목을 반환하는 이점은 전체 데이터 집합을 메모리에 로드할 필요가 없다는 것입니다. 데이터에서 단일 항목을 로드하려면 충분한 메모리만 사용해야 합니다. 인터페이스를 `IEnumerable(T)` 구현하는 클래스는 루프 `For Each` 또는 LINQ 쿼리와 함께 사용할 수 있습니다.  
  
 예를 들어 큰 텍스트 파일을 읽고 특정 검색 조건과 일치하는 파일에서 각 줄을 반환해야 하는 응용 프로그램을 생각해 보십시오. 응용 프로그램은 LINQ 쿼리를 사용하여 지정된 조건과 일치하는 파일에서 줄을 반환합니다. LINQ 쿼리를 사용하여 파일의 내용을 쿼리하기 위해 응용 프로그램은 파일의 내용을 배열 또는 컬렉션에 로드할 수 있습니다. 그러나 전체 파일을 배열 또는 컬렉션에 로드하면 필요한 것보다 훨씬 많은 메모리가 소비됩니다. LINQ 쿼리대신 열거 가능한 클래스를 사용하여 파일 내용을 쿼리하고 검색 조건과 일치하는 값만 반환할 수 있습니다. 일치하는 값만 몇 개만 반환하는 쿼리는 메모리를 훨씬 적게 사용합니다.  
  
 원본 데이터를 열거 가능한 <xref:System.Collections.Generic.IEnumerable%601> 데이터로 노출하도록 인터페이스를 구현하는 클래스를 만들 수 있습니다. 인터페이스를 `IEnumerable(T)` 구현하는 클래스에는 원본 데이터를 반복하기 <xref:System.Collections.Generic.IEnumerator%601> 위해 인터페이스를 구현하는 다른 클래스가 필요합니다. 이 두 클래스를 사용하면 데이터의 항목을 특정 유형으로 순차적으로 반환할 수 있습니다.  
  
 이 연습에서는 `IEnumerable(Of String)` 인터페이스를 구현하는 클래스와 한 번에 한 줄에 `IEnumerator(Of String)` 텍스트 파일을 읽는 인터페이스를 구현하는 클래스를 만듭니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>열거가능한 클래스 만들기  
  
**열거 가능한 클래스 프로젝트 만들기**

1. 시각적 기본에서 **파일** 메뉴에서 **새로** 를 가리킨 다음 **프로젝트를**클릭합니다.

1. **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다. **템플릿** 창에서 **클래스 라이브러리**를 선택합니다. **이름** 상자에 `StreamReaderEnumerable`을 입력한 다음 **확인**을 클릭합니다. 새 프로젝트가 표시됩니다.

1. **솔루션 탐색기에서**Class1.vb 파일을 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기를**클릭합니다. 파일 이름을 `StreamReaderEnumerable.vb`로 바꾸고 ENTER 키를 누릅니다. 파일 이름을 바꾸면 클래스 이름도 `StreamReaderEnumerable`으로 바뀝니다. 이 클래스는 `IEnumerable(Of String)` 인터페이스를 구현합니다.

1. StreamReader열화 가능한 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가를**가리킨 다음 **새 항목을**클릭합니다. 클래스 템플릿을 **선택합니다.** **이름** 상자에 `StreamReaderEnumerator.vb`를 입력하고 **확인**을 클릭합니다.

 이 프로젝트의 첫 번째 클래스는 열거 가능한 클래스이며 인터페이스를 `IEnumerable(Of String)` 구현합니다. 이 일반 인터페이스는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하고 이 클래스의 소비자가 로 `String`입력된 값에 액세스할 수 있도록 보장합니다.  
  
**IEnumerable을 구현하는 코드 추가**

1. StreamReaderEnumerable.vb 파일을 엽니다.

2. 다음 `Public Class StreamReaderEnumerable`줄을 입력하고 ENTER를 누릅니다.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic은 인터페이스에 필요한 멤버로 클래스를 `IEnumerable(Of String)` 자동으로 채웁니다.
  
3. 이 열거형 클래스는 한 번에 한 줄의 텍스트 파일에서 줄을 읽습니다. 다음 코드를 클래스에 추가하여 파일 경로를 입력 매개 변수로 하는 공용 생성기를 노출합니다.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. 인터페이스 메서드를 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 구현하면 클래스의 새 인스턴스가 `StreamReaderEnumerator` 반환됩니다. `IEnumerable(Of String)` 인터페이스의 `GetEnumerator` 멤버만 노출해야 하기 `Private`때문에 인터페이스 메서드의 구현을 `IEnumerable(Of String)` 수행할 수 있습니다. `IEnumerable` 메서드에 대해 생성된 Visual `GetEnumerator` Basic 코드를 다음 코드로 바꿉니다.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**IEnumerator를 구현하는 코드 추가**

1. StreamReaderEnumerator.vb 파일을 엽니다.

2. 다음 `Public Class StreamReaderEnumerator`줄을 입력하고 ENTER를 누릅니다.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic은 인터페이스에 필요한 멤버로 클래스를 `IEnumerator(Of String)` 자동으로 채웁니다.

3. 열거자 클래스는 텍스트 파일을 열고 파일 I/O를 수행하여 파일에서 줄을 읽습니다. 다음 코드를 클래스에 추가하여 파일 경로를 입력 매개 변수로 사용하는 공용 생성기를 노출하고 읽을 텍스트 파일을 엽니다.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. 및 `Current` `IEnumerator(Of String)` 인터페이스모두에 대한 속성은 텍스트 파일에서 현재 항목을 로 반환합니다. `String` `IEnumerator` 인터페이스의 멤버만 `Current` 노출해야 하므로 `IEnumerator(Of String)` 인터페이스의 속성을 구현할 수 있습니다. `Private` `IEnumerator` 속성에 대해 생성된 Visual `Current` Basic 코드를 다음 코드로 바꿉니다.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. 인터페이스 `MoveNext` 메서드는 `IEnumerator` 텍스트 파일의 다음 항목으로 이동 하 고 `Current` 속성에서 반환 되는 값을 업데이트 합니다. 읽을 항목이 더 이상 없는 `MoveNext` 경우 `False`메서드가 반환합니다. 그렇지 `MoveNext` 않으면 `True`메서드가 반환합니다. `MoveNext` 메서드에 다음 코드를 추가합니다.

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. `IEnumerator` 인터페이스의 메서드는 `Reset` 반복기를 텍스트 파일의 시작을 가리키도록 지시하고 현재 항목 값을 지웁히 지웁습니다. `Reset` 메서드에 다음 코드를 추가합니다.

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. 인터페이스 `Dispose` 방법은 `IEnumerator` 관리되지 않는 모든 리소스가 처리기를 소멸하기 전에 해제되도록 보장합니다. 개체에서 `StreamReader` 사용하는 파일 핸들은 관리되지 않는 리소스이며 거무자 인스턴스가 삭제되기 전에 닫아야 합니다. 메서드에 대해 생성된 Visual `Dispose` Basic 코드를 다음 코드로 바꿉니다.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>샘플 이터레이터 사용

 루프 또는 LINQ 쿼리와 같이 구현하는 `IEnumerable`개체가 필요한 컨트롤 구조와 함께 코드에서 열거 가능한 클래스를 사용할 수 있습니다. `For Next` 다음 예제에서는 `StreamReaderEnumerable` LINQ 쿼리를 보여 주습니다.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [루프 구조체](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
