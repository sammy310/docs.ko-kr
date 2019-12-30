---
title: 지역화된 IntelliSense 파일 설치
description: Visual Studio에서 .NET Core 프로젝트에 대해 지역화된 IntelliSense 파일을 사용하도록 개발 머신을 설정하는 방법을 알아봅니다.
author: mairaw
ms.author: mairaw
ms.date: 12/18/2019
ms.openlocfilehash: 98d75544ab853e75c175dd2919991b250cfaa3b0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75436675"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a>.NET Core에 대해 지역화된 IntelliSense 파일을 설치하는 방법

[IntelliSense](/visualstudio/ide/using-intellisense)는 Visual Studio 등 여러 IDE(통합 개발 환경)에서 사용할 수 있는 코드 완성 지원 기능입니다. 기본적으로 .NET Core 프로젝트를 개발할 때 SDK에는 영어 버전의 IntelliSense 파일만 포함됩니다. 이 문서는 다음 사항을 설명합니다.

- 이러한 파일의 지역화된 버전을 설치하는 방법
- 다른 언어를 사용하도록 Visual Studio 설치를 수정하는 방법

## <a name="prerequisites"></a>전제 조건

- [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) 이상 버전
- [Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상 버전

## <a name="download-and-install-the-localized-intellisense-files"></a>지역화된 IntelliSense 파일 다운로드 및 설치

> [!IMPORTANT]
> IntelliSense 파일을 .NET Core 설치 폴더로 복사하려면 관리자 권한이 있어야 합니다.

1. [IntelliSense 파일 다운로드](https://dotnet.microsoft.com/download/dotnet-core/intellisense) 페이지로 이동합니다.

1. 사용할 언어 및 버전에 대한 IntelliSense 파일을 다운로드합니다.

1. Zip 파일의 내용을 추출합니다.

1. .NET Core 설치 폴더로 이동합니다. 기본적으로 *%ProgramFiles%\dotnet\packs*에 있습니다.

   - IntelliSense를 설치할 SDK를 선택하고 연결 경로로 이동합니다. 다음과 같은 옵션을 선택할 수 있습니다.

      | SDK 형식        | 경로                               |
      | --------------- | ---------------------------------- |
      | .NET Core       | *Microsoft.NETCore.App.Ref*        |
      | Windows 바탕 화면 | *Microsoft.WindowsDesktop.App.Ref* |
      | .NET Standard   | *NETStandard.Library.Ref*          |
   
   - 지역화된 IntelliSense를 설치하려는 버전으로 이동합니다. 예: *3.1.0*.
   - *ref* 폴더를 엽니다.
   - 모니커 폴더를 엽니다. 예: *netcoreapp3.1*.

   이동하는 전체 경로는 *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*과 비슷합니다.

1. 방금 연 모니커 폴더 안에 하위 폴더를 만듭니다. 폴더 이름은 사용하려는 언어를 나타냅니다. 다음 표에서는 다양한 옵션을 지정합니다.

   | 언어              | 폴더 이름 |
   | --------------------- | ----------- |
   | 포르투갈어(브라질)  | *pt-br*     |
   | 중국어(간체)  | *zh-hans*   |
   | 중국어(번체) | *zh-hant*   |
   | 프랑스어                | *fr*        |
   | 독일어                | *de*        |
   | 이탈리아어               | *it*        |
   | 일본어              | *ja*        |
   | 한국어                | *ko*        |
   | 러시아어               | *ru*        |
   | 스페인어               | *es*        |

1. 3단계에서 추출한 *.xml* 파일을 이 새 폴더에 복사합니다. *.xml* 파일이 SDK 폴더별로 분할되므로 4단계에서 선택한 일치하는 SDK로 복사합니다.

## <a name="modify-visual-studio-language"></a>Visual Studio 언어 수정

Visual Studio에서 IntelliSense에 다른 언어를 사용하도록 하려면 적절한 언어 팩을 설치합니다. 이 작업은 [설치 중](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional)에 수행하거나 Visual Studio 설치를 수정하여 나중에 수행할 수 있습니다. 선택한 언어로 Visual Studio를 이미 구성한 경우 IntelliSense 설치가 준비됩니다.

### <a name="install-the-language-pack"></a>언어 팩 설치

설치하는 동안 원하는 언어 팩을 설치하지 않은 경우 다음과 같이 Visual Studio를 업데이트하여 언어 팩을 설치합니다.

> [!IMPORTANT]
> Visual Studio를 설치, 업데이트 또는 수정하려면 관리 권한이 있는 계정으로 로그온해야 합니다. 자세한 내용은 [사용자 권한 및 Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio)를 참조하세요.

1. 컴퓨터에서 Visual Studio 설치 관리자를 찾습니다.

   예를 들어 Windows 10을 실행하는 컴퓨터에서 **시작**을 선택한 다음, **Visual Studio 설치 관리자**로 나열되는 **V** 문자로 스크롤합니다.

   ![Windows에서 Visual Studio 설치 관리자 열기](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > 다음 위치에서 Visual Studio 설치 관리자를 찾을 수도 있습니다.
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   계속하기 전에 설치 관리자를 업데이트해야 할 수 있습니다. 그렇다면 지시를 따르세요.

1. 설치 관리자에서 언어 팩을 추가하려는 Visual Studio의 버전을 찾은 다음, **수정**을 선택합니다.

   ![Visual Studio 업데이트 또는 수정](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > **수정** 단추가 표시되지 않고 **업데이트** 단추가 대신 표시되는 경우, Visual Studio를 업데이트해야만 설치를 수정할 수 있습니다.
   > 업데이트가 완료되면 **수정** 단추가 표시됩니다.

1. **언어 팩** 탭에서 설치하거나 제거하려는 언어를 선택하거나 선택 취소합니다.

   ![Visual Studio 언어 팩 탭](./media/localized-intellisense/vs-modify-language-packs.png)

1. **수정**을 선택합니다. 업데이트가 시작됩니다.

### <a name="modify-language-settings-in-visual-studio"></a>Visual Studio에서 언어 설정 수정

원하는 언어 팩을 설치했으면 다른 언어를 사용하도록 Visual Studio 설정을 수정합니다.

1. Visual Studio를 엽니다.

1. 시작 창에서 **코드를 사용하지 않고 계속**을 선택합니다.

1. 주 메뉴에서 **도구** > **옵션**을 선택합니다. [옵션] 대화 상자가 열립니다.

1. **환경** 폴더 아래에서 **국가별 설정**을 선택합니다.

1. **언어** 드롭다운에서 원하는 언어를 선택합니다. **확인**을 선택합니다. 

1. 변경 내용을 적용하려면 Visual Studio를 다시 시작해야 함을 알리는 대화 상자가 표시됩니다. **확인**을 선택합니다.

1. Visual Studio를 다시 시작합니다.

그러면 방금 설치한 IntelliSense 파일의 버전을 대상으로 하는 .NET Core 프로젝트를 열 때 IntelliSense가 예상대로 작동합니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio의 IntelliSense](/visualstudio/ide/using-intellisense)
