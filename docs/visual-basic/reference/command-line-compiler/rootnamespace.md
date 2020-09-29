---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: d9388ace03f654458eb955e989673b7441e72f23
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085141"
---
# <a name="-rootnamespace"></a>-rootnamespace

모든 형식 선언에 대한 네임스페이스를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`namespace`|현재 프로젝트에 대한 모든 형식 선언을 묶을 네임스페이스의 이름입니다.|  
  
## <a name="remarks"></a>설명  

 Visual Studio 실행 파일(Devenv.exe)을 사용하여 Visual Studio 통합 개발 환경에서 만든 프로젝트를 컴파일하는 경우 `-rootnamespace`를 사용하여 <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> 속성의 값을 지정합니다. 자세한 내용은 [Devenv 명령줄 스위치](/visualstudio/ide/reference/devenv-command-line-switches)를 참조하세요.  
  
 공용 언어 런타임 MSIL 디스어셈블러(`Ildasm.exe`)를 사용하여 출력 파일에서 네임스페이스 이름을 봅니다.  
  
|Visual Studio 통합 개발 환경에서 -rootnamespace을 설정하려면 다음을 수행합니다.|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **애플리케이션** 탭을 클릭합니다.<br />3.  **루트 네임스페이스** 상자에서 값을 수정합니다.|  
  
## <a name="example"></a>예제  

 다음 코드는 `In.vb`를 컴파일하고 네임스페이스 `mynamespace`의 모든 형식 선언을 묶습니다.  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [Ildasm.exe(IL 디스어셈블러)](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
