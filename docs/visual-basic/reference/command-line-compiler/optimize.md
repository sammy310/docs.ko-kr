---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: d4b50d56373676bf78a7591102095209401c907d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097594"
---
# <a name="-optimize"></a>-optimize

컴파일러 최적화를 사용하거나 사용하지 않도록 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. `-optimize-` 옵션은 컴파일러 최적화를 사용하지 않도록 설정합니다. `-optimize+` 옵션은 최적화를 사용하도록 설정합니다. 최적화는 기본적으로 사용되지 않습니다.|  
  
## <a name="remarks"></a>설명  

 컴파일러 최적화를 통해 더 작지만 빠르고 효율적인 출력 파일을 만듭니다. 그러나 최적화로 인해 출력 파일에서 코드가 재배열되기 때문에 `-optimize+`는 디버깅을 어렵게 만들 수 있습니다.  
  
 어셈블리에 대해 `-target:module`을 사용하여 생성된 모든 모듈은 어셈블리와 동일한 `-optimize` 설정을 사용해야 합니다. 자세한 내용은 [-target(Visual Basic)](target.md)을 참조하세요.  
  
 `-optimize` 및 `-debug` 옵션을 결합할 수 있습니다.  
  
|Visual Studio 통합 개발 환경에서 -optimize를 설정하려면 다음을 수행합니다.|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.<br />     <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  **최적화 사용** 확인란을 수정합니다.|  
  
## <a name="example"></a>예제  

 다음 코드는 `T2.vb`를 컴파일하고 컴파일러 최적화를 사용하도록 설정합니다.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-debug(Visual Basic)](debug.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [-target(Visual Basic)](target.md)
