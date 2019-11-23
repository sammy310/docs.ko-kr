---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344770"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
조건부 컴파일러 상수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

or

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`symbol`|필수 요소. 정의할 기호입니다.|  
|`value`|(선택 사항) `symbol`을 할당할 값입니다. If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks. 값을 지정하지 않으면 True가 지정됩니다.|  
  
## <a name="remarks"></a>주의  
 The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.  
  
 이 옵션으로 만든 기호를 `#If`...`Then`...`#Else` 지시문과 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.  
  
 `-d`는 약식 `-define`입니다.  
  
 쉼표를 사용해 기호 정의를 구분하여 `-define`으로 여러 기호를 정의할 수 있습니다.  
  
|Visual Studio 통합 개발 환경에서 /define을 설정하려면|  
|---|  
|1.  Have a project selected in **Solution Explorer**. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  Click the **Compile** tab.<br />3.  Click **Advanced**.<br />4.  Modify the value in the **Custom Constants** box.|  
  
## <a name="example"></a>예제  
 다음 코드는 두 조건부 컴파일러 상수를 정의한 다음 사용합니다.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
