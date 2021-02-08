---
description: '#Region 지시문에 대해 자세히 알아보세요.'
title: '#Region 지시문'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: 4ba1645cfc51a69d39e6a60b5ea236dd65883e1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797226"
---
# <a name="region-directive"></a>#Region 지시문

Visual Basic 파일에서 코드 섹션을 축소하고 숨깁니다.  
  
## <a name="syntax"></a>Syntax  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`identifier_string`|필수 요소. 축소된 경우 영역의 제목 역할을 하는 문자열입니다. 영역은 기본적으로 축소되어 있습니다.|  
|`#End Region`|`#Region` 블록을 종료합니다.|  
  
## <a name="remarks"></a>설명  

 `#Region` 지시문을 사용하면 Visual Studio 코드 편집기의 개요 기능을 사용할 때 확장하거나 축소할 코드 블록을 지정할 수 있습니다. 다른 지역 내에서 영역을 추가 하거나 *중첩* 하 여 비슷한 지역을 함께 그룹화 할 수 있습니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 `#Region` 지시문을 사용합니다.  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>참고 항목

- [#If...Then...#Else 지시문](if-then-else-directives.md)
- [개요](/visualstudio/ide/outlining)
- [방법: 코드 섹션 축소 및 숨기기](../../programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
