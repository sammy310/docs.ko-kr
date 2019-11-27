---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352383"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)
출력 파일의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`filename`|필수입니다. 컴파일러가 만드는 출력 파일의 이름입니다. 파일 이름에 공백이 포함 된 경우 이름을 큰따옴표 ("")로 묶습니다.|  
  
## <a name="remarks"></a>주의  
 만들 파일의 전체 이름 및 확장명을 지정 합니다. 이렇게 하지 않으면 .exe 파일은 `Sub Main` 프로시저를 포함 하는 소스 코드 파일에서 해당 이름을 사용 하 고 .dll 파일은 첫 번째 소스 코드 파일에서 해당 이름을 가져옵니다.  
  
 .Exe 또는 .dll 확장명 없이 파일 이름을 지정 하는 경우 컴파일러는 `-target` 컴파일러 옵션에 지정 된 값에 따라 자동으로 확장을 추가 합니다.  
  
|Visual Studio 통합 개발 환경에서 설정 하려면|  
|---|  
|1. **솔루션 탐색기**에서 프로젝트를 선택 합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **애플리케이션** 탭을 클릭합니다.<br />3. **어셈블리 이름** 상자에서 값을 수정 합니다.|  
  
## <a name="example"></a>예제  
 다음 코드는 `T2.vb`를 컴파일하고 `T2.exe`출력 파일을 만듭니다.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
