---
description: '자세한 정보: -addmodule'
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: ca08aa599003897e680240af21c4a0eb568e31d8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468293"
---
# <a name="-addmodule"></a>-addmodule

컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>인수  

 `fileList`  
 필수 요소. 메타데이터를 포함하지만 어셈블리 매니페스트를 포함하지 않는 파일의 쉼표로 구분된 목록입니다. 공백이 포함된 파일 이름은 따옴표("")로 묶어야 합니다.  
  
## <a name="remarks"></a>설명  

 `fileList` 매개 변수로 나열되는 파일은 `-target:module` 옵션 또는 다른 컴파일러의 `-target:module`와 동등한 옵션을 사용하여 만들어야 합니다.  
  
 `-addmodule`을 사용하여 추가된 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다. 즉, 컴파일 시간에 임의 디렉터리에 있는 모듈을 지정할 수 있지만 런타임에 모듈이 애플리케이션 디렉터리에 있어야 합니다. 그렇지 않으면 <xref:System.TypeLoadException> 오류가 발생합니다.  
  
 `-addmodule`과 함께 `-target:module`이 아닌 [-target(Visual Basic)](target.md) 옵션을 암시적 또는 명시적으로 지정하는 경우 `-addmodule`에 전달하는 파일이 프로젝트 어셈블리의 일부가 됩니다. `-addmodule`을 사용하여 추가된 파일이 하나 이상 있는 출력 파일을 실행하려면 어셈블리가 필요합니다.  
  
 [-reference (Visual Basic)](reference.md)를 사용하여 어셈블리를 포함하는 파일에서 메타데이터를 가져옵니다.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-addmodule` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 코드에서는 모듈을 만듭니다.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 다음 코드에서는 모듈의 형식을 가져옵니다.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 `t1`을 실행하면 `802`를 출력합니다.  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-target(Visual Basic)](target.md)
- [-reference(Visual Basic)](reference.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
