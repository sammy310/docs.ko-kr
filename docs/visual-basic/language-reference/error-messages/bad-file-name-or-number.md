---
title: 파일 이름 또는 번호가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322162"
---
# <a name="bad-file-name-or-number"></a>파일 이름 또는 번호가 잘못되었습니다.
지정한 파일에 액세스 하는 동안 오류가 발생 했습니다. 이 오류에 대 한 가능한 원인 중:  
  
-   문에서 참조에서 지정 되지 않은 파일 이름 또는 번호를 사용 하 여 파일에는 `FileOpen` 문이나는에 지정 된을 `FileOpen` 문을 하지만 이후에 닫힙니다.  
  
-   문이 파일 번호의 범위를 벗어난 숫자로 파일을 참조 합니다.  
  
-   문에 파일 이름 또는 유효 하지 않은 숫자를 가리킵니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 파일 이름에 지정 해야는 `FileOpen` 문입니다. 호출 하는 경우는 `FileClose` 문 인수 없이 있습니다 닫힐 수 열려 있는 모든 파일입니다.  
  
2. 코드를 생성할 경우 파일 번호 알고리즘 방식으로 숫자 올바른지 확인 합니다.  
  
3. 운영 체제 규칙을 준수 하는지 확인 하려면 파일 이름을 확인 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
