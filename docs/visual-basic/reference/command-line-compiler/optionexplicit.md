---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 54d438541e8840e4394b24b20b4f394ff8cdb820
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332393"
---
# <a name="-optionexplicit"></a>-optionexplicit
컴파일러에서 오류를 보고 사용 하기 전에 선언 되지 않은 경우.  
  
## <a name="syntax"></a>구문  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 지정 `-optionexplicit+` 변수의 명시적 선언이 필요 합니다. 합니다 `-optionexplicit+` 옵션은 기본값 이므로 같습니다 `-optionexplicit`합니다. `-optionexplicit-` 암시적 변수 선언을 수 있도록 해줍니다.  
  
## <a name="remarks"></a>설명  
 소스 코드 파일을 포함 하는 경우는 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md), 문이 재정의 `-optionexplicit` 명령줄 컴파일러 설정을 사용 합니다.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>-Optionexplicit Visual Studio IDE에서 설정 하려면  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.   
  
2. **컴파일** 탭을 클릭합니다.  
  
3. 값을 수정 합니다 **Option Explicit** 상자입니다.  
  
## <a name="example"></a>예제  
 다음 코드는 경우 `-optionexplicit-` 사용 됩니다.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [옵션 대화 상자, 프로젝트, VB 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
