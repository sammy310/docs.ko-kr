---
title: F# 설치
description: 다양한 방법으로 F#을 설치하는 방법에 대해 알아봅니다.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401096"
---
# <a name="install-f"></a>설치 F\#

환경에 따라 여러 가지 방법으로 F#을 설치할 수 있습니다.

## <a name="install-f-with-visual-studio"></a>비주얼 스튜디오로 F# 설치

1. [Visual Studio를](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 처음 다운로드하는 경우 먼저 Visual Studio 설치 프로그램을 설치합니다. 설치 관리자에서 Visual Studio의 적절한 버전을 설치합니다.

   Visual Studio가 이미 설치되어 있는 경우 F#을 추가할 에디션 옆의 **수정을** 선택합니다.

2. 워크로드 페이지에서 ASP.NET 핵심 프로젝트에 대한 F# 및 .NET Core 지원을 포함하는 **ASP.NET 및 웹 개발** 워크로드를 선택합니다.

3. 오른쪽 하단 모서리에서 **수정을** 선택하여 선택한 모든 것을 설치합니다.

   그런 다음 Visual Studio 설치 관리자에서 **시작을** 선택하여 F#으로 Visual Studio를 열 수 있습니다.

## <a name="install-f-with-visual-studio-code"></a>비주얼 스튜디오 코드로 F# 설치

1. PATH에 [git을](https://git-scm.com/download) 설치하고 사용할 수 있는지 확인합니다. 명령 프롬프트를 입력하고 `git --version` **Enter**를 눌러 올바르게 설치되었는지 확인할 수 있습니다.

2. [.NET 코어 SDK](https://dotnet.microsoft.com/download) 및 [비주얼 스튜디오 코드를](https://code.visualstudio.com)설치합니다.

3. 확장 아이콘을 선택하고 "Ionide"를 검색합니다.

   비주얼 스튜디오 코드에서 F # 지원에 필요한 유일한 플러그인은 [Ionide-fsharp입니다.](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) 그러나, 당신은 또한 [가짜](https://fake.build/) 지원을 얻기 위해 [이오네이드 페이크를](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 설치하고 [이오니드 - Paket는](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) [Paket](https://fsprojects.github.io/Paket/) 지원을 받을 수 있습니다. FAKE와 Paket은 각각 프로젝트를 구축하고 종속성을 관리하기 위한 추가 F# 커뮤니티 도구입니다.

## <a name="install-f-with-visual-studio-for-mac"></a>Mac용 비주얼 스튜디오로 F# 설치

F#은 어떤 구성을 선택하든 [Mac용 Visual Studio에](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)기본적으로 설치됩니다.

설치가 완료되면 시각적 **스튜디오 시작을**선택합니다. macOS에서 파인더를 통해 비주얼 스튜디오를 열 수도 있습니다.

## <a name="install-f-on-a-build-server"></a>빌드 서버에 F# 설치

.NET SDK를 통해 .NET 코어 또는 .NET 프레임워크를 사용하는 경우 빌드 서버에 .NET SDK를 설치하기만 하면 됩니다. 그것은 당신이 필요로하는 모든 것을 가지고 있습니다.

.NET Framework를 사용하고 있고 .NET SDK를 사용하지 **않는** 경우 Windows 서버에 [Visual Studio 빌드 도구 SKU를](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) 설치해야 합니다. 설치 관리자에서 **.NET 데스크톱 빌드 도구를**선택한 다음 설치 프로그램 메뉴의 오른쪽에 있는 **F# 컴파일러** 구성 요소를 선택합니다.
