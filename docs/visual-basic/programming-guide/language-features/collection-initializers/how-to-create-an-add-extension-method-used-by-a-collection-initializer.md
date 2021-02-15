---
description: '자세히 알아보기: 방법: 컬렉션 이니셜라이저에 사용 되는 추가 확장 메서드 만들기 (Visual Basic)'
title: '방법: 컬렉션 이니셜라이저에서 사용되는 확장 메서드 만들기 및 추가'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 1fbe6f438c4761ae668a6bd6a0a2c38c8efdb439
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475476"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>방법: 컬렉션 이니셜라이저에 사용되는 확장 추가 메서드 만들기(Visual Basic)

컬렉션 이니셜라이저를 사용 하 여 컬렉션을 만드는 경우 Visual Basic 컴파일러는 컬렉션 형식의 메서드를 검색 합니다 .이 메서드는 컬렉션의 `Add` 매개 변수가 `Add` 컬렉션 이니셜라이저의 값 형식과 일치 합니다. 이 메서드는 컬렉션을 `Add` 컬렉션 이니셜라이저의 값으로 채우는 데 사용 됩니다.  
  
 일치 하는 `Add` 메서드가 없고 컬렉션에 대 한 코드를 수정할 수 없는 경우 `Add` 컬렉션 이니셜라이저에 필요한 매개 변수를 사용 하는 라는 확장명 메서드를 추가할 수 있습니다. 일반적으로 제네릭 컬렉션에 대해 컬렉션 이니셜라이저를 사용할 때 수행 해야 하는 작업입니다.  
  
## <a name="example"></a>예  

 다음 예제에서는 <xref:System.Collections.Generic.List%601> 컬렉션 이니셜라이저를 사용 하 여 형식의 개체를 추가할 수 있도록 제네릭 형식에 확장 메서드를 추가 하는 방법을 보여 줍니다 `Employee` . 확장 메서드를 사용 하면 축약 된 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>추가 정보

- [컬렉션 이니셜라이저](index.md)
- [방법: 컬렉션 이니셜라이저에서 사용되는 컬렉션 만들기](how-to-create-a-collection-used-by-a-collection-initializer.md)
