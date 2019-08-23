---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937266"
---
# <a name="-verbose"></a>-verbose
컴파일러가 자세한 상태 및 오류 메시지를 생성 하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 를 지정 하는 것 `-verbose+` 은컴파일러가자세한정보메시지를내보내도록하는을지정하는것과같습니다.`-verbose` 이 옵션 `-verbose-`의 기본값은입니다.  
  
## <a name="remarks"></a>설명  
 옵션 `-verbose` 은 컴파일러에서 발생 한 총 오류 수에 대 한 정보를 표시 하 고, 모듈에서 로드 되는 어셈블리를 보고 하 고, 현재 컴파일되는 파일을 표시 합니다.  
  
> [!NOTE]
> 이 `-verbose` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 자세한 `In.vb` 상태 정보를 표시 하도록 컴파일러를 컴파일하고 지시 합니다.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
