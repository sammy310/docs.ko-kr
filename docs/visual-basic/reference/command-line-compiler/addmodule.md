---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2de5fe82f1969a2fdb305d45951d7d698252c0c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839224"
---
# <a name="-addmodule"></a>-addmodule
컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>인수  
 `fileList`  
 필수 요소. 메타 데이터를 포함 하지만 어셈블리 매니페스트를 포함 하지 않은 파일의 쉼표로 구분 된 목록입니다. 공백이 포함 된 파일 이름을 따옴표로 묶어야 ("").  
  
## <a name="remarks"></a>설명  
 나열 된 파일을 `fileList` 매개 변수를 사용 하 여 만들어야 합니다를 `-target:module` 옵션을 또는 다른 컴파일러의 동일 `-target:module`합니다.  
  
 사용 하 여 추가 된 모든 모듈 `-addmodule` 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다. 즉, 컴파일 타임에 모든 디렉터리의 모듈을 지정할 수 있지만 런타임에 모듈이 응용 프로그램 디렉터리 여야 합니다. 그렇지 않은 경우 표시는 <xref:System.TypeLoadException> 오류입니다.  
  
 (암시적 또는 명시적)을 지정 하면 모든[-대상 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) 이외의 옵션 `-target:module` 사용 하 여 `-addmodule`에 전달 되는 파일이 `-addmodule` 프로젝트의 어셈블리의 일부가 됩니다. 어셈블리에 있는 출력 파일을 실행 해야 합니다. 또는 더 많은 파일 추가 `-addmodule`합니다.  
  
 사용 하 여 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) 어셈블리가 포함 된 파일에서 메타 데이터를 가져오려고 합니다.  
  
> [!NOTE]
>  `-addmodule` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.  
  
## <a name="example"></a>예제  
 다음 코드는 모듈을 만듭니다.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 다음 코드는 모듈의 형식을 가져옵니다.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 실행할 때 `t1`, 출력 `802`합니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-참조 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
