---
title: '방법: 컬렉션 이니셜라이저에 사용되는 확장 추가 메서드 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 6d5f9d38b413b79f111a14ec3829c57a9797ce54
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346716"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>방법: 컬렉션 이니셜라이저에 사용되는 확장 추가 메서드 만들기(Visual Basic)
컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만드는 경우 Visual Basic 컴파일러는 컬렉션 형식의 `Add` 메서드를 검색 하 여 `Add` 메서드의 매개 변수가 컬렉션 이니셜라이저의 값 형식과 일치 하는지 확인 합니다. 이 `Add` 메서드는 컬렉션을 컬렉션 이니셜라이저의 값으로 채우는 데 사용 됩니다.  
  
 일치 하는 `Add` 메서드가 없고 컬렉션의 코드를 수정할 수 없는 경우 컬렉션 이니셜라이저에 필요한 매개 변수를 사용 하는 `Add` 라는 확장명 메서드를 추가할 수 있습니다. 일반적으로 제네릭 컬렉션에 대해 컬렉션 이니셜라이저를 사용할 때 수행 해야 하는 작업입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 컬렉션 이니셜라이저를 사용 하 여 `Employee`형식의 개체를 추가할 수 있도록 제네릭 <xref:System.Collections.Generic.List%601> 형식에 확장 메서드를 추가 하는 방법을 보여 줍니다. 확장 메서드를 사용 하면 축약 된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>참고 항목

- [컬렉션 이니셜라이저](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [방법: 컬렉션 이니셜라이저에 사용되는 컬렉션 만들기](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
