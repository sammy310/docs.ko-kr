---
title: 대리자에서 형식 인수를 유추할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 1024cf6f2c1fa112db29cb710eef190a5022d3af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838601"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>대리자에서 형식 인수를 유추할 수 없습니다.
대입문이 `AddressOf` 를 사용하여 제네릭 프로시저의 주소를 대리자에게 할당하지만 형식 인수를 제네릭 프로시저에 제공하지 않습니다.  
  
 일반적으로 제네릭 형식을 호출하는 경우 제네릭 형식이 정의하는 각 형식 매개 변수에 대해 형식 인수를 제공합니다. 형식 인수를 제공하지 않으면 컴파일러에서 형식 매개 변수에 전달될 형식을 유추하려고 합니다. 컨텍스트에서 컴파일러가 형식을 유추하도록 정보를 충분히 제공하지 않으면 오류가 생성됩니다.  
  
 **오류 ID:** BC36564  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   `AddressOf` 식에서 제네릭 프로시저에 대한 형식 인수를 지정합니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)
- [확장명 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
