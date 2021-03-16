---
title: VS Code 확장 작성자용 .NET 설치 도구
description: .NET 런타임 설치를 위한 Visual Studio Code 확장인 확장 작성자용 .NET 설치 도구에 대한 개요입니다.
author: sfoslund
ms.date: 11/18/2020
ms.openlocfilehash: 4be931a254e4ce969f9eaf2efde7939cb54e1d5f
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605154"
---
# <a name="net-install-tool-for-extension-authors"></a><span data-ttu-id="4afc8-103">확장 작성자용 .NET 설치 도구</span><span class="sxs-lookup"><span data-stu-id="4afc8-103">.NET install tool for extension authors</span></span>

<span data-ttu-id="4afc8-104">[확장 작성자용 .NET 설치 도구](https://github.com/dotnet/vscode-dotnet-runtime)는 VS Code 확장 작성자를 위해 특별히 .NET 런타임 획득을 허용하는 Visual Studio Code 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="4afc8-104">The [.NET install tool for extension authors](https://github.com/dotnet/vscode-dotnet-runtime) is a Visual Studio Code extension that allows acquisition of the .NET runtime specifically for VS Code extension authors.</span></span> <span data-ttu-id="4afc8-105">이 도구는 .NET에서 작성된 확장에 활용되며 확장(예: 언어 서버)을 부팅하기 위해 .NET이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4afc8-105">This tool is intended to be leveraged in extensions that are written in .NET and require .NET to boot pieces of the extension (for example, a language server).</span></span> <span data-ttu-id="4afc8-106">확장은 사용자가 개발용 .NET을 설치하는 데 직접 사용하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4afc8-106">The extension is not intended to be used directly by users to install .NET for development.</span></span>

## <a name="getting-started-extension-authors"></a><span data-ttu-id="4afc8-107">시작: 확장 작성자</span><span class="sxs-lookup"><span data-stu-id="4afc8-107">Getting started: extension authors</span></span>

<span data-ttu-id="4afc8-108">확장 작성자용 .NET 설치 도구가 사용자의 시나리오에 적합한지 확인하려면 먼저 GitHub 페이지에서 [이 확장의 목표](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions)를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="4afc8-108">To ensure that the .NET install tool for extension authors is the right fit for your scenario, start by reviewing the [goals of this extension](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions) on our GitHub page.</span></span>

> [!NOTE]
> <span data-ttu-id="4afc8-109">이 도구는 .NET 런타임 설치에만 사용할 수 있으며, 현재 .NET SDK를 설치하는 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc8-109">This tool can be used to install the .NET runtime only, it currently does not have the capability to install the .NET SDK.</span></span>

<span data-ttu-id="4afc8-110">확장 작성자용 .NET 설치 도구가 사용자의 요구에 적합한 것을 확인했다면 [확장 매니페스트](https://code.visualstudio.com/api/references/extension-manifest)에서 해당 종속성을 가져오고 [VS Code API](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command)에 표시되는 명령을 사용하여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc8-110">Once you have verified that the .NET install tool for extension authors fits your needs, you can take a dependency on it in your [extension manifest](https://code.visualstudio.com/api/references/extension-manifest) and begin using the commands we expose with the [VS Code API](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command).</span></span> <span data-ttu-id="4afc8-111">[GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md)에서 이 확장이 표시하는 명령 목록을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc8-111">You can find the list of commands this extension exposes on our [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md).</span></span>

<span data-ttu-id="4afc8-112">이러한 단계를 수행하는 방법은 이 [샘플 확장](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4afc8-112">Check out this [sample extension](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample) to see these steps in action.</span></span>

<span data-ttu-id="4afc8-113">더 많은 예제를 보려면 현재 이 도구를 활용하는 오픈 소스 확장을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4afc8-113">For more examples, check out these open source extensions that currently leverage this tool:</span></span>

- [<span data-ttu-id="4afc8-114">Visual Studio Code용 Azure Resource Manager(ARM) 도구</span><span class="sxs-lookup"><span data-stu-id="4afc8-114">Azure Resource Manager (ARM) Tools for Visual Studio Code</span></span>](https://github.com/microsoft/vscode-azurearmtools)

- [<span data-ttu-id="4afc8-115">.NET Interactive Notebook</span><span class="sxs-lookup"><span data-stu-id="4afc8-115">.NET Interactive Notebooks</span></span>](https://github.com/dotnet/interactive/tree/main/src/dotnet-interactive-vscode)

## <a name="getting-started-end-users"></a><span data-ttu-id="4afc8-116">시작: 최종 사용자</span><span class="sxs-lookup"><span data-stu-id="4afc8-116">Getting started: end users</span></span>

<span data-ttu-id="4afc8-117">일반적으로 최종 사용자는 확장 작성자용 .NET 설치 도구와 상호 작용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4afc8-117">In general, the end user should not need to interact with the .NET install tool for extension authors at all.</span></span> <span data-ttu-id="4afc8-118">확장에 문제가 있는 경우 [문제 해결 페이지](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting-runtime.md)를 확인하거나 [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues)에서 문제를 제출하세요.</span><span class="sxs-lookup"><span data-stu-id="4afc8-118">If you are having problems with the extension, check out our [troubleshooting page](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting-runtime.md) or file an issue on our [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues).</span></span>
