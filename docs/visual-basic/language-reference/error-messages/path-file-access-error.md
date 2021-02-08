---
description: '자세한 정보: 경로/파일 액세스 오류'
title: 경로-파일 액세스 오류
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: d4fc7e716f025c0a482ab414f4a25a2b521634e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795445"
---
# <a name="pathfile-access-error"></a>경로/파일 액세스 오류입니다.

파일 액세스 또는 디스크 액세스 작업 중에 운영 체제에서 경로와 파일 이름 간에 연결을 설정할 수 없습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 파일 사양의 형식이 올바르게 지정 되었는지 확인 합니다. 파일 이름에는 정규화 된 절대 경로 또는 상대 경로를 사용할 수 있습니다. 정규화 된 경로는 드라이브 이름 (경로가 다른 드라이브에 있는 경우)으로 시작 하 여 루트에서 파일로의 명시적 경로를 나열 합니다. 정규화 되지 않은 경로는 현재 드라이브와 디렉터리에 대 한 상대 경로입니다.  
  
2. 기존 읽기 전용 파일을 대체 하는 파일을 저장 하려고 하지 않았는지 확인 합니다. 이 경우 대상 파일의 읽기 전용 특성을 변경 하거나 파일을 다른 파일 이름으로 저장 합니다.  
  
3. 읽기 전용 파일을 순차적 또는 모드로 열지 않았는지 확인 `Output` `Append` 합니다. 이 경우 모드에서 파일을 열거나 `Input` 파일의 읽기 전용 특성을 변경 합니다.  
  
4. 데이터베이스 또는 문서 내의 Visual Basic 프로젝트를 변경 하지 않았는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목

- [오류 유형](../../programming-guide/language-features/error-types.md)
