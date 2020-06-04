---
title: Erase 문
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 31aeaf822bc9c1de59a5c5f68406c6521216ae0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404721"
---
# <a name="erase-statement-visual-basic"></a>Erase 문(Visual Basic)
배열 변수를 해제 하 고 해당 요소에 사용 되는 메모리의 할당을 취소 하는 데 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>부분  
 `arraylist`  
 필수 요소. 지울 배열 변수의 목록입니다. 여러 변수는 쉼표로 구분됩니다.  
  
## <a name="remarks"></a>설명  
 `Erase`문은 프로시저 수준 에서만 나타날 수 있습니다. 즉, 프로시저 내에서 배열을 해제할 수 있지만 클래스 또는 모듈 수준에서는 해제할 수 없습니다.  
  
 `Erase`문은 각 배열 변수에 할당 하는 것과 같습니다 `Nothing` .  
  
## <a name="example"></a>예제  
 다음 예제에서는 문을 사용 하 여 `Erase` 두 배열을 지우고 해당 메모리 (1000 및 100 저장소 요소 각각)를 해제 합니다. `ReDim`그런 다음 문이 새 배열 인스턴스를 3 차원 배열에 할당 합니다.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>참고 항목

- [Nothing](../nothing.md)
- [ReDim 문](redim-statement.md)
