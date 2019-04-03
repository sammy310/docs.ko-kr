---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822728"
---
# <a name="-removeintchecks"></a>-removeintchecks
오버플로 오류 또는 해제 하는 정수 연산에 대 한 검사를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. `-removeintchecks-` 옵션을 사용 하면 모든 정수 연산 오버플로 오류를 확인 합니다. 기본값은 `-removeintchecks-`입니다.<br /><br /> 지정 `-removeintchecks` 또는 `-removeintchecks+` 오류 검사를 차단 하 고 정수 계산을 더욱 빠르게 만들 수 있습니다. 오류를 검사 하지 않는 반면 및 잘못 된 결과 데이터 형식 용량 오버플로 경우 오류를 일으키지 않고 저장 될 수 있습니다.|  
  
|Visual Studio 통합된 개발 환경에서-removeintchecks를 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  값을 수정 합니다 **정수 오버플로 검사 해제** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Test.vb` 정수 오버플로 오류 검사를 해제 합니다.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
