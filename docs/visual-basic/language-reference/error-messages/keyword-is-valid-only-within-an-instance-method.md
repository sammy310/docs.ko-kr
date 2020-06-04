---
title: "'<keyword>'은(는) 인스턴스 메서드 안에서만 사용할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 537689405ea30bdd7c075320eba58a8723a93cdb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397404"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<keyword>'은(는) 인스턴스 메서드 안에서만 사용할 수 있습니다.
`Me`, `MyClass` 및 키워드는 `MyBase` 특정 클래스 인스턴스를 참조 합니다. 공유 또는 프로시저 내에서는 사용할 수 `Function` 없습니다 `Sub` .  
  
 **오류 ID:** BC30043  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 프로시저에서 키워드를 제거 하거나 `Shared` 프로시저 선언에서 키워드를 제거 합니다.  
  
## <a name="see-also"></a>참고 항목

- [개체 변수 할당](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase 및 MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
