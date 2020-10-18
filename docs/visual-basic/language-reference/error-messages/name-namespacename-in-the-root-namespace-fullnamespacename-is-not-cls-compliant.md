---
title: 루트 네임스페이스 <namespacename>의 이름 <fullnamespacename>이(가) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 48e020cb74641279a4f402e47034514d78dfc4fc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160212"
---
# <a name="bc40039-name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a>BC40039: \<namespacename> 루트 네임 스페이스의 이름이 \<fullnamespacename> CLS 규격이 아닙니다.

어셈블리가로 표시 `<CLSCompliant(True)>` 되지만 루트 네임 스페이스 이름의 요소는 밑줄 ()로 시작 `_` 합니다.

 프로그래밍 요소는 하나 이상의 밑줄을 포함할 수 있지만 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)를 준수 하려면 밑줄로 시작 하지 않아야 합니다. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.

 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.

 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC40039

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- CLS 규격이 필요한 경우 해당 요소가 밑줄로 시작 하지 않도록 루트 네임 스페이스 이름을 변경 합니다.

- 네임 스페이스 이름이 변경 되지 않은 상태로 유지 되어야 하는 경우 <xref:System.CLSCompliantAttribute> 어셈블리에서를 제거 하거나로 표시 합니다 `<CLSCompliant(False)>` .

## <a name="see-also"></a>참고 항목

- [Namespace 문](../statements/namespace-statement.md)
- [Visual Basic의 네임스페이스](../../programming-guide/program-structure/namespaces.md)
- [-rootnamespace](../../reference/command-line-compiler/rootnamespace.md)
- [프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Visual Basic 명명 규칙](../../programming-guide/program-structure/naming-conventions.md)
