---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005439"
---
# <a name="-noconfig"></a>-noconfig
컴파일러가 일반적으로 사용되는 .NET Framework 어셈블리를 자동으로 참조하지 않도록 하거나 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져오지 않도록 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>설명  
 `-noconfig` 옵션은 Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일로 컴파일하지 않도록 컴파일러에 지시합니다. Vbc.rsp 파일은 일반적으로 사용되는 .NET Framework 어셈블리를 참조하고 `System` 및 `Microsoft.VisualBasic` 네임스페이스를 가져옵니다. 컴파일러는 `-nostdlib` 옵션이 지정되지 않는 한 System.dll 어셈블리를 암시적으로 참조합니다. `-nostdlib` 옵션은 Vbc.rsp를 사용하여 컴파일하지 않도록 하거나 System.dll 어셈블리를 자동으로 참조하지 않도록 컴파일러에 지시합니다.  
  
> [!NOTE]
> Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조됩니다.  
  
 Vbc.rsp 파일을 수정하여 모든 Vbc.exe 컴파일에 포함되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다(`-noconfig` 옵션을 지정할 경우 제외). 자세한 내용은 [@ (지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)을 참조하세요.  
  
 컴파일러는 `vbc` 명령에 마지막으로 전달된 옵션을 처리합니다. 따라서 명령줄의 모든 옵션은 Vbc.rsp 파일에 있는 동일한 옵션의 설정을 재정의합니다.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-noconfig` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참조

- [-nostdlib(Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [@(지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-reference(Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
