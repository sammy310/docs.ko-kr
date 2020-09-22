---
title: "'<name>'에 적절한 시그니처가 있는 액세스 가능한 'Main' 메서드가 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6958e778701066760aa74e3b4d566800b7527b76
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871482"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>'\<name>'에 적절한 시그니처가 있는 액세스 가능한 'Main' 메서드가 없습니다.

명령줄 응용 프로그램에는가 정의 되어 있어야 합니다 `Sub Main` . `Main` 는 클래스에 정의 된 것 처럼 선언 `Public Shared` 하거나 모듈에 정의 된 것 처럼 선언 해야 합니다 `Public` .  
  
 **오류 ID:** BC30737  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `Public Sub Main`프로젝트에 대 한 프로시저를 정의 합니다. `Shared`클래스 내에서 정의 하는 경우에만이를 선언 합니다.  
  
## <a name="see-also"></a>참조

- [Visual Basic 프로그램의 구조](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [절차](../../programming-guide/language-features/procedures/index.md)
