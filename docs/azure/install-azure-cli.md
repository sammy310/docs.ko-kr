---
title: Azure CLI 설치
description: Azure 개발자는 Azure CLI를 설치해야 하므로 이 문서에서는 CLI가 필요한 이유와 다운로드하여 설치할 수 있는 위치를 설명합니다.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 43737aaf5dfd02b8c4ffa6c213d7221cfe38162f
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700973"
---
# <a name="install-the-azure-cli"></a><span data-ttu-id="536f1-103">Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="536f1-103">Install the Azure CLI</span></span>

<span data-ttu-id="536f1-104">Azure에서는 Azure Portal 외에도 Azure 리소스를 만들고 관리하는 명령줄 도구로 [Azure CLI](/cli/azure/)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-104">In addition to the Azure Portal, Azure also offers the [Azure CLI](/cli/azure/) as a command-line tool to create and manage Azure resources.</span></span> <span data-ttu-id="536f1-105">Azure CLI는 효율성과 반복 가능성을 향상하고 반복 작업을 스크립팅할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-105">The Azure CLI offers the benefits of efficiency, repeatability, and the ability to script recurring tasks.</span></span>  

<span data-ttu-id="536f1-106">실제로 대부분의 개발자는 Azure Portal과 Azure CLI를 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-106">In practice, most developers use both the Azure Portal and the Azure CLI.</span></span> <span data-ttu-id="536f1-107">Azure Portal이 새로운 서비스를 탐색하고 Azure 계정의 모든 리소스에 관한 개요를 확인할 때 유용하다면 Azure CLI를 통해서는 대부분의 개발자가 더 빠르고 효율적으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-107">Where as the Azure Portal is useful when exploring new services and getting an overview of all of the resources in your Azure account, most developers find the Azure CLI to be faster and more efficient.</span></span>  <span data-ttu-id="536f1-108">Azure Portal에서 여러 단계로 수행하는 작업을 Azure CLI에서 단일 명령으로 수행할 수 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-108">The Azure CLI can often accomplish in a single command what takes multiple steps in the Azure Portal.</span></span>  <span data-ttu-id="536f1-109">또한 Azure CLI 명령을 파일에 저장할 수 있으므로 개발자가 되풀이 작업이 매번 동일하게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-109">In addition, since Azure CLI commands can be saved to a file, developers can assure that recurrent tasks are run the same way each time.</span></span>

<span data-ttu-id="536f1-110">Azure CLI는 Windows, macOS, Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-110">The Azure CLI is available for Windows, macOS, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="536f1-111">Windows용 Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="536f1-111">Install the Azure CLI for Windows</span></span>](/cli/azure/install-azure-cli-windows?tabs=azure-cli)

> [!div class="nextstepaction"]
> [<span data-ttu-id="536f1-112">macOS용 Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="536f1-112">Install the Azure CLI for macOS</span></span>](/cli/azure/install-azure-cli-macos)

> [!div class="nextstepaction"]
> [<span data-ttu-id="536f1-113">Linux용 Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="536f1-113">Install the Azure CLI for Linux</span></span>](/cli/azure/install-azure-cli-linux)

### <a name="azure-cloud-shell"></a><span data-ttu-id="536f1-114">Azure Cloud Shell</span><span class="sxs-lookup"><span data-stu-id="536f1-114">Azure Cloud Shell</span></span>

<span data-ttu-id="536f1-115">[https://shell.azure.com](https://shell.azure.com)의 Azure Cloud Shell에서 Azure CLI를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-115">You can also use the Azure CLI in the Azure Cloud Shell at [https://shell.azure.com](https://shell.azure.com).</span></span>  <span data-ttu-id="536f1-116">Azure Cloud Shell은 Azure 리소스를 관리하기 위한 모든 기능을 갖춘 브라우저 기반 셸입니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-116">The Azure Cloud Shell is a fully functional, browser-based shell for managing Azure resources.</span></span>  <span data-ttu-id="536f1-117">Azure Cloud Shell은 명령줄 환경이 필요하지만 Azure CLI를 설치할 수 없는 디바이스를 사용 중인 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="536f1-117">The Azure Cloud Shell is useful when you need a command line environment but are working on a device where you are unable to install the Azure CLI.</span></span>

![브라우저에서 실행하는 Azure Cloud Shell의 스크린샷](media/azure-cloud-shell.png)
