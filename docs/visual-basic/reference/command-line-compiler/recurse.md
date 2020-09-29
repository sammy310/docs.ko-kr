---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 7ded2b7d102430d8d4e545da5ab6ce8bafe3609e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095424"
---
# <a name="-recurse"></a>-recurse

지정된 디렉터리 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>인수  

 `dir`  
 선택 사항입니다. 검색을 시작하려는 디렉터리입니다. 지정하지 않으면 프로젝트 디렉터리에서 검색이 시작됩니다.  
  
 `file`  
 필수 요소. 검색할 파일입니다. 와일드카드 문자가 허용됩니다.  
  
## <a name="remarks"></a>설명  

 파일 이름에 와일드카드를 사용하면 `-recurse`를 사용하지 않고 프로젝트 디렉터리에서 일치하는 모든 파일을 컴파일할 수 있습니다. 출력 파일 이름이 지정되지 않은 경우 컴파일러는 처리된 첫 번째 입력 파일의 출력 파일 이름을 기반으로 합니다. 이는 일반적으로 사전순으로 볼 때 컴파일되는 파일 목록의 첫 번째 파일입니다. 따라서 `-out` 옵션을 사용하여 출력 파일을 지정하는 것이 가장 좋습니다.  
  
> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-recurse` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 명령은 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다.  
  
```console
vbc *.vb  
```  
  
 다음 명령은 `Test\ABC` 디렉터리와 그 아래 디렉터리에 있는 모든 Visual Basic 파일을 컴파일한 다음, `Test.ABC.dll`을 생성합니다.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-out(Visual Basic)](out.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
