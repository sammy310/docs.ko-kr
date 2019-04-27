---
title: 명령줄에서 빌드(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: 798baa90308c83e42b335635fb23a9983f5180fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839386"
---
# <a name="building-from-the-command-line-visual-basic"></a>명령줄에서 빌드(Visual Basic)
Visual Basic 프로젝트를 하나 이상의 별도 소스 파일로 구성 됩니다. 컴파일으로 알려진 프로세스 동안 이러한 파일은 모일 하나의 패키지로-응용 프로그램으로 실행할 수 있는 단일 실행 파일이 있습니다.  
  
 Visual Basic Visual Studio 통합된 개발 환경 (IDE) 내에서 프로그램을 컴파일하는 대신 명령줄 컴파일러를 제공 합니다. 명령줄 컴파일러는 IDE의 기능 중 일부만 필요 하지는 상황을 위한-예를 들어 때 사용 하거나 제한 된 시스템 메모리 또는 저장소 공간이 있는 컴퓨터에 대 한 작성 합니다.  
  
  Visual Studio IDE 내에서 원본 파일을 컴파일하려면 선택 합니다 **빌드** 에서 명령을 합니다 **빌드** 메뉴.  
  
> [!TIP]
>  Visual Studio IDE를 사용 하 여 프로젝트 파일을 빌드할 때 연결에 대 한 정보를 표시할 수 있습니다 **vbc** 명령 및 출력 창에 해당 스위치입니다. 이 정보를 표시 하려면 열을 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), 설정한 후 합니다 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 에 **보통** 또는 더 높은 수준의 세부 정보 표시 합니다. 자세한 내용은 [방법: 보기, 저장 및 빌드 로그 파일 구성](/visualstudio/ide/how-to-view-save-and-configure-build-log-files)합니다.  
  
 MSBuild를 사용 하 여 명령 프롬프트에서 프로젝트 (.vbproj) 파일을 컴파일할 수 있습니다. 자세한 내용은 [명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference) 고 [연습: MSBuild 사용](/visualstudio/msbuild/walkthrough-using-msbuild)을 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 명령줄 컴파일러 호출](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 MS-DOS 프롬프트 또는 특정 하위 디렉터리에서 명령줄 컴파일러를 호출 하는 방법에 설명 합니다.  
  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 자신의 용도 맞게 수정할 수 있는 샘플 명령줄의 목록을 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 컴파일러 옵션을 사전순 또는 용도 따라 구성 목록을 제공 합니다.  
  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 특정 코드 부분을 컴파일하는 방법을 설명 합니다.  
  
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 다른 빌드에 포함 될 새로운, 프로젝트 속성을 선택 하 고 올바른 순서 대로 프로젝트를 빌드하는 구성 하는 방법에 설명 합니다.
