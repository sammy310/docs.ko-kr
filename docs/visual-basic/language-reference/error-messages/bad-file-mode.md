---
description: '자세한 정보: 잘못 된 파일 모드'
title: 파일 모드가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: da792407fb37f5c206be7ff39da14d314ef1e2d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797083"
---
# <a name="bad-file-mode"></a>파일 모드가 잘못되었습니다.

파일 콘텐츠를 조작 하는 데 사용 되는 문은 파일이 열린 모드에 적절 해야 합니다. 가능한 원인은 다음과 같습니다.  
  
- `FilePutObject`또는 `FileGetObject` 문에서 순차 파일을 지정 합니다.  
  
- `Print`문이 또는 이외의 액세스 모드로 열린 파일을 지정 합니다 `Output` `Append` .  
  
- `Input`문이 다음 이외의 액세스 모드로 열린 파일을 지정 합니다.`Input`  
  
- 읽기 전용 파일에 쓰려고 했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `FilePutObject`및 `FileGetObject` 에 대해 열려 있는 파일만 참조 하는지 확인 `Random` `Binary` 합니다.  
  
- `Print` `Output` 또는 액세스 모드에 대해 열려 있는 파일을 지정 해야 합니다 `Append` . 그렇지 않으면 다른 문을 사용 하 여 데이터를 파일에 저장 하거나 적절 한 모드로 파일을 다시 엽니다.  
  
- `Input`에 대해 열려 있는 파일을 지정 해야 합니다 `Input` . 그렇지 않으면 다른 문을 사용 하 여 데이터를 파일에 저장 하거나 적절 한 모드로 파일을 다시 엽니다.  
  
- 읽기 전용 파일에 쓰는 경우 파일의 읽기/쓰기 상태를 변경 하거나 파일에 쓰지 않습니다.  
  
- `My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.FileSystem>
- [문제 해결: 텍스트 파일 읽기 및 쓰기](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
