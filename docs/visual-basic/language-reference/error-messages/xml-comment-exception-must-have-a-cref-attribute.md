---
title: XML 주석 예외에는 'cref' 특성이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321167"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>XML 주석 예외에는 'cref' 특성이 있어야 합니다.

@No__t_0exception > 태그는 메서드에 의해 throw 될 수 있는 예외를 문서화 하는 방법을 제공 합니다. 필수 `cref` 특성은 문서 생성기에 의해 확인 되는 멤버의 이름을 지정 합니다. 멤버가 있으면 설명서 파일의 정식 요소 이름으로 변환 됩니다.

**오류 ID:** BC42319

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

다음과 같이 `cref` 특성을 예외에 추가 합니다.

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>참조

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
