---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: d146f5967058b05795026cd7726ed5eda7ba3153
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095410"
---
# <a name="-win32resource"></a>-win32resource

Win32 리소스 파일을 출력 파일에 삽입합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a>인수  

 `filename`  
 출력 파일에 추가할 리소스 파일의 이름입니다. 공백이 있으면 파일 이름을 따옴표(" ")로 묶습니다.  
  
## <a name="remarks"></a>설명  

 Microsoft Windows RC(리소스 컴파일러)를 사용하여 Win32 리소스 파일을 만들 수 있습니다.  
  
 Win32 리소스는 **파일 탐색기**에서 애플리케이션을 식별하는 데 도움이 되는 버전 정보나 비트맵(아이콘) 정보를 포함할 수 있습니다. `-win32resource`를 지정하지 않으면 컴파일러에서 어셈블리 버전을 기반으로 버전 정보를 생성합니다. `-win32resource` 및 `-win32icon` 옵션은 함께 사용할 수 없습니다.  
  
 .NET Framework 리소스 파일 또는 [-resource (Visual Basic)](resource.md)를 참조하여 .NET Framework 리소스 파일을 연결하려면 [-linkresource(Visual Basic)](linkresource.md)를 참조하세요.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-win32resource` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 코드에서는 `In.vb`를 컴파일하고 Win32 리소스 파일 `Rf.res`를 연결합니다.  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
