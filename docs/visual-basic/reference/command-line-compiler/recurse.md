---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2fe1834c3e92c3eff016ffd7857a0473eb2e8b3a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816423"
---
# <a name="-recurse"></a>-recurse
지정된 된 디렉터리 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>인수  
 `dir`  
 선택 사항입니다. 검색을 시작하려는 디렉터리입니다. 지정 하지 않으면 프로젝트 디렉터리에서 검색을 시작 합니다.  
  
 `file`  
 필수 요소. 검색할 파일입니다. 와일드카드 문자가 허용됩니다.  
  
## <a name="remarks"></a>설명  
 사용 하지 않고 프로젝트 디렉터리에서 일치 하는 모든 파일을 컴파일할 파일 이름에 와일드 카드를 사용할 수 있습니다 `-recurse`합니다. 출력 파일 이름은 없으므로 지정 하는 경우 컴파일러 처리 하는 첫 번째 입력된 파일에서 출력 파일 이름으로 계산 됩니다. 이 일반적으로 사전순으로 볼 때 컴파일된 파일 목록에서 첫 번째 파일입니다. 이러한 이유로 사용 하 여 출력 파일을 지정 하는 가장 좋은 것은 `-out` 옵션입니다.  
  
> [!NOTE]
>  `-recurse` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.  
  
## <a name="example"></a>예제  
 다음 명령은 현재 디렉터리에 모든 Visual Basic 파일을 컴파일합니다.  
  
```console
vbc *.vb  
```  
  
 다음 명령에서 모든 Visual Basic 파일을 컴파일하고 합니다 `Test\ABC` 디렉터리와 모든 디렉터리 아래 생성 `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
