---
title: .NET을 사용한 Azure 개발을 위한 Visual Studio Code 구성
description: 이 문서에서는 VS Code에서 적합한 플러그인을 설치하고 구성하는 방법을 비롯해 Azure 개발을 위한 Visual Studio Code를 구성하는 방법을 안내합니다.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 65ced99befe12d137062b4ea6a59a1ccd3099e0b
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700989"
---
# <a name="configure-visual-studio-code-for-azure-development"></a>Azure 개발을 위한 Visual Studio Code 구성

.NET 개발을 수행하거나, Angular, React, Vue와 같은 프레임워크를 사용하여 단일 페이지 애플리케이션을 빌드하거나, Python과 같은 다른 언어로 애플리케이션을 작성하기 위해 Visual Studio Code를 사용하는 경우 Azure 개발을 위한 Visual Studio Code를 구성하는 것이 좋습니다.

### <a name="download-visual-studio-code"></a>Visual Studio Code 다운로드

Visual Studio Code가 이미 설치되어 있으면 이 단계를 건너뛸 수 있습니다.

> [!div class="nextstepaction"]
> [Visual Studio Code 다운로드](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a>Azure Tools 확장 팩 설치

[Azure Tools 확장 팩](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)에는 Azure App Service, Azure Functions, Azure Storage, Cosmos DB, Azure Virtual Machines 등을 사용하는 데 필요한 모든 확장이 하나의 편리한 패키지로 포함되어 있습니다.

Visual Studio Code에서 확장을 설치하려면 다음을 수행합니다.

1. <kbd>Ctrl+Shift+X</kbd>를 눌러 **확장** 창을 엽니다.
1. *Azure Tools* 확장을 검색합니다.
1. **설치** 단추를 선택합니다.

![Azure Tools 확장 팩을 검색하는 확장 패널을 보여 주는 Visual Studio Code의 스크린샷](./media/visual-studio-code-azure-tools.png)

Visual Studio Code에서 확장을 설치하는 방법에 대한 자세한 내용은 Visual Studio Code 웹 사이트에서 [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)(확장 Marketplace) 문서를 참조하세요.

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a>Azure Tools를 사용하여 Azure 계정에 로그인

왼쪽 패널에 Azure 아이콘이 있습니다. 이 아이콘을 선택하면 Azure 서비스의 제어판이 표시됩니다. 서비스 아래에서 **Azure에 로그인...** 을 선택하여 Visual Studio Code에서 Azure Tools의 인증 프로세스를 완료합니다.

![Azure Tools로 Azure에 로그인하는 방법을 보여 주는 Visual Studio Code의 스크린샷](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a>다음 단계

다음으로 워크스테이션에 Azure CLI를 설치하는 것이 좋습니다.

> [!div class="nextstepaction"]
> [Azure CLI 설치](./install-azure-cli.md)
