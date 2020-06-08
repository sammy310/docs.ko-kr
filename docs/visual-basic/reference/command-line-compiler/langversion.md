---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 271606ac021e6afcb28fdac3e1bc86e1aaba7d2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408540"
---
# <a name="-langversion-visual-basic"></a>-langversion(Visual Basic)
컴파일러에서 지정된 Visual Basic 언어 버전에 포함된 구문만 허용하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>인수  
 `version`  
 필수 요소. 컴파일하는 동안 사용할 언어 버전입니다. 허용되는 값은 `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` 및 `latest`입니다.

 `.0`를 부 버전으로 사용하여 전체 숫자를 지정할 수도 있습니다(예: `11.0`).

 명령줄에서 `-langversion:?`을 지정하면 가능한 모든 값의 목록을 볼 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `-langversion` 옵션은 컴파일러에서 허용하는 구문을 지정합니다. 예를 들어 언어 버전을 9.0으로 지정하면 컴파일러는 버전 10.0 이상에서만 유효한 구문에 대한 오류를 생성합니다.  
  
 다른 버전의 .NET Framework를 대상으로 하는 애플리케이션을 개발할 때 이 옵션을 사용할 수 있습니다. 예를 들어 .NET Framework 3.5를 대상으로 하는 경우 이 옵션을 사용하여 언어 버전 10.0의 구문을 사용하지 않도록 할 수 있습니다.  
  
 명령줄을 사용하여 `-langversion`을 직접 설정할 수 있습니다. 자세한 내용은 [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/visual-studio-multi-targeting-overview)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드는 Visual Basic 9.0에 대한 `sample.vb`를 컴파일합니다.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/visual-studio-multi-targeting-overview)
