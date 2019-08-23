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
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929481"
---
# <a name="-filealign"></a>-filealign
출력 파일의 섹션에 맞출 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>인수  
 `number`  
 필수 요소. 출력 파일에 있는 섹션의 맞춤을 지정 하는 값입니다. 유효한 값은 512, 1024, 2048, 4096 및 8192입니다. 이러한 값은 바이트 단위입니다.  
  
## <a name="remarks"></a>설명  
 `-filealign` 옵션을 사용 하 여 출력 파일의 섹션 맞춤을 지정할 수 있습니다. 섹션은 코드 또는 데이터를 포함 하는 PE (이식 가능한 실행) 파일의 연속 메모리 블록입니다. 옵션 `-filealign` 을 사용 하면 비표준 맞춤을 사용 하 여 응용 프로그램을 컴파일할 수 있습니다. 대부분의 개발자는이 옵션을 사용할 필요가 없습니다.  
  
 각 섹션은 `-filealign` 값의 배수가 되는 경계에 정렬 됩니다. 고정된 기본값이 없습니다. 을 `-filealign` 지정 하지 않으면 컴파일러가 컴파일 시간에 기본값을 선택 합니다.  
  
 섹션 크기를 지정 하 여 출력 파일의 크기를 변경할 수 있습니다. 섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다.  
  
> [!NOTE]
> 이 `-filealign` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
