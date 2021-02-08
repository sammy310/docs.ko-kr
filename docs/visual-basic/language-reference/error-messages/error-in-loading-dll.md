---
description: '자세한 정보: DLL을 로드 하는 동안 오류 발생 (Visual Basic)'
title: DLL을 로드하는 동안 오류가 발생했습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 098d05e93d328f3667000bd81290f4b77cf7949e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796511"
---
# <a name="error-in-loading-dll-visual-basic"></a>DLL을 로드하는 동안 오류가 발생했습니다(Visual Basic).

DLL (동적 연결 라이브러리)은 문의 절에 지정 된 라이브러리입니다 `Lib` `Declare` . 이 오류의 가능한 원인은 다음과 같습니다.  
  
- 파일이 DLL 실행 파일이 아닙니다.  
  
- 파일이 Microsoft Windows DLL이 아닙니다.  
  
- DLL이 존재 하지 않는 다른 DLL을 참조 합니다.  
  
- DLL 또는 참조 된 DLL이 경로에 지정 된 디렉터리에 없습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 파일이 원본 텍스트 파일 이며 DLL 실행 파일이 아닌 경우이 파일을 컴파일하여 DLL 실행 파일 폼에 연결 해야 합니다.  
  
- 파일이 Microsoft Windows DLL이 아닌 경우에는 Microsoft Windows를 가져옵니다.  
  
- DLL이 존재 하지 않는 다른 DLL을 참조 하는 경우 참조 된 DLL을 가져와 사용 가능 하 게 설정 합니다.  
  
- DLL 또는 참조 DLL이 경로에 지정 된 디렉터리에 없으면 DLL을 참조 된 디렉터리로 이동 합니다.  
  
## <a name="see-also"></a>참고 항목

- [Declare 문](../statements/declare-statement.md)
