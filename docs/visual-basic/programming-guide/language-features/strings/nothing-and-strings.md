---
title: Nothing 및 문자열
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 392de45b0ee1688224f3e8170b0144f1acdb0912
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360568"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Visual Basic의 Nothing 및 문자열
Visual Basic 런타임 및 .NET Framework는 `Nothing` 문자열에 제공 되는 경우 다르게 평가 됩니다.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic 런타임 및 .NET Framework  
 다음 예제를 참조하세요.  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Visual Basic 런타임은 일반적으로 `Nothing` 빈 문자열 ("")로 계산 됩니다. 그러나 .NET Framework는에 대해 문자열 작업을 수행 하려고 할 때마다 예외를 throw 하지 않습니다 `Nothing` .  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 문자열 소개](introduction-to-strings.md)
