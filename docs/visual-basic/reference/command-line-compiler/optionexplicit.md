---
description: '자세한 정보: -optionexplicit'
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
ms.openlocfilehash: 4d1ab14bbf9de176de17fb5077f4bb919f5472b4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433564"
---
# <a name="-optionexplicit"></a>-optionexplicit

변수를 사용하기 전에 선언되지 않은 경우 컴파일러에서 오류를 보고합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>인수  

 `+` &#124; `-`  
 선택 사항입니다. 명시적 변수 선언이 필요하면 `-optionexplicit+`를 지정합니다. `-optionexplicit+` 옵션이 기본값이며 `-optionexplicit`와 동일합니다. `-optionexplicit-` 옵션을 사용하면 변수를 암시적으로 선언할 수 있습니다.  
  
## <a name="remarks"></a>설명  

 소스 코드 파일에 [Option Explicit 문](../../language-reference/statements/option-explicit-statement.md)이 포함되어 있으면 해당 명령문이 `-optionexplicit` 명령줄 컴파일러 설정을 재정의합니다.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Visual Studio IDE에서 -optionexplicit를 설정하려면 다음을 수행합니다.  
  
1. **솔루션 탐색기** 에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성** 을 클릭합니다.
  
2. **컴파일** 탭을 클릭합니다.  
  
3. **Option Explicit** 상자에서 값을 수정합니다.  
  
## <a name="example"></a>예제  

 다음 코드는 `-optionexplicit-`가 사용될 때 컴파일됩니다.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-optioncompare](optioncompare.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [Option Explicit 문](../../language-reference/statements/option-explicit-statement.md)
- [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
