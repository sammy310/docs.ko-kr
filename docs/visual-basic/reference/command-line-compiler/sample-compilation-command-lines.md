---
title: 샘플 컴파일 명령줄
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350849"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>샘플 컴파일 명령줄 (Visual Basic)

Visual Studio 내에서 Visual Basic 프로그램을 컴파일하는 대신 명령줄에서 컴파일하여 실행 파일 (.exe) 또는 동적 연결 라이브러리 (.dll) 파일을 생성할 수 있습니다.

Visual Basic 명령줄 컴파일러는 입력 및 출력 파일, 어셈블리, 디버그 및 전처리기 옵션을 제어 하는 전체 옵션 집합을 지원 합니다. 각 옵션은 두 가지 상호 교환 가능한 형식 (`-option` 및 `/option`에서 사용할 수 있습니다. 이 문서에서는 `-option` 양식만 보여 줍니다.

다음 표에서는 사용자가 직접 사용 하기 위해 수정할 수 있는 몇 가지 샘플 명령줄을 보여 줍니다.

|수행할 작업|이후|
|--------|---------|
|파일 .vb를 컴파일하고 파일을 만듭니다.|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|파일 .vb를 컴파일하고 파일 .dll을 만듭니다.|`vbc -target:library File.vb`|
|파일 .vb를 컴파일하고 .exe를 만듭니다.|`vbc -out:My.exe File.vb`|
|파일 .vb를 컴파일하고 라이브러리와 파일 .dll 이라는 참조 어셈블리를 모두 만듭니다.|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|최적화를 사용 하 고 정의 된 `DEBUG` 기호를 사용 하 여 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다. File2를 만듭니다.|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|로고 또는 경고를 표시 하지 않고 디버그 버전의 File2를 생성 하는 현재 디렉터리의 모든 Visual Basic 파일을 컴파일합니다.|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|현재 디렉터리에 있는 모든 Visual Basic 파일을 다른 .dll로 컴파일합니다.|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 출력 창에 컴파일러 옵션을 사용 하 여 연결 된 **vbc** 명령에 대 한 정보를 표시할 수 있습니다. 이 정보를 표시 하려면 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)을 연 다음 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 를 **보통** 또는 높은 수준의 자세한 표시로 설정 합니다.

## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
