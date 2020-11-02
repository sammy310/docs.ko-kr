---
title: 어셈블리 위치
description: .NET 어셈블리의 위치에 따라 CLR에서 해당 어셈블리를 찾는 방법과 해당 어셈블리가 다른 어셈블리와 공유할 수 있는지 여부가 결정됩니다.
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 1fa1c486c0cddce4ddcfae7f2df27e2e85c88e66
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687600"
---
# <a name="assembly-location"></a><span data-ttu-id="392cd-103">어셈블리 위치</span><span class="sxs-lookup"><span data-stu-id="392cd-103">Assembly location</span></span>

<span data-ttu-id="392cd-104">어셈블리 위치에 따라 공용 언어 런타임이 참조 시 해당 위치를 찾을 수 있는지 여부가 결정되고 어셈블리를 다른 어셈블리와 공유할 수 있는지 여부도 결정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-104">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="392cd-105">다음 위치에 어셈블리를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-105">You can deploy an assembly in the following locations:</span></span>

- <span data-ttu-id="392cd-106">애플리케이션의 디렉터리 또는 하위 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="392cd-106">The application's directory or subdirectories.</span></span>

     <span data-ttu-id="392cd-107">어셈블리를 배포할 수 있는 가장 일반적인 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-107">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="392cd-108">애플리케이션 루트 디렉터리의 하위 디렉터리는 언어 또는 문화권에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-108">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="392cd-109">어셈블리에 문화권 특성의 정보가 있으면 어셈블리는 애플리케이션 디렉터리 아래 하위 디렉터리에 문화권 이름과 함께 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-109">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>

- <span data-ttu-id="392cd-110">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="392cd-110">The global assembly cache.</span></span>

     <span data-ttu-id="392cd-111">공용 언어 런타임이 설치되는 모든 위치에 설치되는 컴퓨터 수준 코드 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-111">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="392cd-112">대부분의 경우 어셈블리를 여러 애플리케이션과 공유하려고 하면 어셈블리를 전역 어셈블리 캐시에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-112">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>

- <span data-ttu-id="392cd-113">HTTP 서버에.</span><span class="sxs-lookup"><span data-stu-id="392cd-113">On an HTTP server.</span></span>

     <span data-ttu-id="392cd-114">HTTP 서버에 배포되는 어셈블리에는 강력한 이름이 있어야 합니다. 애플리케이션 구성 파일의 코드베이스 섹션에 있는 어셈블리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="392cd-114">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="392cd-115">참조</span><span class="sxs-lookup"><span data-stu-id="392cd-115">See also</span></span>

- [<span data-ttu-id="392cd-116">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="392cd-116">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="392cd-117">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="392cd-117">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="392cd-118">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="392cd-118">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
