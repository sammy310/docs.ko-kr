---
title: .NET SDK 개요
description: .NET 프로젝트를 만드는 데 사용되는 라이브러리 및 도구 집합인 .NET SDK에 대해 알아봅니다.
ms.date: 07/31/2019
ms.technology: dotnet-cli
ms.openlocfilehash: 5236d4abec5dcbf950059dd906958158cfb592fe
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216143"
---
# <a name="net-sdk-overview"></a><span data-ttu-id="c13d9-103">.NET SDK 개요</span><span class="sxs-lookup"><span data-stu-id="c13d9-103">.NET SDK overview</span></span>

<span data-ttu-id="c13d9-104">.NET SDK는 개발자가 .NET 애플리케이션과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-104">The .NET SDK is a set of libraries and tools that allow developers to create .NET applications and libraries.</span></span> <span data-ttu-id="c13d9-105">애플리케이션을 빌드하고 실행하는 데 사용되는 다음 구성 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-105">It contains the following components that are used to build and run applications:</span></span>

- <span data-ttu-id="c13d9-106">.NET CLI.</span><span class="sxs-lookup"><span data-stu-id="c13d9-106">The .NET CLI.</span></span>
- <span data-ttu-id="c13d9-107">.NET 라이브러리 및 런타임.</span><span class="sxs-lookup"><span data-stu-id="c13d9-107">.NET libraries and runtime.</span></span>
- <span data-ttu-id="c13d9-108">`dotnet` [드라이버](tools/index.md#driver).</span><span class="sxs-lookup"><span data-stu-id="c13d9-108">The `dotnet` [driver](tools/index.md#driver).</span></span>

## <a name="acquiring-the-net-sdk"></a><span data-ttu-id="c13d9-109">.NET SDK 가져오기</span><span class="sxs-lookup"><span data-stu-id="c13d9-109">Acquiring the .NET SDK</span></span>

<span data-ttu-id="c13d9-110">모든 도구와 마찬가지로 먼저 컴퓨터에 도구를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-110">As with any tooling, the first thing is to get the tools to your machine.</span></span> <span data-ttu-id="c13d9-111">시나리오에 따라 다음 방법 중 하나를 사용하여 SDK를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-111">Depending on your scenario, you can install the SDK using one of the following methods:</span></span>

- <span data-ttu-id="c13d9-112">기본 설치 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-112">Use the native installers.</span></span>
- <span data-ttu-id="c13d9-113">설치 셸 스크립트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-113">Use the installation shell script.</span></span>

<span data-ttu-id="c13d9-114">기본 설치 관리자는 주로 개발자의 컴퓨터를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-114">The native installers are primarily meant for developer's machines.</span></span> <span data-ttu-id="c13d9-115">SDK는 Ubuntu의 DEB 패키지 또는 Windows의 MSI 번들 등 지원되는 플랫폼의 기본 설치 메커니즘을 사용하여 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-115">The SDK is distributed using each supported platform's native install mechanism, such as DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="c13d9-116">이러한 설치 관리자는 설치 후 SDK를 즉시 사용하려는 사용자에게 필요한 환경을 설치 및 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-116">These installers install and set up the environment as needed for the user to use the SDK immediately after the install.</span></span> <span data-ttu-id="c13d9-117">그러나 이러한 사용자는 컴퓨터에 대한 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-117">However, they also require administrative privileges on the machine.</span></span> <span data-ttu-id="c13d9-118">[.NET 다운로드](https://dotnet.microsoft.com/download) 페이지에 설치할 SDK를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-118">You can find the SDK to install on the [.NET downloads](https://dotnet.microsoft.com/download) page.</span></span>

<span data-ttu-id="c13d9-119">반면 설치 스크립트는 관리 권한이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-119">Install scripts, on the other hand, don't require administrative privileges.</span></span> <span data-ttu-id="c13d9-120">그러나 머신에 필수 구성 요소도 설치되지 않습니다. 모든 필수 구성 요소를 수동으로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-120">However, they also don't install any prerequisites on the machine; you need to install all of the prerequisites manually.</span></span> <span data-ttu-id="c13d9-121">스크립트는 대개 빌드 서버를 설정하거나 관리자 권한 없이 도구를 설치할 경우 사용됩니다(위의 필수 구성 요소 주의 사항 참조).</span><span class="sxs-lookup"><span data-stu-id="c13d9-121">The scripts are meant mostly for setting up build servers or when you wish to install the tools without admin privileges (do note the prerequisites caveat above).</span></span> <span data-ttu-id="c13d9-122">자세한 내용은 [스크립트 참조 설치](tools/dotnet-install-script.md) 문서에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-122">You can find more information in the [install script reference](tools/dotnet-install-script.md) article.</span></span> <span data-ttu-id="c13d9-123">CI 빌드 서버에서 SDK를 설정하는 방법에 관심이 있는 경우 [CI(연속 통합)에서 .NET SDK 및 도구 사용](tools/using-ci-with-cli.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c13d9-123">If you're interested in how to set up the SDK on your CI build server, see the [Using .NET SDK and tools in Continuous Integration (CI)](tools/using-ci-with-cli.md) article.</span></span>

<span data-ttu-id="c13d9-124">기본적으로 SDK는 "side-by-side"(SxS) 방식으로 설치되므로 여러 버전이 단일 머신에서 동시에 공존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-124">By default, the SDK installs in a "side-by-side" (SxS) manner, which means multiple versions can coexist at any given time on a single machine.</span></span> <span data-ttu-id="c13d9-125">CLI 명령을 실행할 때 버전을 선택하는 방법은 [사용할 .NET 버전 선택](versions/selection.md) 문서에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c13d9-125">How the version gets picked when you're running CLI commands is explained in more detail in the [Select the .NET version to use](versions/selection.md) article.</span></span>

## <a name="see-also"></a><span data-ttu-id="c13d9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c13d9-126">See also</span></span>

- [<span data-ttu-id="c13d9-127">.NET CLI 개요</span><span class="sxs-lookup"><span data-stu-id="c13d9-127">.NET CLI overview</span></span>](tools/index.md)
- [<span data-ttu-id="c13d9-128">.NET 버전 관리 개요</span><span class="sxs-lookup"><span data-stu-id="c13d9-128">.NET versioning overview</span></span>](versions/index.md)
- [<span data-ttu-id="c13d9-129">.NET 런타임 및 SDK를 제거하는 방법</span><span class="sxs-lookup"><span data-stu-id="c13d9-129">How to remove the .NET runtime and SDK</span></span>](install/remove-runtime-sdk-versions.md)
- [<span data-ttu-id="c13d9-130">사용할 .NET 버전 선택</span><span class="sxs-lookup"><span data-stu-id="c13d9-130">Select the .NET version to use</span></span>](versions/selection.md)
