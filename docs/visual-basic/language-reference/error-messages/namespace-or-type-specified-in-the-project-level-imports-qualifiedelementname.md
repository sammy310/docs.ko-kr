---
title: 프로젝트 수준의 Imports '<qualifiedelementname>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: e0be18509d0d4b1b4f5eadfadce7a0785e9309f0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871510"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>프로젝트 수준의 Imports '\<qualifiedelementname>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.

프로젝트 수준의 Imports ' '에 지정 된 네임 스페이스 또는 형식에 \<qualifiedelementname> public 멤버가 없거나 해당 네임 스페이스를 찾을 수 없습니다. 네임 스페이스 또는 형식이 정의 되어 있고 하나 이상의 public 멤버를 포함 하는지 확인 합니다. 별칭 이름이 다른 별칭을 포함 하지 않는지 확인 합니다.  
  
 프로젝트의 가져오기 속성은 찾을 수 없거나 멤버를 정의 하지 않는 포함 하는 요소를 지정 합니다 `Public` .  
  
 *포함 하는 요소* 는 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다. 포함 하는 요소에는 변수, 프로시저 또는 포함 하는 다른 요소와 같은 멤버가 포함 됩니다.  
  
 가져오기의 목적은 코드에서 한정 하지 않고 네임 스페이스 또는 형식 멤버에 액세스할 수 있도록 하는 것입니다. 프로젝트에서 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다. 자세한 내용은 [선언 된 요소에](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)대 한 참조에서 "포함 하는 요소 가져오기"를 참조 하세요.  
  
 컴파일러가 지정 된 포함 요소를 찾을 수 없는 경우 해당 요소를 사용 하는 참조를 확인할 수 없습니다. 요소를 찾았지만 요소가 멤버를 노출 하지 않는 경우에는 `Public` 참조가 실패할 수 있습니다. 두 경우 모두 요소를 가져오는 것은 의미가 없습니다.  
  
 **프로젝트 디자이너** 를 사용 하 여 가져올 요소를 지정할 수 있습니다. **참조** 페이지의 **가져온 네임 스페이스** 섹션을 사용 합니다. **솔루션 탐색기**에서 **내 프로젝트** 아이콘을 두 번 클릭 하 여 **프로젝트 디자이너** 에 액세스할 수 있습니다.  
  
 **오류 ID:** BC40057  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. **프로젝트 디자이너** 를 열고 **참조** 페이지로 전환 합니다.  
  
2. **가져온 네임 스페이스** 섹션에서 포함 하는 요소를 프로젝트에서 액세스할 수 있는지 확인 합니다.  
  
3. 포함 하는 요소가 하나 이상의 멤버를 노출 하는지 확인 합니다 `Public` .  
  
## <a name="see-also"></a>참조

- [참조 페이지, 프로젝트 디자이너(Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)
- [공용](../modifiers/public.md)
- [Visual Basic의 네임스페이스](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
