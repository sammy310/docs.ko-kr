---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839725"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
컴파일러가 지정된 된 Visual Basic 언어 버전에 포함 된 구문만 허용 하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>인수  
 `version`  
 필수 요소. 컴파일하는 동안 사용할 언어 버전입니다. 허용 되는 값은 `9`, `10`, `11`, `12`, `14`를 `15`, `15.3`를 `15.5`를 `default` 및 `latest`합니다.

 전체 숫자 하나라도 지정할 수 있습니다 사용 하 여 `.0` 부 버전, 예를 들어 `11.0`합니다.

 모든 가능한 값 목록을 지정 하 여 보이는 `-langversion:?` 명령줄에서.  
  
## <a name="remarks"></a>설명  
 `-langversion` 옵션 컴파일러에서는 허용 되는 구문을 지정 합니다. 예를 들어 언어 버전 9.0 인지를 지정 하면 컴파일러 이상 10.0 버전에만 유효는 구문에 대 한 오류를 생성 합니다.  
  
 해당 대상 다른 버전의.NET Framework 응용 프로그램을 개발 하는 경우이 옵션을 사용할 수 있습니다. 예를 들어,.NET Framework 3.5를 대상으로 하는 경우 언어 버전 10.0에서에서 구문을 사용 하는지 확인 하려면이 옵션을 사용할 수 있습니다.  
  
 설정할 수 있습니다 `-langversion` 직접 명령줄을 사용 해야만 합니다. 자세한 내용은 [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `sample.vb` Visual Basic 9.0에 대 한 합니다.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
