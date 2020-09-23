---
title: variables
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: bd6417033a6c2626d17ad003de6c637dd1e8adaa
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080220"
---
# <a name="variables-in-visual-basic"></a>Visual Basic의 변수

Visual Basic를 사용 하 여 계산을 수행 하는 경우 값을 저장 해야 하는 경우가 많습니다. 예를 들어 여러 값을 계산하여 비교하고 비교 결과에 따라 값에서 다른 작업을 수행해야 할 수 있습니다. 값을 비교하려면 값을 보존해야 합니다.  
  
## <a name="usage"></a>사용  

 Visual Basic 대부분의 프로그래밍 언어와 마찬가지로에서는 변수를 사용 하 여 값을 저장 합니다. *변수*에는 이름(변수에 포함된 값을 참조하는 데 사용할 단어)이 있습니다. 변수에는 데이터 형식(변수가 저장할 수 있는 데이터 종류 결정)도 있습니다. 변수는 밀접하게 관련된 데이터 항목의 인덱싱된 집합을 저장해야 할 경우 배열을 나타낼 수 있습니다.  
  
 데이터 형식을 명시적으로 지정하지 않고 지역 형식 유추를 사용하여 변수를 선언할 수 있습니다. 대신에 컴파일러는 초기화 식의 형식에서 변수 형식을 유추합니다. 자세한 내용은 [지역 형식 유추](local-type-inference.md) 및 [Option Infer 문](../../../language-reference/statements/option-infer-statement.md)을 참조하세요.  
  
## <a name="assigning-values"></a>값 할당  

 다음 예제와 같이 대입문을 사용하여 계산을 수행하고 결과를 변수에 할당합니다.  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> 이 예제의 등호(`=`)는 같음 연산자가 아닌 대입 연산자입니다. 값이 `applesSold` 변수에 할당됩니다.  
  
 자세한 내용은 [방법: 변수 값 저장 및 검색](how-to-move-data-into-and-out-of-a-variable.md)을 참조하세요.  
  
## <a name="variables-and-properties"></a>변수 및 속성  

 변수처럼 *속성*은 액세스할 수 있는 값을 나타냅니다. 그러나 변수보다 더 복잡합니다. 속성에는 값을 설정 및 검색하는 방법을 제어하는 코드 블록이 사용됩니다. 자세한 내용은 [Visual Basic에서 속성과 변수의 차이점](../procedures/differences-between-properties-and-variables.md)을 참조하세요.  
  
## <a name="see-also"></a>참조

- [변수 선언](variable-declaration.md)
- [개체 변수](object-variables.md)
- [변수 문제 해결](troubleshooting-variables.md)
- [방법: 변수 값 저장 및 검색](how-to-move-data-into-and-out-of-a-variable.md)
- [Visual Basic에서 속성과 변수의 차이점](../procedures/differences-between-properties-and-variables.md)
- [지역 형식 유추](local-type-inference.md)
