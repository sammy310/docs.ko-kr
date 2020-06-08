---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: 524660fca7c56fa490cc85169898bf2bf6d1a16e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400580"
---
# <a name="-optioninfer"></a>-optioninfer
변수 선언에서 지역 형식 유추를 사용하도록 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. 지역 형식 유추를 사용하도록 설정하려면 `-optioninfer+`를 지정하고, 차단하려면 `-optioninfer-`를 지정합니다. 값을 지정하지 않은 `-optioninfer` 옵션은 `-optioninfer+`와 같습니다. `-optioninfer` 스위치가 없을 때의 기본값도 `-optioninfer+`입니다. 기본값은 vbc.rsp 지시 파일에서 설정됩니다.|  
  
> [!NOTE]
> `-noconfig` 옵션을 사용하여 vbc.rsp에 지정된 값 대신 컴파일러의 내부 기본값을 유지할 수 있습니다. 이 옵션에 대한 컴파일러 기본값은 `-optioninfer-`입니다.  
  
## <a name="remarks"></a>설명  
 소스 코드 파일에 [Option Infer 문](../../language-reference/statements/option-infer-statement.md)이 포함되어 있는 경우 해당 명령문이 `-optioninfer` 명령줄 컴파일러 설정을 재정의합니다.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>Visual Studio IDE에서 -optioninfer를 설정하려면 다음을 수행합니다.  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2. **컴파일** 탭에서 **Option infer** 상자의 값을 수정합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 지역 형식 유추를 사용하도록 설정한 상태로 `test.vb`를 컴파일합니다.  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-optioncompare](optioncompare.md)
- [-optionexplicit](optionexplicit.md)
- [-optionstrict](optionstrict.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [Option Infer 문](../../language-reference/statements/option-infer-statement.md)
- [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)
- [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [-noconfig](noconfig.md)
- [명령줄에서 빌드](building-from-the-command-line.md)
