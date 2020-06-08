---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 75f3ee7f24112f911803732ccb8d39eeafa95e3d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400515"
---
# <a name="-out-visual-basic"></a>-out(Visual Basic)
출력 파일의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수 요소. 컴파일러에서 생성하는 출력 파일의 이름입니다. 파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.|  
  
## <a name="remarks"></a>설명  
 생성할 파일의 전체 이름과 확장명을 지정합니다. 이렇게 하지 않으면 .exe 파일은 `Sub Main` 프로시저를 포함하는 소스 코드 파일에서 해당 이름을 가져오고 .dll 파일은 첫 번째 소스 코드 파일에서 해당 이름을 가져옵니다.  
  
 .exe 또는 .dll 확장명 없이 파일 이름을 지정하면 `-target` 컴파일러 옵션에 지정된 값에 따라 컴파일러에서 자동으로 확장명을 추가합니다.  
  
|Visual Studio 통합 개발 환경에서 -out을 설정하려면 다음을 수행합니다.|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **애플리케이션** 탭을 클릭합니다.<br />3.  **어셈블리 이름** 상자에서 값을 수정합니다.|  
  
## <a name="example"></a>예제  
 다음 코드는 `T2.vb`를 컴파일하고 `T2.exe` 출력 파일을 만듭니다.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-target(Visual Basic)](target.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
