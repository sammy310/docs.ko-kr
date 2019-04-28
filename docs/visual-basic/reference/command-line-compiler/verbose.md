---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796093"
---
# <a name="-verbose"></a>-verbose
컴파일러에서 상태 및 오류에 대 한 자세한 정보 표시 메시지를 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 지정 `-verbose` 지정 하는 것 같습니다 `-verbose+`는 컴파일러가을 자세한 정보 표시 메시지를 내보냅니다. 이 옵션의 기본값은 `-verbose-`합니다.  
  
## <a name="remarks"></a>설명  
 `-verbose` 옵션은 컴파일러에서 생성 한 오류의 총 수에 대 한 정보를 표시, 모듈에서 어셈블리를 로드 하는 보고 및 현재 컴파일 중인 파일을 표시 합니다.  
  
> [!NOTE]
>  `-verbose` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 받고 자세한 상태 정보를 표시 하도록 컴파일러에 지시 합니다.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
