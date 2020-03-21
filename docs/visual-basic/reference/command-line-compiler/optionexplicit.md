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
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266731"
---
# <a name="-optionexplicit"></a>-optionexplicit
변수를 사용 하기 전에 선언 되지 않은 경우 컴파일러 오류를 보고 합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 (선택 사항) 변수의 명시적 선언을 요구하도록 지정합니다. `-optionexplicit+` 이 `-optionexplicit+` 옵션은 기본값이며 `-optionexplicit`. 이 `-optionexplicit-` 옵션을 사용하면 변수의 암시적 선언이 가능합니다.  
  
## <a name="remarks"></a>설명  
 소스 코드 파일에 [Option Explicit 문이](../../../visual-basic/language-reference/statements/option-explicit-statement.md)포함된 경우 `-optionexplicit` 문은 명령줄 컴파일러 설정을 재정의합니다.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>비주얼 스튜디오 IDE에서 -optionexplicit를 설정하려면  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.
  
2. **컴파일** 탭을 클릭합니다.  
  
3. **옵션 명시적** 상자의 값을 수정합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 사용될 `-optionexplicit-` 때 컴파일됩니다.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-옵션 비교](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-옵션 스밀](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [- 옵션 인퍼](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [옵션 대화 상자, 프로젝트, VB 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
