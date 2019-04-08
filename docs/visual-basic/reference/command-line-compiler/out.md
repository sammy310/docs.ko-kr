---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 5dcf9dc5cc0987e965aba7fd2b8821252e19a655
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815994"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
출력 파일의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. 컴파일러 출력 파일의 이름을 만듭니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").|  
  
## <a name="remarks"></a>설명  
 전체 이름 및 만들 파일의 확장명을 지정 합니다. .Exe 파일을 포함 하는 소스 코드 파일에서 해당 이름을 이렇게 하지 않으면 경우는 `Sub Main` 프로시저 및.dll 파일에서 첫 번째 소스 코드 파일의 이름을 가져옵니다.  
  
 .Exe 또는.dll 확장명 없이 파일 이름을 지정 하는 경우 컴파일러가 자동으로 추가 확장, 지정 된 값에 따라는 `-target` 컴파일러 옵션입니다.  
  
|확장은 Visual Studio 통합된 개발 환경에서 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  값을 수정 합니다 **어셈블리 이름** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드 컴파일을 `T2.vb` 출력 파일을 만들고 `T2.exe`합니다.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
