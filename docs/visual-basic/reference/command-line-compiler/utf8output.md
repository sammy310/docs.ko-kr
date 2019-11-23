---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 5cdc60888cd872940afc1b03febd879bb6d87c2e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350834"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 (선택 사항) The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding. `-utf8output`를 지정하는 것은 `-utf8output+`를 지정하는 것과 같습니다.  
  
## <a name="remarks"></a>주의  
 In some international configurations, compiler output cannot be displayed correctly in the console. In such situations, use `-utf8output` and redirect compiler output to a file.  
  
> [!NOTE]
> The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.  
  
## <a name="example"></a>예제  
 The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
