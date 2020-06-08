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
ms.openlocfilehash: 496627d3b77b0382ae7d15c8225a6fbd41f1db73
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403124"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>샘플 컴파일 명령줄(Visual Basic)

Visual Studio 내에서 Visual Basic 프로그램을 컴파일하는 대신 명령줄에서 컴파일하여 실행 파일(.exe) 또는 동적 연결 라이브러리(.dll) 파일을 생성할 수 있습니다.

Visual Basic 명령줄 컴파일러는 입력 및 출력 파일, 어셈블리, 디버그 및 전처리기 옵션을 제어하는 전체 옵션 세트를 지원합니다. 각 옵션은 `-option`과 `/option`의 두 가지 상호 교환 가능한 형식으로 사용할 수 있습니다. 이 설명서에서는 `-option` 양식만 표시합니다.

다음 표에서는 사용자가 직접 사용하기 위해 수정할 수 있는 몇 가지 샘플 명령줄을 보여줍니다.

|대상|기능|
|--------|---------|
|File.vb 컴파일 및 File.exe 만들기|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|File.vb 컴파일 및 File.dll 만들기|`vbc -target:library File.vb`|
|File.vb 컴파일 및 My.exe 만들기|`vbc -out:My.exe File.vb`|
|File.vb를 컴파일하고 File.dll이라는 라이브러리와 참조 어셈블리를 모두 만듭니다.|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|최적화가 설정되고 `DEBUG` 기호가 정의되어 File2.exe가 생성되는 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다.|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|로고 또는 경고를 표시하지 않고 File2.dll의 디버그 버전을 생성하여 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다.|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|현재 디렉터리에 있는 모든 Visual Basic 파일을 Something.dll로 컴파일합니다.|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> Visual Studio IDE를 사용하여 프로젝트를 빌드할 때 출력 창에 해당 컴파일러 옵션과 함께 연결된 **vbc** 명령에 대한 정보를 표시할 수 있습니다. 이 정보를 표시하려면 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)을 연 다음, **MSBuild 프로젝트 빌드 출력 상세도**를 **보통** 또는 더 높은 수준의 자세한 정보 표시로 설정합니다.

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [조건부 컴파일](../../programming-guide/program-structure/conditional-compilation.md)
