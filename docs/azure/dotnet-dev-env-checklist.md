---
title: Azure의 .NET 개발 구성 검사 목록
description: Azure를 사용하여 .NET 개발을 수행하기 위해 설치해야 하는 모든 도구의 간략한 요약을 제공합니다.
ms.date: 1/1/2021
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: a2ff9bbf1e6a8790ddc161a1a1c8d14e8fab6e41
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98027243"
---
# <a name="net-on-azure-development-environment-checklist"></a><span data-ttu-id="f56aa-103">Azure의 .NET 개발 환경 검사 목록</span><span class="sxs-lookup"><span data-stu-id="f56aa-103">.NET on Azure development environment checklist</span></span>

<span data-ttu-id="f56aa-104">이 검사 목록은 Azure에서의 .NET 개발을 위해 개발 환경이 올바르게 구성되었는지 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-104">This checklist is provided to help you make sure you have your development environment correctly configured for .NET development with Azure</span></span>

## <a name="create-an-azure-account"></a><span data-ttu-id="f56aa-105">Azure 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="f56aa-105">Create an Azure account</span></span>

<span data-ttu-id="f56aa-106">Azure 서비스에 액세스하거나 Azure에서 애플리케이션을 실행하려면 Azure 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-106">To access Azure services or run applications in Azure, you need an Azure account.</span></span>

* <span data-ttu-id="f56aa-107">Visual Studio 구독자인 경우 매월 제공되는 [무료 Azure 크레딧](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-107">If you are a Visual Studio subscriber, you have monthly [free Azure credits](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) available to you every month</span></span>
* <span data-ttu-id="f56aa-108">[Azure 체험 계정을 만들고](https://azure.microsoft.com/free/dotnet/) $200 크레딧을 받고 12개월 동안의 별도의 비용이 없는 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-108">[Create a free Azure account](https://azure.microsoft.com/free/dotnet/) and receive $200 in credits and select services free for 12 months</span></span>
* <span data-ttu-id="f56aa-109">회사의 Azure 관리자가 할당해준 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-109">Use an account assigned to you by your company's Azure administrator</span></span>

## <a name="configure-your-ide"></a><span data-ttu-id="f56aa-110">IDE 구성</span><span class="sxs-lookup"><span data-stu-id="f56aa-110">Configure your IDE</span></span>

<span data-ttu-id="f56aa-111">Visual Studio 및 Visual Studio Code와 같은 널리 사용되는 도구에는 IDE에서 바로 Azure로 작업하도록 해주는 확장이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-111">Popular tools like Visual Studio and Visual Studio Code have extensions available to let you work with Azure right from your IDE.</span></span>

* <span data-ttu-id="f56aa-112">Azure를 사용한 .NET 개발을 위한 [Visual Studio 구성](./configure-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="f56aa-112">[Configure Visual Studio](./configure-visual-studio.md) for .NET development using Azure</span></span>
* <span data-ttu-id="f56aa-113">Azure를 사용한 .NET 개발을 위한 [Visual Studio Code 구성](./configure-vs-code.md)</span><span class="sxs-lookup"><span data-stu-id="f56aa-113">[Configure Visual Studio Code](./configure-vs-code.md) for .NET Development using Azure</span></span>

## <a name="install-the-azure-cli"></a><span data-ttu-id="f56aa-114">Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="f56aa-114">Install the Azure CLI</span></span>

<span data-ttu-id="f56aa-115">Azure Portal을 사용하는 것 외에도 Azure CLI를 설치하여 Azure 리소스를 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-115">In addition to using the Azure portal, you will want to install the Azure CLI to create and manage Azure resources.</span></span>

* <span data-ttu-id="f56aa-116">[Windows용 Azure CLI 설치](/cli/azure/install-azure-cli-windows?tabs=azure-cli)</span><span class="sxs-lookup"><span data-stu-id="f56aa-116">[Install the Azure CLI for Windows](/cli/azure/install-azure-cli-windows?tabs=azure-cli))</span></span>
* [<span data-ttu-id="f56aa-117">macOS용 Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="f56aa-117">Install the Azure CLI for macOS</span></span>](/cli/azure/install-azure-cli-macos)
* [<span data-ttu-id="f56aa-118">Linux용 Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="f56aa-118">Install the Azure CLI for Linux</span></span>](/cli/azure/install-azure-cli-linux)

## <a name="install-additional-tools-and-utilities"></a><span data-ttu-id="f56aa-119">추가 도구 및 유틸리티 설치</span><span class="sxs-lookup"><span data-stu-id="f56aa-119">Install additional tools and utilities</span></span>

<span data-ttu-id="f56aa-120">이러한 추가 도구는 Azure로 작업할 때 생산성을 높일 수 있도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-120">These additional tools are designed to make you more productive when working with Azure.</span></span>

* <span data-ttu-id="f56aa-121">PowerShell 스크립트를 사용하여 Azure 리소스를 만들고 관리하려는 경우 [Azure PowerShell 설치](/powershell/azure/install-az-ps)</span><span class="sxs-lookup"><span data-stu-id="f56aa-121">[Install Azure PowerShell](/powershell/azure/install-az-ps) if you plan on using PowerShell scripts to create and manage Azure resources</span></span>
* <span data-ttu-id="f56aa-122">BLOB, 큐, 테이블, CosmosDB를 비롯한 Azure 스토리지 리소스의 데이터를 업로드, 다운로드, 관리하려면 [Azure Storage Explorer 설치](https://azure.microsoft.com/features/storage-explorer/)</span><span class="sxs-lookup"><span data-stu-id="f56aa-122">[Install Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/) to upload, download, and manage data in Azure storage resources including blobs, queues, tables, and CosmosDB.</span></span>
* <span data-ttu-id="f56aa-123">Azure SQL로 작업하는 경우 [Azure Data Studio 설치](/sql/azure-data-studio/download-azure-data-studio)</span><span class="sxs-lookup"><span data-stu-id="f56aa-123">[Install Azure Data Studio](/sql/azure-data-studio/download-azure-data-studio) if you are working with Azure SQL</span></span>

## <a name="bookmark-the-following-sites"></a><span data-ttu-id="f56aa-124">다음 사이트를 책갈피에 추가</span><span class="sxs-lookup"><span data-stu-id="f56aa-124">Bookmark the following sites</span></span>

<span data-ttu-id="f56aa-125">Azure 개발 중에는 이러한 사이트를 자주 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f56aa-125">You will use these sites frequently when doing Azure development.</span></span>  <span data-ttu-id="f56aa-126">빠른 참조를 위해 책갈피에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="f56aa-126">Bookmark them for quick reference.</span></span>

* <span data-ttu-id="f56aa-127">Azure Portal - [https://portal.azure.com/](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="f56aa-127">Azure Portal - [https://portal.azure.com/](https://portal.azure.com/)</span></span>
* <span data-ttu-id="f56aa-128">Azure Cloud Shell - [https://shell.azure.com/](https://shell.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="f56aa-128">Azure Cloud Shell - [https://shell.azure.com/](https://shell.azure.com/)</span></span>
