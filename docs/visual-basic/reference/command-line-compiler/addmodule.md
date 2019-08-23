---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 0e0915a2534f950cec074632a59750c3f96b679d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962453"
---
# <a name="-addmodule"></a>-addmodule
컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>인수  
 `fileList`  
 필수 요소. 메타 데이터를 포함 하지만 어셈블리 매니페스트를 포함 하지 않는 파일의 쉼표로 구분 된 목록입니다. 공백이 포함 된 파일 이름은 큰따옴표 ("")로 묶어야 합니다.  
  
## <a name="remarks"></a>설명  
 `fileList` 매개 변수를 `-target:module` 사용 하 여 나열 된 파일은 옵션을 사용 하거나와 동일한 `-target:module`다른 컴파일러의를 사용 하 여 만들어야 합니다.  
  
 로 추가 된 `-addmodule` 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다. 즉, 컴파일 시간에 모든 디렉터리에 모듈을 지정할 수 있지만 런타임에 모듈이 응용 프로그램 디렉터리에 있어야 합니다. 그렇지 <xref:System.TypeLoadException> 않으면 오류가 발생 합니다.  
  
 를 사용 하는 것과 `-addmodule`는 다르게 `-target:module` (암시적 또는 명시적으로)[대상 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) 옵션을 지정 하면에 전달 `-addmodule` 하는 파일이 프로젝트의 어셈블리에 포함 됩니다. 어셈블리는를 사용 하 여 `-addmodule`하나 이상의 파일이 추가 된 출력 파일을 실행 하는 데 필요 합니다.  
  
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) 를 사용 하 여 어셈블리를 포함 하는 파일에서 메타 데이터를 가져옵니다.  
  
> [!NOTE]
> 이 `-addmodule` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 모듈을 만듭니다.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 다음 코드에서는 모듈의 형식을 가져옵니다.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 을 실행 `t1`하면이 출력 `802`됩니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
