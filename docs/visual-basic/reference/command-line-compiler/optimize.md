---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: eb84e0a7038e7ff8cb399ac7222b6ac1661b5bc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842163"
---
# <a name="-optimize"></a>-optimize
사용 하거나 컴파일러 최적화를 사용 하지 않도록 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. `-optimize-` 옵션 컴파일러 최적화를 사용 하지 않도록 설정 합니다. `-optimize+` 옵션 최적화할 수 있습니다. 최적화는 기본적으로 사용되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 컴파일러 최적화를 통해 더 작지만 빠르고 효율적인 출력 파일을 만듭니다. 그러나 최적화로 인해 출력 파일에서 코드가 다시 정렬 되기 때문에, `-optimize+` 디버깅이 어려워질 수 있습니다.  
  
 사용 하 여 생성 된 모든 모듈 `-target:module` 어셈블리는 동일한 사용 해야 합니다 `-optimize` 어셈블리로 설정 합니다. 자세한 내용은 [-대상 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)합니다.  
  
 결합할 수 있습니다 합니다 `-optimize` 고 `-debug` 옵션입니다.  
  
|Visual Studio 통합된 개발 환경 설정-최적화|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.<br />     <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  수정 된 **최적화를 사용 하도록 설정** 확인란 합니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 컴파일러 최적화를 사용 하 고 있습니다.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-디버그 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
