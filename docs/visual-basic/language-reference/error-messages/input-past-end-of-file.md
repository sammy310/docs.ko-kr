---
title: 입력(값)이 파일의 끝을 넘습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873965"
---
# <a name="input-past-end-of-file"></a>입력(값)이 파일의 끝을 넘습니다.

`Input`비어 있거나 모든 데이터가 사용 되는 파일에서 문을 읽고 있거나 `EOF` 이진 액세스용으로 열린 파일에 함수를 사용 했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. `EOF`문 바로 앞에 함수를 사용 `Input` 하 여 파일의 끝을 검색 합니다.  
  
2. 이진 액세스용으로 파일을 연 경우 및를 사용 `Seek` `Loc` 합니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
