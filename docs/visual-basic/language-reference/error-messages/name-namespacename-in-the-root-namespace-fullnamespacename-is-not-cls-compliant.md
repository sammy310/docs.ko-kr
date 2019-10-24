---
title: 루트 네임스페이스 <namespacename>의 이름 <fullnamespacename>이(가) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 821044d3ee359a052fa6a763e9c5a89da5d6f607
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775577"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a>루트 네임 스페이스 > \<fullnamespacename \<namespacename > 이름이 CLS 규격이 아닙니다.
어셈블리가 `<CLSCompliant(True)>`로 표시 되어 있지만 루트 네임 스페이스 이름의 요소가 밑줄 (`_`)로 시작 합니다.  
  
 프로그래밍 요소는 하나 이상의 밑줄을 포함할 수 있지만 [언어 독립성 및 CLS (언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) )를 준수 하려면 밑줄로 시작 하지 않아야 합니다. [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.  
  
 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)를 참조하세요.  
  
 **오류 ID:** BC40039  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- CLS 규격이 필요한 경우 해당 요소가 밑줄로 시작 하지 않도록 루트 네임 스페이스 이름을 변경 합니다.  
  
- 네임 스페이스 이름이 변경 되지 않은 상태로 유지 되어야 하는 경우 어셈블리에서 <xref:System.CLSCompliantAttribute>를 제거 하거나 `<CLSCompliant(False)>`으로 표시 합니다.  
  
## <a name="see-also"></a>참조

- [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Visual Basic 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [-rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
