---
title: REM 문
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: bdde4beae242c3175b02cd2af252babb850416f6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346724"
---
# <a name="rem-statement-visual-basic"></a>REM 문(Visual Basic)
프로그램의 소스 코드에 설명 설명을 포함 하는 데 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>요소  
 `comment`  
 (선택 사항) 포함 하려는 주석의 텍스트입니다. `REM` 키워드와 `comment`사이에 공백이 필요 합니다.  
  
## <a name="remarks"></a>주의  
 `REM` 문을 한 줄에 단독으로 넣거나 다른 문 다음의 줄에 삽입할 수 있습니다. `REM` 문은 줄의 마지막 문 이어야 합니다. 다른 문을 따르는 경우에는 `REM`를 해당 문에서 공백으로 구분 해야 합니다.  
  
 `REM`대신 작은따옴표 (`'`)를 사용할 수 있습니다. 이는 주석이 동일한 줄에서 다른 문을 팔 로우 하거나 한 줄에만 적용 되는지 여부에 해당 합니다.  
  
> [!NOTE]
> `_`(줄 연속 시퀀스)를 사용 하 여 `REM` 문을 계속할 수 없습니다. 주석이 시작 되 면 컴파일러는 특수 한 의미에 대 한 문자를 검사 하지 않습니다. 여러 줄로 된 주석을 보려면 각 줄에서 다른 `REM` 문이나 주석 기호 (`'`)를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 프로그램에 설명 설명을 포함 하는 데 사용 되는 `REM` 문을 보여 줍니다. 또한 `REM`대신 작은따옴표 (`'`)를 사용 하는 대신 사용 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- [코드 주석](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
