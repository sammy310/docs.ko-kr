---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775631"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
이 모듈이 속할 어셈블리의 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`assembly_name`|이 모듈이 속할 어셈블리의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 컴파일러는 `-target:module` 옵션이 지정된 경우에만 `-moduleassemblyname` 옵션을 처리합니다. 이렇게 하면 컴파일러가 모듈을 만듭니다. 컴파일러에서 만든 모듈은 `-moduleassemblyname` 옵션으로 지정된 어셈블리에만 유효합니다. 모듈을 다른 어셈블리에 배치하면 런타임 오류가 발생합니다.  
  
 `-moduleassemblyname` 옵션은 다음 조건이 충족되는 경우에만 필요합니다.  
  
- 모듈의 데이터 형식에는 참조된 어셈블리의 `Friend` 형식에 대한 액세스 권한이 필요합니다.  
  
- 참조된 어셈블리는 모듈을 빌드할 어셈블리에 대한 friend 어셈블리 액세스 권한을 부여했습니다.  
  
 모듈 만들기에 대한 자세한 내용은 [-target(Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)을 참조하세요. friend 어셈블리에 대한 자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조하세요.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-moduleassemblyname` 옵션을 사용할 수 없습니다. 명령 프롬프트에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참조

- [방법: 다중 파일 어셈블리 빌드](../../../framework/app-domains/build-multifile-assembly.md)
- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target(Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-reference(Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [.NET 어셈블리](../../../standard/assembly/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Friend 어셈블리](../../../standard/assembly/friend.md)
