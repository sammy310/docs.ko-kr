---
title: Nothing 및 문자열
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344304"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Visual Basic의 Nothing 및 문자열
Visual Basic 런타임 및 .NET Framework는 문자열에 대 한 `Nothing`를 다르게 평가 합니다.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic 런타임 및 .NET Framework  
 다음 예제를 참조하세요.  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Visual Basic 런타임은 일반적으로 `Nothing`를 빈 문자열 ("")로 평가 합니다. 그러나 .NET Framework는 `Nothing`에서 문자열 작업을 수행 하려고 할 때마다 예외를 throw 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
