---
title: XML 주석 예외에는 'cref' 특성이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a974df5d2305b88946981d0d258a8088b23d3fc3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813290"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>XML 주석 예외에는 'cref' 특성이 있어야 합니다.
\<예외 > 태그는 메서드에서 throw 될 수 있는 예외를 문서화 하는 방법을 제공 합니다. 필수 `cref` 특성 설명서 생성기에서 확인 하는 멤버의 이름을 지정 합니다. 멤버가 있는 경우 문서 파일의 정식 요소 이름으로 변환 됩니다.  
  
 **오류 ID:** BC42319  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   추가 된 `cref` 예외에 특성을 다음과 같이 합니다.  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>참고자료

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md)
