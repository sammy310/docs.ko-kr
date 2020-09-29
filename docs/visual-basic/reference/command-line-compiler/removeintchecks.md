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
ms.openlocfilehash: ce1f24f25ea58cb6ddc2f5c582b6103d8f18d922
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085167"
---
# <a name="-removeintchecks"></a>-removeintchecks

정수 연산에 대해 오버플로 오류 검사를 설정하거나 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. `-removeintchecks-` 옵션을 사용하면 컴파일러에서 오버플로 오류에 대한 모든 정수 계산을 검사할 수 있습니다. 기본값은 `-removeintchecks-`입니다.<br /><br /> `-removeintchecks` 또는 `-removeintchecks+`를 지정하면 오류 검사를 방지하고 정수 계산을 더 빠르게 수행할 수 있습니다. 그러나 오류 검사를 수행하지 않고 데이터 형식 용량이 오버플로되는 경우 오류 발생 없이도 잘못된 결과가 저장될 수 있습니다.|  
  
|Visual Studio 통합 개발 환경에서 -removeintchecks를 설정하려면 다음을 수행합니다.|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  **정수 오버플로 검사 해제** 상자의 값을 수정합니다.|  
  
## <a name="example"></a>예제  

 다음 코드는 `Test.vb`를 컴파일하고 정수 오버플로 오류 검사를 해제합니다.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
