---
title: XML 주석 예외에는 'cref' 특성이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 18e7aa5f6905eaa9c509aa21fe6f5bfcd54d46f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163300"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a>BC42319: XML 주석 예외에는 ' cref ' 특성이 있어야 합니다.

\<exception>태그는 메서드에 의해 throw 될 수 있는 예외를 문서화 하는 방법을 제공 합니다. Required `cref` 특성은 문서 생성기에 의해 확인 되는 멤버의 이름을 지정 합니다. 멤버가 있으면 설명서 파일의 정식 요소 이름으로 변환 됩니다.

**오류 ID:** BC42319

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

다음과 `cref` 같이 예외에 특성을 추가 합니다.

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>참고 항목

- [\<exception>](../xmldoc/exception.md)
- [방법: XML 설명서 만들기](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML 주석 태그](../xmldoc/index.md)
