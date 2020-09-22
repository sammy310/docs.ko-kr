---
title: 파일 이름 또는 번호가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: d57a9e78e6ae179d3050e5a92399ca731fa16ba7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874900"
---
# <a name="bad-file-name-or-number"></a>파일 이름 또는 번호가 잘못되었습니다.

지정 된 파일에 액세스 하는 동안 오류가 발생 했습니다. 이 오류는 다음과 같은 경우에 발생할 수 있습니다.  
  
- 문이 문에 지정 되지 않았거나 `FileOpen` 문에 지정 되었지만 이후에 종결 된 파일 이름 또는 번호가 포함 된 파일을 참조 합니다 `FileOpen` .  
  
- 문이 파일 번호 범위를 벗어난 번호를 사용 하는 파일을 참조 합니다.  
  
- 문이 잘못 된 파일 이름 또는 번호를 참조 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 문에 파일 이름이 지정 되어 있는지 확인 `FileOpen` 합니다. `FileClose`인수 없이 문을 호출 하면 열려 있는 모든 파일이 실수로 닫혀 있을 수 있습니다.  
  
2. 코드에서 알고리즘 방식으로 파일 번호를 생성 하는 경우 번호가 올바른지 확인 합니다.  
  
3. 파일 이름을 확인 하 여 운영 체제 규칙을 준수 하는지 확인 합니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Visual Basic 명명 규칙](../../programming-guide/program-structure/naming-conventions.md)
