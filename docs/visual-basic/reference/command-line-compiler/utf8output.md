---
description: '자세한 정보: -utf8output(Visual Basic)'
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 317c1be3f18150ae88bb8e95927d9f5faf0e4f3c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461894"
---
# <a name="-utf8output-visual-basic"></a>-utf8output(Visual Basic)

UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>인수  

 `+` &#124; `-`  
 선택 사항입니다. 이 옵션의 기본값은 `-utf8output-`입니다. 즉, 컴파일러 출력에서 UTF-8 인코딩을 사용하지 않습니다. `-utf8output`를 지정하는 것은 `-utf8output+`를 지정하는 것과 같습니다.  
  
## <a name="remarks"></a>설명  

 일부 국가별 구성에서는 컴파일러 출력이 콘솔에 올바르게 표시되지 않을 수 있습니다. 이러한 경우 `-utf8output`을 사용하여 컴파일러 출력을 파일로 리디렉션합니다.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-utf8output` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 코드는 `In.vb`를 컴파일하고 UTF-8 인코딩을 사용하여 출력을 표시하도록 컴파일러에 지시합니다.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
