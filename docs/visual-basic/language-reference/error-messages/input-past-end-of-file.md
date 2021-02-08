---
description: '자세히 알아보기: 파일의 끝을 지난 입력'
title: 입력(값)이 파일의 끝을 넘습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: b65a57bdc56367518a93880be28781e56c9b99cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796043"
---
# <a name="input-past-end-of-file"></a>입력(값)이 파일의 끝을 넘습니다.

`Input`비어 있거나 모든 데이터가 사용 되는 파일에서 문을 읽고 있거나 `EOF` 이진 액세스용으로 열린 파일에 함수를 사용 했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. `EOF`문 바로 앞에 함수를 사용 `Input` 하 여 파일의 끝을 검색 합니다.  
  
2. 이진 액세스용으로 파일을 연 경우 및를 사용 `Seek` `Loc` 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
