---
title: 참조 및 Imports 문(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: f3396eb3e758dc456d86de80246de24349680f2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967754"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>참조 및 Imports 문(Visual Basic)
있습니다 수 외부 개체에 사용할 프로젝트를 선택 하 여 합니다 **참조 추가** 명령 합니다 **프로젝트** 메뉴. Visual Basic에는 형식 라이브러리 하지만 자세한 정보를 포함 하는 같은 어셈블리를 참조할 수 있습니다.  
  
## <a name="the-imports-statement"></a>Imports 문  
 어셈블리는 하나 이상의 네임 스페이스를 포함 합니다. 어셈블리에 대 한 참조를 추가할 때 추가할 수도 있습니다는 `Imports` 모듈 내에서 해당 어셈블리의 네임 스페이스의 표시 유형을 제어 하는 모듈에는 문입니다. `Imports` 문을 고유한 참조를 제공 하는 데 필요한 네임 스페이스의 부분에만 사용할 수 있도록 범위 지정 컨텍스트를 제공 합니다.  
  
 `Imports` 문에 다음 구문:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` 가져온된 네임 스페이스를 가리키도록 코드 내에서 사용할 수 있습니다 약식 이름을 가리킵니다. `Namespace` 네임 스페이스 중 하나를 통해 사용할 수 있는 프로젝트 참조를 프로젝트 내에서 정의 통해 또는 이전 `Imports` 문입니다.  
  
 모듈에는 개수에 관계 없이 포함 될 수 있습니다 `Imports` 문입니다. 이후 나타나야 합니다. `Option` 문, 있는 경우 다른 코드 전에 합니다.  
  
> [!NOTE]
>  포함 된 프로젝트 참조를 혼동 하지 마십시오 합니다 `Imports` 문 또는 `Declare` 문입니다. 프로젝트 참조 어셈블리의 개체와 같은 외부 개체를 Visual Basic 프로젝트를 사용할 수 있도록 합니다. `Imports` 문을 프로젝트 참조에 대 한 액세스를 간소화는 데 사용 되지만 이러한 개체에 대 한 액세스를 제공 하지 않습니다. `Declare` 문을 사용 하는 동적 연결 라이브러리 (DLL)에 외부 프로시저에 대 한 참조를 선언 합니다.  
  
## <a name="using-aliases-with-the-imports-statement"></a>Imports 문을 사용 하 여 별칭을 사용 하 여  
 `Imports` 문을 사용 하면 클래스의 메서드에 대 한 액세스를 쉽게 참조의 정규화 된 이름을 명시적으로 입력할 필요가 없습니다. 별칭을 통해 네임 스페이스의 한 부분에 친숙 한 이름을 지정할 수 있습니다. 캐리지 리턴/줄 바꿈 여러 줄에 표시할 텍스트는 단일 시퀀스의 일부인 예를 들어 합니다 <xref:Microsoft.VisualBasic.ControlChars> 모듈에는 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 네임 스페이스입니다. 이 상수 별칭 없이 프로그램을 사용 하려면 다음 코드를 입력 해야 합니다.  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` 문은 바로 다음 첫 번째 줄은 반드시 `Option` 모듈의 문이 있습니다. 다음 코드 조각 가져오기에 대 한 별칭을 할당 하는 방법을 보여 줍니다는 <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> 모듈:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 이 네임 스페이스에 대 한 향후 참조 짧아집니다 될 수 있습니다.  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 경우는 `Imports` 문에 별칭 이름을 지정 하지 않은, 한정자 없이 모듈에서 가져온된 네임 스페이스 내에 정의 된 요소를 사용할 수 있습니다. 별칭을 지정 하는 경우 해당 네임 스페이스 내에 포함 된 이름에 대 한 한정자로 사용 되어야 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [.NET 어셈블리](../../../standard/assembly/index.md)
- [방법: 명령줄을 사용하여 어셈블리 만들기 및 사용](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
- [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
