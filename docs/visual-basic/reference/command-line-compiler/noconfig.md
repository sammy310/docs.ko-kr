---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964388"
---
# <a name="-noconfig"></a>-noconfig
컴파일러가 일반적으로 사용 되는 .NET Framework 어셈블리를 자동으로 참조 하지 않도록 지정 하거나 `System` 및 `Microsoft.VisualBasic` 네임 스페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>설명  
 옵션 `-noconfig` 은 vbc.exe 파일과 동일한 디렉터리에 있는 vbc.exe 파일을 사용 하 여 컴파일하지 않도록 컴파일러에 지시 합니다. Vbc.exe 파일은 일반적으로 사용 되는 .NET Framework 어셈블리를 참조 하 고 `System` 및 `Microsoft.VisualBasic` 네임 스페이스를 가져옵니다. `-nostdlib` 옵션이 지정 되지 않은 경우 컴파일러는 system.object 어셈블리를 암시적으로 참조 합니다. 옵션 `-nostdlib` 은 vbc.exe를 사용 하 여 컴파일하지 않도록 컴파일러에 지시 하거나 system.object 어셈블리를 자동으로 참조 합니다.  
  
> [!NOTE]
> Mscorlib.dll 및 Microsoft.visualbasic 어셈블리는 항상 참조 됩니다.  
  
 Vbc.rsp 파일을 수정 하 여 옵션을 `-noconfig` 지정 하는 경우를 제외 하 고 모든 vbc.exe 컴파일에 포함 되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다. 자세한 내용은 [@ (지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)을 참조하세요.  
  
 컴파일러는 마지막으로 `vbc` 명령에 전달 된 옵션을 처리 합니다. 따라서 명령줄의 모든 옵션은 Vbc.rsp 파일에 있는 동일한 옵션의 설정을 재정의 합니다.  
  
> [!NOTE]
> 이 `-noconfig` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [@(지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
