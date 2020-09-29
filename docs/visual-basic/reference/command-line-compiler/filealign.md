---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 809b7ad005b6bb5f127f84425b5d2beb980df471
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058133"
---
# <a name="-filealign"></a>-filealign

출력 파일의 섹션에 맞출 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>인수  

 `number`  
 필수 요소. 출력 파일에 있는 섹션의 맞춤을 지정하는 값입니다. 유효한 값은 512, 1024, 2048, 4096 및 8192입니다. 이러한 값은 바이트 단위입니다.  
  
## <a name="remarks"></a>설명  

 `-filealign` 옵션을 사용하여 출력 파일에 있는 섹션의 맞춤을 지정할 수 있습니다. 섹션은 코드 또는 데이터를 포함하는 PE(이식 가능한 실행) 파일의 연속 메모리 블록입니다. `-filealign` 옵션을 사용하면 비표준 맞춤을 통해 애플리케이션을 컴파일할 수 있습니다. 대부분의 개발자는 이 옵션을 사용할 필요가 없습니다.  
  
 각 섹션은 `-filealign` 값의 배수인 경계에 맞춰집니다. 고정된 기본값이 없습니다. `-filealign`을 지정하지 않으면 컴파일러는 컴파일 시간에 기본값을 선택합니다.  
  
 섹션 크기를 지정하여 출력 파일의 크기에 변경할 수 있습니다. 섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-filealign` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
