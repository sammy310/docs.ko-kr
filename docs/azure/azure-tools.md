---
title: 추가 Azure 도구
description: 이 문서에서는 Azure 작업을 위한 추가 도구와 유틸리티 및 이들의 설치 방법을 설명합니다.
ms.date: 1/1/2021
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: e2137c8758fd8ca5ba05dcad87afb5480ec95561
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98027244"
---
# <a name="additional-tools-for-azure-developers"></a><span data-ttu-id="fd05c-103">Azure 개발자를 위한 추가 도구</span><span class="sxs-lookup"><span data-stu-id="fd05c-103">Additional Tools for Azure Developers</span></span>

<span data-ttu-id="fd05c-104">IDE를 구성하고 Azure CLI를 설치하는 것 외에도 Azure에서 생산성 향상에 도움이 되는 여러 가지 도구와 유틸리티를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-104">In addition to configuring your IDE and installing the Azure CLI, multiple other tools and utilities are available to help you be more productive with Azure.</span></span>  

## <a name="azure-powershell"></a><span data-ttu-id="fd05c-105">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd05c-105">Azure PowerShell</span></span>

<span data-ttu-id="fd05c-106">Azure PowerShell은 PowerShell에서 직접(명령줄 또는 PowerShell 스크립트 내에서) Azure 리소스를 관리하기 위한 cmdlet의 PowerShell 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-106">Azure PowerShell is a PowerShell module of cmdlets for managing Azure resource directly from PowerShell, either from the command line or from within PowerShell scripts.</span></span>  <span data-ttu-id="fd05c-107">Azure PowerShell은 PowerShell 개체, 명령을 파이프라인으로 결합하기와 같은 PowerShell 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-107">Azure PowerShell supports PowerShell features like PowerShell objects and combining commands into pipelines.</span></span>  <span data-ttu-id="fd05c-108">전에 PowerShell을 사용했거나 Azure 리소스를 관리하기 위해 복잡한 자동화 스크립트를 작성해야 하는 경우 Azure PowerShell을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-108">If you have used PowerShell before or need to write complex automation scripts to manage Azure resources, you will want to install Azure PowerShell.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fd05c-109">Azure PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="fd05c-109">Install Azure PowerShell</span></span>](/powershell/azure/install-az-ps)

## <a name="azure-storage-explorer"></a><span data-ttu-id="fd05c-110">Azure Storage Explorer</span><span class="sxs-lookup"><span data-stu-id="fd05c-110">Azure Storage Explorer</span></span>

<span data-ttu-id="fd05c-111">Azure Storage Explorer는 Azure에서 스토리지 리소스 및 데이터를 관리하는 데 사용할 수 있는 무료 GUI 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-111">Azure Storage Explorer is a free, GUI tool for managing storage resources and data in Azure.</span></span>  <span data-ttu-id="fd05c-112">BLOB 및 파일을 업로드, 다운로드, 관리하는 것은 물론 Azure 큐, 테이블, CosmosDB의 데이터도 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-112">You can upload, download and manage blobs and files, as well as manage data in Azure queues, tables and CosmosDB.</span></span>  <span data-ttu-id="fd05c-113">Azure에서 스토리지 리소스를 사용하려는 경우 Azure Storage Explorer를 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-113">If you plan on working with any storage resources in Azure, installation of Azure Storage Explorer is recommended.</span></span>  <span data-ttu-id="fd05c-114">Windows, macOS, Linux 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-114">Versions are available for Windows, macOS and Linux.</span></span>  

> [!div class="nextstepaction"]
> [<span data-ttu-id="fd05c-115">Azure Storage Explorer 다운로드</span><span class="sxs-lookup"><span data-stu-id="fd05c-115">Download Azure Storage Explorer</span></span>](https://azure.microsoft.com/en-us/features/storage-explorer/)

## <a name="azure-data-studio"></a><span data-ttu-id="fd05c-116">Azure Data Studio</span><span class="sxs-lookup"><span data-stu-id="fd05c-116">Azure Data Studio</span></span>

<span data-ttu-id="fd05c-117">Azure Data Studio는 온-프레미스 및 클라우드 데이터베이스에 모두 액세스하기 위한 플랫폼 간 데이터베이스 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-117">Azure Data Studio is a cross-platform database tool for accessing both on-premises and cloud databases.</span></span>  <span data-ttu-id="fd05c-118">이를 통해 결과 집합을 차트로 작성하고 시각화하는 것 외에도 SQL 쿼리를 편집하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-118">It allows you to edit and execute SQL queries in addition to charting and visualizing result sets.</span></span>  <span data-ttu-id="fd05c-119">SQL Server 2014 이상 및 Azure SQL의 모든 SQL Server 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-119">It supports all versions of SQL Server from SQL Server 2014 and later and Azure SQL.</span></span>  <span data-ttu-id="fd05c-120">Azure SQL을 사용하려는 경우 Azure Data Studio를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-120">If you plan to work with Azure SQL, download and install Azure Data Studio.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fd05c-121">Azure Data Studio 다운로드</span><span class="sxs-lookup"><span data-stu-id="fd05c-121">Download Azure Data Studio</span></span>](/sql/azure-data-studio/download-azure-data-studio)

## <a name="next-steps"></a><span data-ttu-id="fd05c-122">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fd05c-122">Next steps</span></span>

<span data-ttu-id="fd05c-123">[Azure의 .NET 개발 환경 검사 목록](./dotnet-dev-env-checklist.md)을 사용하여 개발 환경이 올바르게 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd05c-123">Validate your development environment is set up correctly using the [.NET on Azure development environment checklist](./dotnet-dev-env-checklist.md).</span></span>
