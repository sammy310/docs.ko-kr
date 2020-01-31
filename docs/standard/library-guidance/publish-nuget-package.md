---
title: NuGet 패키지 게시
description: .NET 라이브러리를 NuGet에 게시하는 모범 사례 권장 사항입니다.
ms.date: 10/02/2018
ms.openlocfilehash: 089c660bc51252c6295858b1462ae59bde968564
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744561"
---
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="77332-103">NuGet 패키지 게시</span><span class="sxs-lookup"><span data-stu-id="77332-103">Publishing a NuGet package</span></span>

<span data-ttu-id="77332-104">NuGet 패키지는 패키지 리포지토리에서 게시되고 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77332-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="77332-105">NuGet.org가 가장 널리 알려지고 사용되는 리포지토리지만, NuGet 패키지는 여러 장소에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77332-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="77332-106">**[NuGet.org](https://www.nuget.org/)** 는 NuGet 패키지에 대한 기본 온라인 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="77332-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="77332-107">NuGet.org의 모든 패키지는 모두에게 공개적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="77332-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="77332-108">기본적으로 Visual Studio에는 패키지 소스로 NuGet.org가 있으며, 많은 개발자에게 NuGet.org는 상호 작용할 수 있는 유일한 패키지 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="77332-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="77332-109">NuGet.org는 커뮤니티 피드백을 원하는 안정적인 패키지 및 시험판 패키지를 게시하기 가장 좋은 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="77332-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="77332-110">**[MyGet](https://myget.org/)** 은 오픈 소스 프로젝트에 대한 사용자 지정 패키지 피드를 지원하는 리포지토리 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="77332-110">**[MyGet](https://myget.org/)** is a repository service that supports custom package feeds for open-source projects.</span></span> <span data-ttu-id="77332-111">MyGet 공용 사용자 지정 피드는 CI 서비스로 만든 시험판 패키지를 게시하기에 이상적인 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="77332-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="77332-112">또한 MyGet은 상업적으로 개인 피드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="77332-113">**[로컬 피드](/nuget/hosting-packages/local-feeds)** 를 통해 폴더를 패키지 리포지토리처럼 취급할 수 있고 NuGet에서 폴더의 `*.nupkg` 파일에 액세스할 수도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77332-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="77332-114">로컬 피드는 NuGet.org에 NuGet 패키지를 게시하기 전에 해당 패키지를 테스트하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="77332-115">패키지가 업로드되면 NuGet.org는 [패키지 삭제를 허용하지 않습니다](/nuget/policies/deleting-packages).</span><span class="sxs-lookup"><span data-stu-id="77332-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="77332-116">패키지는 UI에 공개적으로 표시되지 않도록 나열을 취소할 수 있지만, `*.nupkg`는 복원 시 계속 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77332-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="77332-117">또한 nuget.org에서는 중복 패키지 버전을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77332-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="77332-118">오류가 있는 NuGet 패키지를 수정하려면 잘못된 패키지를 나열 취소하고 버전 번호를 늘리고 패키지의 새 버전을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="77332-119">✔️ 커뮤니티 피드백을 원하는 [안정적인 패키지 및 시험판 패키지를 NuGet.org에 게시](/nuget/create-packages/publish-a-package)합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-119">✔️ DO [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="77332-120">✔️ 연속 통합 빌드에서 시험판 패키지를 MyGet 피드에 게시하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="77332-120">✔️ CONSIDER publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="77332-121">✔️ 로컬 피드 또는 MyGet을 사용하여 개발 환경에서 패키지를 테스트하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="77332-121">✔️ CONSIDER testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="77332-122">패키지가 작동하는지 확인하고 해당 패키지를 NuGet.org에 게시하세요.</span><span class="sxs-lookup"><span data-stu-id="77332-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="77332-123">NuGet.org 보안</span><span class="sxs-lookup"><span data-stu-id="77332-123">NuGet.org security</span></span>

<span data-ttu-id="77332-124">공격자가 NuGet 계정에 액세스하여 라이브러리의 악성 버전을 업로드할 수 없는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="77332-125">NuGet.org는 패키지가 게시될 때 2단계 인증 및 전자 메일 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="77332-126">NuGet.org에 로그인한 후 **계정 설정** 페이지에서 이러한 기능을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="77332-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="77332-127">![대체 텍스트](./media/publish-nuget-package/nuget-2fa.png "NuGet 계정 보안")</span><span class="sxs-lookup"><span data-stu-id="77332-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="77332-128">✔️ Microsoft 계정을 사용하여 NuGet에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-128">✔️ DO use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="77332-129">✔️ NuGet 액세스에 대해 2단계 인증을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-129">✔️ DO enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="77332-130">✔️ 패키지가 게시될 때 이메일 알림을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77332-130">✔️ DO enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="77332-131">[이전](sourcelink.md)
>[다음](versioning.md)</span><span class="sxs-lookup"><span data-stu-id="77332-131">[Previous](sourcelink.md)
[Next](versioning.md)</span></span>
